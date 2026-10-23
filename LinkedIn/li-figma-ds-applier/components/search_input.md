# Search Input

**Component:** `Search Input SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use when the action of searching by text within a form or page context is needed.
- **Not** for global search (top navigation) — use `Global Search Input SDUI` instead.

---

## Types

| Type | Use |
|---|---|
| **Stand-alone** | Search blends with the interface. Used in contexts like messaging search where the field is the primary element. |
| **Within a form** | Search is clearly distinguished from other form elements. Used in lists, tables, filter forms. |
| **Global Search** | Top/global navigation bar only — separate component. |

---

## Anatomy

| Slot | Rule |
|---|---|
| **Visible Label (A)** | Optional — but always required programmatically. May be omitted visually when purpose is clear from context (single prominent search bar, limited space). |
| **Search icon (B)** | Optional decorative icon indicating search function. Either search icon OR placeholder text must be present — cannot omit both. |
| **Hint/Placeholder (C)** | Optional placeholder text when value is empty. Either B or C must be present. |
| **Helper text (D)** | Optional. Provides tips or context. Never put critical instructions here. |
| **Value (E)** | The text the user has entered. Does not wrap — scrolls horizontally. |
| **Clear button (F)** | Appears when field has a value. Clears the field and returns focus to the empty input state. |

---

## Sizes (Within a form only)

| Size | Use |
|---|---|
| **Small (default)** | Compact UIs, dense layouts, logged-in experiences |
| **Large** | Low information density experiences with available space |

---

## Component property keys

Use these with `setProperties()` to show/hide slots and set text values programmatically.

**Boolean props (show/hide):**
| Property | Key | Default |
|---|---|---|
| Label | `Label#35619:0` | `true` |
| Helper text | `Helper text#28294:51` | `false` |
| Hint text | `Hint text#36528:15` | `false` |
| Search Icon | `Search Icon#62902:0` | `true` |

**Text props (set value):**
| Property | Key |
|---|---|
| Hint text value | `↳ Hint text#122952:50` |
| Label value | `↳ Label#122952:25` |
| Helper text value | `↳ Helper text#122952:75` |
| Input value | `Value#122952:100` |

---

## Behavior

- State changes are reflected in the container border.
- **States:** Enabled / Hover (web) / Active / Typing / Disabled
- When the field is filled and the user returns to focus, all current text is selected unless the user positions the cursor manually.
- Errors: no error state on the input itself. Show errors in the search results area; display "no results" messages rather than input errors.
- Input value does not wrap — overflows horizontally; users scroll by moving the cursor to the left/right edge.

---

## Accessibility

**Target size:**
- Small (with label): ~48px
- Large: ~70px
- Clear button: 32px (compact)

**Keyboard:**
- Empty field: single focus stop on the input.
- Filled field: two focus stops — input field and Clear button.
- `Tab` — moves focus to search input (then to Clear button if present)
- `←` / `→` — moves cursor within the input
- Any character key — inserts at cursor position
- `↓` — moves sub-focus to typeahead menu (if present)
- `Enter` — submits the search form
- Clear button: inherits Button keyboard behavior

**Focus indicator:** Search input and Clear button have distinct, visible focus indicators.

**Name, Role, Value:**

*Search Input:*
- Role: `search`
- Label: use visible label text. If no visible label, provide programmatic label starting with "Search" (e.g. `aria-label="Search messages"`)
- Hint/placeholder: never put critical instructions here — it may not be perceivable by all users
- Helper text: linked programmatically (e.g. `aria-description` or `UIAccessibilityHint`)
- Value: the current text entered by the user

*Clear button:*
- Inherits Button properties
- Non-visible label: `"Clear"` (or `"Clear search"` if other Clear buttons are present on the page)

**Color & Contrast:**
- All default colors meet minimum requirements for light and dark modes.
- Disabled state is exempt from contrast minimums.
