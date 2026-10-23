# Entity Lockup

**Component:** `Entity Lockup SDUI`, `Circle Entity Lockup SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## Usage contexts

The Entity Lockup component has a built-in **Text Alignment layer** that holds the title, subtitle, and metadata in a horizontal layout alongside the entity image. The default behavior is to use this layer as-is. Hiding it is only allowed in the specific contexts below.

### Feeds, lists, and cards (default)
Use Entity Lockup SDUI as-is. **Never hide the Text Alignment layer.** This is the correct representation for:
- Feed posts and content cards (content header with name, role, and timestamp)
- Search results and recommendation lists
- Message threads and conversation headers
- Any surface where entity details appear next to the image in a horizontal row

### Profile and module headers
For profile headers where a large centered entity photo is the focal point and custom typographic hierarchy appears below (not beside) it, you may hide the Text Alignment layer. Rules:
- This is the **only approved context** for hiding the Text Alignment layer
- All text below the image must be separate text nodes with `textStyleId` bound to DS Typography 2.0 styles — never raw `fontName`/`fontSize`/`lineHeight`
- Use `Heading L` or `Heading M` for the member name, `Supportive M` for role/headline

### Company and school logos in Experience / Education rows
For logo-in-row layouts (e.g. a company logo beside job title and date range), use Entity Lockup SDUI (Square, Size 48) with the Text Alignment layer hidden. The surrounding row frame provides the text column — the lockup provides only the logo.

---

### Decision tree

```
Entity appears in a horizontal row with text beside it?
  → YES: Use Entity Lockup as-is. Never hide Text Alignment.
  → NO: Is the entity photo the large visual anchor with text stacked below?
      → YES (profile header): Use Entity Lockup, hide Text Alignment. All text must use textStyleId.
      → NO: Is this a logo-only slot in an Experience/Education row?
          → YES: Use Entity Lockup (Square, 48), hide Text Alignment.
          → NO: Use Entity SDUI (standalone photo component).
```

---

## When to use

- Use to represent LinkedIn entities (members, companies, jobs) in context alongside other content.
- Acts as a navigation link to the entity's profile or home page.
- Connects contributions to their authors or sources.

---

## Best practices

**Identify the Entity — always include image + title together** unless one of the approved contexts in **Usage contexts** above applies (profile headers or logo-in-row). In default use (feeds, lists, cards), the entity image and title must always appear together — separating them makes the entity unrecognizable and defeats the component's purpose.

**Use elements contextually.** Select subtitle, metadata, and tags that share concise, valuable insights for the specific placement context. The information should instantly connect members with each other and guide them to other resources and opportunities. Think about the context in which you are using the component as you add or remove additional details.

**Placement:**
- *Content headers / visual anchors* — used at the top of a card, post, or section to tie the entity to its content.
- *Lists and conversations* — used in feeds, message threads, or result lists.

---

## Anatomy

| Slot | Rule |
|---|---|
| **Entity Image (A)** | Required. Circle or Square. Holds image, Entity Ghost, or Entity Initials. |
| **Title (B)** | Required. Member name or entity name. Web = head/subhead; iOS = name/subhead. |
| **Badge (C)** | Optional. Indicates LinkedIn membership status. |
| **Degree (D)** | Optional. Shows connection degree between members (1st, 2nd, 3rd). |
| **Tag (E)** | Optional. Denotes role, status, degree, or relationship. |
| **Subtitle (F)** | Optional. Job title, company, industry, location, or headline. |
| **Metadata (G)** | Optional. Timestamp or date (e.g., "posted 10 days ago", "1w · Edited"). |

---

## Internal layout behavior

After placing an Entity Lockup instance, the internal `Content Alignment` frame defaults to `layoutSizingHorizontal = 'HUG'`, which constrains the text column to ~72px regardless of how wide the lockup is. Always set it to `'FILL'` immediately after placing:

```js
const contentAlignment = instance.findOne(n => n.name === 'Content Alignment');
if (contentAlignment) contentAlignment.layoutSizingHorizontal = 'FILL';
```

The individual text nodes inside also use `textAutoResize: 'HEIGHT'` with a fixed width — after setting FILL on the parent, set each text node to `textAutoResize = 'WIDTH_AND_HEIGHT'` or resize explicitly to match the available width.

**Internal text node names** (use these when setting text content programmatically):
| Slot | Internal node name |
|---|---|
| Title | `Firstname Lastname` |
| Subtitle | `Subheading` |

---

## Component property keys

Use these with `setProperties()` to show/hide optional slots programmatically.

| Property | Key | Values |
|---|---|---|
| Badge | `Badge#42745:0` | `true` / `false` |
| Degree | `Degree#28269:42` | `true` / `false` |
| Subtitle | `Subtitle#28062:52` | `true` / `false` |
| Timestamp | `Timestamp#28062:64` | `true` / `false` |
| Tag | `Tag#28062:23` | `true` / `false` |

---

## Sizes

Supports Circle and Square entities in 5 sizes: **24, 32, 40, 48, 64**.

Text size is not manually adjustable — the component controls and adjusts text size automatically for each size variant.

---

## Adaptability

**Wrapping:** All text elements wrap; they never truncate.

**Tag:** Wraps to the next line when extremely long.

**InBug Badge:** Always appended to the last word of the Title using a non-breaking space (`&nbsp;`). Does not differentiate first vs. last name to accommodate RTL languages.

**Font scaling:** All text elements grow or shrink with font scale changes. Plan for increased vertical space at 200% scale — single-line text may wrap to multiple lines. (MAS 1.4.4 Resize text, MAS 1.4.12 Text spacing)

**RTL:** Text and layout mirror direction.

---

## Interaction

Entity Lockup acts as a link — tapping/clicking navigates to the entity's profile page.
