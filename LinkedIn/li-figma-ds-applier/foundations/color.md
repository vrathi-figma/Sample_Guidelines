# Color Tokens

**Library:** DS Color Library (`bxdWZ7oDbeJFZMJUCDwZsV`)

---

## How to read a color token name

Color token names are composed of segments in a fixed order. The prefix `color` is always first. Each segment category may contribute at most one value per token name. Not all segments are required — only those needed for the desired level of specificity.

```
color - [feature] - [component] - [element] - [concept] - [intensity] - [application] - [x_scale] - [scale] - [interaction_state] - [flag]
```

To interpret any token: decompose by segment order, look up each segment value's definition below, and intersect their meanings.

---

## Composition rules

- Segments always appear in the order defined above
- At most one value from each segment category per token name
- Fewer segments = broader application; more segments = more specific and constrained use
- Tokens omitting the `element` segment are **concept-level** — they apply to any relevant foreground surface (text, icon, label, border) and may be used as background fills depending on design treatment
- The `element` segment determines the applicable design property — tokens with an element segment are restricted to that element's surface
- Tokens sharing the same root with an `interaction_state` suffix (`hover`, `active`, `disabled`) form a **state set** — always check for and apply sibling state tokens to corresponding interaction states
- When multiple element tokens are applied to the same interactive surface (background + label + icon + border), all elements advance their interaction state together — if the background moves to hover, the label, icon, and border on that surface should also move to their hover variants
- Overlay and transparent state tokens (`intensity: transparent`, `application: overlay`) are unrestricted by surface and may be applied to any design property
- `feature`-scoped tokens are for that feature team's defined context only — do not use outside that context without consultation
- `component`-scoped tokens apply within that component only — do not use them on other elements

---

## Segment definitions

### element
The UI surface or role the token applies to. When present, the token is scoped to that surface.

| Value | Applies to |
|---|---|
| `background` | Background fills behind content — containers, cards, screens, and layout surfaces |
| `border` | Strokes, dividers, and outlines on structural or interactive elements |
| `text` | Default typographic content |
| `text-meta` | Meta typographic content |
| `label` | Component labels |
| `link` | Links |
| `icon` | Icon fills |
| `scrim` | Scrim and overlay layers that obscure content beneath — modals, drawers, bottom sheets |
| `indicator` | Indicators |
| `track` | Slider or progress tracks |
| `shadow` | Elevation composite tokens |
| `logo` | LinkedIn logo assets |
| `signal` | AI identity assets |
| `coachmark` | Coachmark elements |
| `inbug` | Inbug elements |

### concept
The design intent or feedback meaning, with a fixed color association per concept. Concept-level tokens omit the element segment and apply across any relevant surface depending on design treatment. Each concept ships as a complete structured set: foreground root + hover + active states, background fills (strong, soft), and transparent background fills (hover + active).

| Value | Meaning |
|---|---|
| `action` | Primary interactive actions and component interactivity. Maps to brand blue |
| `positive` | Communicating success or confirmation. Maps to green |
| `negative` | Communicating errors or destructive actions. Maps to red |
| `caution` | Communicating warnings or states requiring user attention. Maps to orange |
| `alert` | Alert and notification states |
| `neutral` | Tonally neutral colors with no brand or feedback association |
| `accent` | Brand accent colors for stylistic brand expression. Color varies per accent family (`accent-1` = amber, `accent-2` = warm-red, etc.) |
| `brand` | Primary brand color moments |
| `new` | Highlighting new or unread content |
| `current` | Communicating the currently active or selected navigation item |
| `loading` | Loading and in-progress states |
| `checked` | Communicating a checked or selected input state. Maps to system green |
| `visited` | Previously visited link states. Web only. No background fills |
| `mono` | Monochromatic color moments with no brand or feedback association |
| `categorical` | Categorical color sequences for data visualizations. No fixed color — values assigned sequentially per series position |

### intensity
The visual weight or opacity treatment of the color.

| Value | Meaning |
|---|---|
| `strong` | High opacity or saturation. The most prominent non-solid treatment |
| `soft` | Low opacity. Gentle presence, less prominent than subtle |
| `subtle` | Low-medium opacity. Present but understated — a step above soft |
| `faint` | Very low opacity or luminosity. Barely-there presence, lightest background washes |
| `solid` | Full opacity. No transparency applied |
| `knockout` | Visually reversed out of its background to match the background color behind its parent container |
| `transparent` | Fully or near-fully transparent. Used in components where an invisible fill is desired in the enabled state, with visual feedback for hover and active states (e.g. Secondary/Tertiary Buttons, Tabs, Numbered Pagination) |

### interaction_state
The interaction state the token applies to. The root token without an interaction_state suffix is the resting/enabled state. State variants inherit the root token's element, concept, and application.

| Value | Meaning |
|---|---|
| `hover` | Cursor hover state. Web only |
| `active` | Pressed or activated state |
| `disabled` | Disabled — not interactive or not available |
| `inactive` | Inactive or de-emphasized. Web only, reserved for data visualization |

### application
A specific contextual use case that further narrows where the token applies.

| Value | Meaning |
|---|---|
| `overlay` | Provides enough contrast to the background it is overlaid on |
| `offset` | Needs to be offset from `color-background` |
| `gap` | Appears as a visible gap, revealing the background color beneath the element. Can be overridden to match the context background |
| `grid` | Grid and layout guide colors |
| `conceal` | Meets a certain visual quality to hide information |
| `range` | Range input and slider fill colors |

### feature
Scopes the token to a specific product feature team. Not for use outside that feature's defined context without consultation.

| Value | Feature team |
|---|---|
| `premium` | Premium |
| `data` | Data visualization |
| `media` | Media |
| `editorial` | Editorial |
| `search` | Search |
| `reactions` | Reactions |
| `agent` | Agentic / agent features |
| `fif` | FIF |
| `presence` | Messaging presence |

### component
Scopes the token to a specific UI component. Apply within that component only.

`button` · `input` · `nav` · `table` · `tag` · `skeleton` · `callout` · `qr-code`

### flag
Marks a special constraint or platform-specific condition.

| Value | Meaning |
|---|---|
| `legacy` | Temporary token needed during major concept color shifts or feature deprecation |
| `mobile` | Mobile-specific |
| `android` | Android-specific |

---

## Usage definitions

Explicit usage guidance for tokens where the naming architecture alone is insufficient. Tokens not listed here can be interpreted by composing the segment definitions above.

### Background

| Token | Usage |
|---|---|
| `color-background` | Default for all backgrounds — pages, sections, cards, containers, and surfaces. Use as the default unless specified otherwise, except for main page-level backgrounds which use `color-background-offset` |
| `color-background-knockout` | Use when a component background needs to appear knocked out from the parent container it sits on top of in an enabled state |
| `color-background-faint` | Use only in components that need a faint semi-opaque background in an enabled state, such as Tag or Skeleton Loader |
| `color-background-overlay` | A nearly-opaque background for component backgrounds that are overlaid, such as Carousel navigation control buttons |
| `color-background-transparent` | Use only for components with a transparent background in the enabled state, such as Tabs or Pagination |
| `color-background-transparent-overlay` | For components that need a transparent background when placed on top of overlaid backgrounds in an enabled state |
| `color-background-neutral-strong` | Alternative stronger neutral background for optical sectioning within layouts. Use as fills for cards, tags, or other surfaces — not for entire pages or page sections. Use when color should not be a main focus. Default to `neutral-soft` unless a stronger variant is specified |
| `color-background-neutral-soft` | Alternative soft neutral background for optical sectioning within layouts. Use as fills for cards, tags, or other surfaces — not for entire pages or page sections. **Default neutral background choice** — use `neutral-strong` only when explicitly specified |
| `color-background-offset` | Page-wide background on **web only** — offsets the page from the main product experience where `color-background` surfaces sit. Do not use anywhere other than the main page background |
| `color-background-offset-mobile` | Page-wide background on **mobile only** — same purpose as `color-background-offset`. Do not use anywhere other than the main page background |
| `color-background-disabled` | Default color for disabled backgrounds |

### Border

| Token | Usage |
|---|---|
| `color-border` | Default border for components with an outline — muted buttons, input fields, and dividers in an enabled state |
| `color-border-faint` | Default border for outlined containers and dividers between lists of content in an enabled state. Only use a border on cards when both the card and its parent container use `color-background` |
| `color-border-grid` | Solid border for overlapping cell borders and dividers within a grid structure, like a table or chart |
| `color-border-knockout` | Use for borders that need to appear knocked out from the parent container. See knockout intensity definition for guidance |
| `color-border-gap` | Use to create an optical gap between two overlapping elements, such as when an element sits inset into another and needs a distinguishing border |
| `color-border-disabled` | Default border for outlined containers, components, and dividers in a disabled state |

### Text

| Token | Usage |
|---|---|
| `color-text` | Default for all type styles in the enabled state — all text elements outside of components, UGC content, and non-label text in components like entity names |
| `color-text-disabled` | Default for all type styles in the disabled state |
| `color-text-meta` | Reserved for meta content. Use only with Supportive type styles in the enabled state. Includes timestamps, social proof, and captions |
| `color-text-solid` | Solid version of default text tokens for Arabic and other language systems with overlapping characters |
| `color-text-meta-solid` | Solid version of text-meta tokens for Arabic and other scripts with overlapping characters |
| `color-text-overlay` | Reserved for text placed on top of noisy backgrounds (images, videos) to improve legibility |

### Label

| Token | Usage |
|---|---|
| `color-label` | Default label color for all component labels — sits slightly apart from primary content but prominent enough to attract attention to the component action. Not for standalone typographic elements outside components |

### Link

| Token | Usage |
|---|---|
| `color-link` | Default styling for all links in the enabled state. Standalone links do not need to be underlined; inline links should be underlined. **Never use `color-action` for links** |
| `color-link-visited` | Default styling for all visited links. Standalone links do not need to be underlined; inline links should be underlined |

### Icon

| Token | Usage |
|---|---|
| `color-icon` | Default icon color for all icons in the enabled state. Icons are designed to match label color — sits between default text and meta text in intensity, so can be paired with either |
| `color-icon-overlay` | Default icon color for icons on top of noisy backgrounds (images, videos) to improve legibility |
| `color-icon-knockout` | Default icon color for icons that need to appear knocked out from the background. Intended for components that need to be inverted from the current light/dark mode standard |

### Nav

| Token | Usage |
|---|---|
| `color-nav-icon` | Default icon color for navigational icons only in the enabled state. Do not apply to non-navigational icons |

### Scrim

| Token | Usage |
|---|---|
| `color-scrim` | Reserved exclusively for a scrim layer between the main page and an elevated element (modals, drawers, bottom sheets) |
| `color-scrim-conceal` | More opaque version of the default scrim — designed to obscure content below |

---

## Variable keys (DS Color Library — `bxdWZ7oDbeJFZMJUCDwZsV`)

Use `importVariableByKeyAsync(key)` to bind color variables directly — do not use collection discovery or name-string filtering.

```js
const variable = await figma.variables.importVariableByKeyAsync(key);
node.fills = [figma.variables.setBoundVariableForPaint(
  { type: 'SOLID', color: { r: 0, g: 0, b: 0 } },
  'color',
  variable
)];
```

### Text
| Token | Key |
|---|---|
| `Text/color-text` | `ff25a8c71bee6dd6fcea792b5240e676ca712e42` |
| `Text/color-text-meta` | `3b3ea0b59103ddec8629e94262f038166c80cd6c` |
| `Text/color-text-disabled` | `ae4e1a9234e91999bec3643447af7dde3bbaa581` |

### Background
| Token | Key |
|---|---|
| `Background/color-background` | `74531ac3e791aa4d846e1eba406bfaf0880722bc` |
| `Background/color-background-neutral-soft` | `9b464fdf5f847b42273c018e6d62735b9758a6ac` |
| `Background/color-background-offset` | `35c08776645e05145df00234aad1e5e0e004e278` |
| `Background/color-background-disabled` | `cf3cc8a7c00cbbb6cff07ab7bc8eda00dbeb477d` |

### Border
| Token | Key |
|---|---|
| `Border/color-border` | `58ebec0c5b5d6fa15a1791652784a749dd99833a` |
| `Border/color-border-faint` | `8a1aadb49cc8b003deaf5d3281fe0945f9fff4f8` |
| `Border/color-border-subtle` | `a80e92633489a8431577c18d59e0c3cacfb9a149` |
| `Border/color-border-disabled` | `5b2fbc7263f21436a3c5364ee7da3e494ed56692` |

### Icon
| Token | Key |
|---|---|
| `Icon/color-icon` | `0e7a397bef0c04ebf2a293daf71f31fdd9466c87` |
| `Icon/color-icon-disabled` | `b49786761109a618df07ac97721514be6c1ea902` |

### Semantic / Feedback
| Token | Key |
|---|---|
| `Action/color-action` | `96f3a671834773afc4ebe8b9d6631af7d890f672` |
| `Positive/color-positive` | `31aaddcdc46be1d1a2213037240d0305de5f22f1` |
| `Negative/color-negative` | `8f60d201115342d3cec4f192c653dd5ac02f9ee0` |
| `Caution/color-caution` | `d2cefd55bdd97bf14ceac8b2fafe5e547fe16335` |

For tokens not listed above, call `getAvailableLibraryVariableCollectionsAsync()` and filter for the DS Color Library by file key `bxdWZ7oDbeJFZMJUCDwZsV`, then import by key. If a token cannot be found, stop and ask the designer — do not fall back to hardcoded hex values.

---

## Disambiguation

**`color-background-neutral-soft` vs `color-background-neutral-strong`**
Both are for optical sectioning within layouts. Use `soft` for a lighter separation, `strong` for more visual contrast. Neither is appropriate for large page backgrounds — use `color-background` or `color-background-offset` instead.

**Concept-level tokens on multiple surfaces**
Tokens like `color-action` (no element segment) can apply to text, icon, border, or background fill. General surface affinity by concept:
- `action` — primarily background fill on buttons; text/icon on ghost buttons and interactive elements. **Never use for links — use `color-link` instead**
- `positive`, `negative`, `caution` — for communicating system feedback only. Never use to add stylistic interest. Background fills for feedback containers; foreground for text/icon in inline feedback

**Accent colors**
Brand accent colors (`color-accent-1` through `color-accent-7`) are for stylistic interest only — not for branding features or conveying meaning.
- `accent-1` (amber) — **reserved for Premium only**
- `accent-2` = warm-red, `accent-3` = lime, `accent-4` = cool-gray, `accent-5` = teal, `accent-6` = purple, `accent-7` = pink

**State sets**
When a token has `hover` and `active` siblings, always apply the full set to interactive elements. Example: `color-background` on a card that's tappable → `color-background-hover` on hover, `color-background-active` on press.
