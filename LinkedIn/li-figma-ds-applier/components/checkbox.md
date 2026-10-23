# Checkbox

**Component:** `Checkbox SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to select one or more items from a group.
- Use a single checkbox for binary decisions: accepting T&C, consenting to data collection, opting into newsletters.

## Component property keys

| Property | Key | Default |
|---|---|---|
| Helper text | `Helper text#35446:0` | `true` — set to `false` to hide |

---

**Choose the right input:**
| Use case | Component |
|---|---|
| Select multiple from a group | Checkbox |
| Select exactly one from a group | Radio |
| Toggle on/off without a form submit | Switch |
| Select one from a collapsed list | Select |

Checkboxes are one of many inputs that afford selection. Use them in groups when multiple options can be selected or unchecked. For all other selection use cases, consider Radio (single value from a group of possible options), Switch (toggling a value on/off without submitting a form), or Select (expanding a list for a single value).

---

## How to configure

**Anatomy:**
| Slot | Rule |
|---|---|
| Checkbox | The interactive toggle element. |
| Label | Visible text describing the choice. Doubles as a11y label. If hidden visually, provide `aria-label`. |
| Helper text | Optional. Supplemental guidance to help the user decide. |

**Variants:**
| Property | Values |
|---|---|
| `State` | `Enabled` · `Hover` · `Active` · `Disabled` |
| `Checked` | `True` · `False` |
| `Indeterminate` | `True` · `False` |
| `Flip` | `False` (label right, default) · `True` (label left) |

**Flip:** Use `Flip=True` when layout requires the label on the left side of the checkbox.

**Indeterminate state:** Use only when a parent checkbox represents a group where some (but not all) children are checked. It is neither checked nor unchecked.

---

## Interaction

- Clicking the checkbox or its label toggles the state.
- Clicking an indeterminate checkbox → becomes checked; second click → unchecked.

**Parent-child relationships:**
- Parent checked → all children check.
- Parent unchecked → all children uncheck.
- Some (not all) children checked → parent becomes indeterminate.
- Note: parent-child logic is not built into the component — each product team must implement it.

**Errors:** Show `Inline Feedback` directly beneath the checkbox group when validation fails.

---

## Adaptability

- Labels wrap to multiple lines; checkbox stays top-aligned when label wraps.
- Checkbox fills the horizontal width of its container. On wide layouts (e.g. landscape mobile), limit width for long labels to preserve readability.
- Text scaling: label and helper text grow with system text size; checkbox control stays default size. Layouts must expand vertically to accommodate.

---

## Content rules

- Use active voice, positive phrasing. Avoid double negatives and jargon.
- Sentence case. Short, clearly distinguishable options.
- Organize logically: numerically, chronologically, by subject, or alphabetically.
- Be consistent: all options lead with nouns, or all with verbs.

---

## Internationalization

- **RTL:** All content (checkbox + label) flips to match the reading direction of the locale.
- **Other languages:** Write labels with translation in mind. Avoid abbreviations that may not translate.

---

## Accessibility

**Target size:**
- Default: 48px tap target.
- Web compact: 32px (use sparingly — reduces usability).

**Focus indicator:** Must be visible and unobscured when focused.

**Keyboard operation (non-disabled only):**

Single checkbox:
- `Tab` — move focus to checkbox
- `Enter` — activate (toggle)

Checkbox group:
- `Tab` — move focus to group (lands on first non-disabled checkbox)
- `↓` / `↑` — move between checkboxes within the group
- `Space` — toggle focused checkbox

**Name, Role, Value:**
- Role: `checkbox`.
- A11y label: Use the visible label. If label is hidden, provide `aria-label`.
- Helper text: Supplemental — may or may not be surfaced by assistive technology depending on settings.

**Color & Contrast:**
- Checkbox square (control): 3:1 contrast with background.
- Label and helper text: 4.5:1 contrast with background.
- Disabled state has no contrast requirement — assume some members won't perceive it.
