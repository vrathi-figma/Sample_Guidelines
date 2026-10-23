# Typography Tokens

**Library:** DS Typography 2.0 (`1Dle3oNSHgIg9jewHabgfW`)

---

## Fonts

DS Typography 2.0 styles use the **SF Pro** font family — not Inter. Defaulting to `Inter` will cause `set_characters` to throw `Cannot write to node with unloaded font "SF Pro Text Regular"` the first time a text style is applied. Load SF Pro up front; include Inter only as a backup.

In Flash mode, load all required fonts in one `Promise.all` at the start of the generation call:

```js
async function tryLoadFont(family, style) {
  try { await figma.loadFontAsync({ family, style }); return true; }
  catch (e) { return false; }
}
await Promise.all([
  tryLoadFont('SF Pro Text', 'Regular'),
  tryLoadFont('SF Pro Text', 'Medium'),
  tryLoadFont('SF Pro Text', 'Semibold'),
  tryLoadFont('SF Pro Text', 'Bold'),
  tryLoadFont('SF Pro Display', 'Regular'),
  tryLoadFont('SF Pro Display', 'Medium'),
  tryLoadFont('SF Pro Display', 'Semibold'),
  tryLoadFont('SF Pro Display', 'Bold'),
]);
```

**SF Pro Text** powers most styles (Supportive, Title, Heading, Body, Prose).
**SF Pro Display** powers the Display group.
The `tryLoadFont` wrapper means a missing weight on one platform won't tank the whole `Promise.all`.

**When setting characters on text inside an imported instance** (e.g. `Firstname Lastname` / `Subheading` inside an Entity Lockup), the node may use a font weight you didn't preload. Read `node.fontName` and call `figma.loadFontAsync(node.fontName)` before writing characters:

```js
const fn = textNode.fontName;
if (fn && fn !== figma.mixed && fn.family) await figma.loadFontAsync(fn);
textNode.characters = value;
```

See anti-pattern `inter-font-default`.

---

## How to read a typography token name

Font semantic token names are composed of segments in a fixed order. No prefix. The semantic group defines the typographic role. Size, weight, and style are optional modifiers.

```
[semantic_group] - [size] - [weight] - [style]
```

To interpret any token: decompose by segment order and intersect each segment value's meaning.

---

## Composition rules

- Segments always appear in the order defined above
- `semantic_group` is always required
- `size`, `weight`, and `style` are optional — include only those needed for specificity
- Bold styles (`weight: bold`) should never be used alone to create hierarchical distinctions within content — use them only for emphasis within a text element that already has a typographic role

---

## Segment definitions

### semantic_group
Identifies the typographic role. This is the primary decision — choose the group that matches the content's purpose, then compose with size and weight.

| Value | Role |
|---|---|
| `heading` | Highest level of hierarchy. Establishes content wayfinding — labels the page's sections within the workspace and layout |
| `title` | Hierarchical distinction within sections of content. Pair `title-s` and `title-l` together to create levels of hierarchy within a section |
| `supportive` | Nearly all component, UI, and system-generated text. Default for labels, metadata, captions, form fields, and any text that isn't reading content or a heading |
| `body` | Reading content on mobile and desktop. Designed at optimal size and leading. Never use for UI labels, component labels, or wayfinding |
| `prose` | Reading content at wider measure. Larger than body — for sustained reading. Never use for UI labels, component labels, or wayfinding |
| `display` | Graphic text elements to grab attention. Use sparingly — high contrast impact loses effect when overused |
| `code` | Monospaced content — code snippets, technical strings, terminal output |

---

## Per-style guidance

### Supportive

**`supportive-s`** (12px / 125%)
Reserved for the smallest details in UI — informative context that shouldn't distract from primary content. Commonly used for metadata, timestamps, dates, social proofs. Never use for member content / UGC.

**`supportive-m`** (14px / 125%)
The most common supportive style — use for the majority of functional content and system-generated text. Commonly used for component labels, subheadings, bullet lists. Should not typically be used for member content / UGC.

**`supportive-l`** (16px / 125%)
Larger supportive option, reserved for pairing with Display styles.

### Title

**`title-s`** (14px / 125%)
Smallest style designed for creating hierarchy. Commonly used for titles of sub-sections within lists and text lockups.

**`title-l`** (16px / 125%)
Commonly used for titles of lists and smaller content cards. May be used as a label in some component designs.

### Heading

**`heading-s`** (18px / 125%)
Sub-section and module headings at a secondary level of wayfinding. Typically used only once per sub-section or module.

**`heading-m`** (20px / 125%)
Page section and layout framework headings for the highest level of hierarchy in **mobile** contexts. Typically used only once per section.

**`heading-l`** (24px / 125%)
Page section and layout framework headings for the highest level of hierarchy in **desktop** contexts. Typically used only once per section.

### Body & Prose

**`body`** (14px / 150%)
For text spanning at least 1 paragraph (~500 characters). Can be used for system-generated paragraph text (contextual info, feature instructions). Commonly used for UGC outside dedicated reading environments — posts, comments on Feed.

**`prose`** (18px / 150%)
For text spanning at least 2 paragraphs (1000+ characters). Long-form content: articles, newsletters, job descriptions, publications.

### Display

**`display-s`** (24px) · **`display-m`** (30px) · **`display-l`** (36px) · **`display-xl`** (48px)
Graphic text to grab attention. Use sparingly — the high contrast impact loses effect when overused. All display styles are available in bold as a stylistic option.

### size
Identifies the size step within the semantic group's scale.

| Value | Step |
|---|---|
| `s` | Small |
| `m` | Medium |
| `l` | Large |
| `xl` | Extra large |

### weight
| Value | Meaning |
|---|---|
| `bold` | Bold-weight emphasis within the semantic group |

### style
| Value | Meaning |
|---|---|
| `italic` | Italic styling within the semantic group |

---

## Hierarchy decision guide

Use this to pick the right semantic group before composing with size.

**Is this a page or section label establishing navigation or wayfinding?**
→ `heading`

**Is this a title creating hierarchy within a section (e.g. a card title, module name, list item heading)?**
→ `title`

**Is this UI text — a label, caption, metadata, badge, tab, form field, button label, or any component text?**
→ `supportive`

**Is this reading content — a paragraph, article body, post text, or anything a user reads linearly?**
→ `body` (compact, 14px) or `prose` (wider measure, 18px)

**Is this a large graphic display moment — a hero headline, marketing callout, or attention-grabbing number?**
→ `display` — use sparingly

**Is this a price, numeric value, or data label?**
→ `supportive-bold` — not `title`. Title is for named content labels; supportive-bold is for emphasized UI text and values.

---

## Default size guidance

When no specific size is called for, start with these defaults:

| Group | Default | When to go larger | When to go smaller |
|---|---|---|---|
| `heading` | `heading-m` | `-l` for standalone landing sections | `-s` for secondary pages or embedded panels |
| `title` | `title-l` | — | `-s` for sub-items within a section (product names, list titles) |
| `supportive` | `supportive-m` | `-l` for primary actions and form inputs | `-s` for compact or dense contexts |
| `body` | `body` | `prose` for wider reading measure | — |
| `display` | `display-m` | `-l` / `-xl` for full-bleed hero moments | `-s` for smaller callouts |

---

## Disambiguation

**`body` vs `prose`**
Both are for reading content. `body` uses a smaller size (14px) and is appropriate for compact content blocks. `prose` uses a larger size (18px) and is for sustained reading at wider measure. Neither should be used for UI labels or component text.

**`supportive-bold` vs `title`**
Both can visually emphasize text within a layout. The distinction is purpose: `title` creates named content hierarchy (section names, card titles, item headings). `supportive-bold` emphasizes UI text, values, or labels — it doesn't imply a hierarchical position in the page structure.

**`heading` vs `title`**
`heading` labels the whole page structure — it's wayfinding. `title` creates hierarchy within a section. On a typical page: the section label is a `heading`, the items within that section have `title` styles.

---

## Text style keys (DS Typography 2.0 — `1Dle3oNSHgIg9jewHabgfW`)

Always apply text styles using `importStyleByKeyAsync(key)` and set `textStyleId` on the text node. Never hardcode `fontName`, `fontSize`, `lineHeight`, or `letterSpacing` on text nodes that should use a named style.

```js
const style = await figma.importStyleByKeyAsync(key);
textNode.textStyleId = style.id;
```

### Supportive
| Style | Key |
|---|---|
| `Supportive S` | `0128f78b0d7605eecb54b205890fb1294cceec66` |
| `Supportive S Bold` | `48c815e0fcdcf24f810c33b1e3c6181d711201a1` |
| `Supportive M` | `785dea1e475760864c241681e81a0ae90a10117f` |
| `Supportive M Bold` | `ae3aecdf429af7bd0d7bb3edc5b1b5fc51c2a9e3` |
| `Supportive L` | `8a6bed854c48f6036bad369572ba183c4b1d5d71` |
| `Supportive L Bold` | `cdb1ce208871e83608f490d034ec62cc5dad80d8` |

### Title
| Style | Key |
|---|---|
| `Title S` | `c307aa4a74eb84b93e194dcb60ecdfada0ac8fea` |
| `Title L` | `9f7bbdb7b1608474ec3b7acd3b540f432cdc2877` |

### Heading
| Style | Key |
|---|---|
| `Heading S` | `7604d4015d80d7137f0d682dbb973fd7461cf9c0` |
| `Heading M` | `885be3387ec88e5ec00b5bfbb2821a24e29931f5` |
| `Heading L` | `db7c9be642c2c6d96bd0e3013aa66c3f7293cadd` |

### Body & Prose
| Style | Key |
|---|---|
| `Body` | `922c3bdee7a366b68db056d373fd59537140271f` |
| `Body Bold` | `46bb7714a3700815512cdc0c10e71375d0b05e58` |
| `Body Italic` | `36f259681b1559bf440d49606eb761837806acd9` |
| `Body Bold Italic` | `92b4212af8756933c903e3142de7865449e7040a` |
| `Prose` | `99762eb4e3cda1ca09e7dc7d4b78e251fa0d3e3e` |
| `Prose Bold` | `5e0ace6ea1e5327d94250158d0d161f49ebac0a5` |
| `Prose Italic` | `88d01f518628d668c57029a27395c00d149039e6` |
| `Prose Bold Italic` | `0b1935b1e1e906b190d6b2729e50d6f25d5ea04b` |

### Display
| Style | Key |
|---|---|
| `Display S` | `295a500b755d0b614cc6497adee0df98f575f174` |
| `Display S Bold` | `d5fa5a0995f407f6b9a67c214236d405bcb68eba` |
| `Display M` | `47bf606c2a1a3cbfd4faafa3e6571b99e3a020f1` |
| `Display M Bold` | `e9b119f18c7256f8294e7c336b088f998e74990c` |
| `Display L` | `d96c34945fd3ee7bc3802cad913b2c517b4e7e29` |
| `Display L Bold` | `4cfaa43622ff863a12a4f9a1881b9630b1388020` |
| `Display XL` | `d925e8e7bf588d6152d26d8df265d430045057e7` |
| `Display XL Bold` | `a23a8a2ebfd18bd63f56ce106f5fdba93b341a75` |
