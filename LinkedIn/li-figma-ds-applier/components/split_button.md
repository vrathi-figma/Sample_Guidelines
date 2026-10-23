# Split Button

**Component:** `Split Button SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to combine a primary action with access to secondary options in a single compact component.
- The label area executes the default/primary action directly; the icon (caret) area opens a dropdown menu with additional options.

---

## Anatomy

| Slot | Rule |
|---|---|
| **Label (A)** | Required. States the primary action. Never truncated — wraps if space is tight. |
| **Icon (B)** | Required. A caret or similar icon indicating the presence of a dropdown menu. |
| **Container (C)** | Two independently interactive regions (label and icon) within a single component. |

---

## Interaction model

| Target | Behavior |
|---|---|
| **Label — hover** | Tooltip appears showing the default action context (e.g., "Save to Uncontacted"). Disappears when hover ends. |
| **Label — click** | Executes the primary action; returns button to enabled state. |
| **Icon — hover** | Tooltip appears showing the dropdown context (e.g., "Select pipeline stage to save to"). Disappears when hover ends. |
| **Icon — click** | Opens a Menu. Closes after a selection is made or user clicks outside. |
| **Menu selection** | Executes the selected action; returns button to enabled state. |

---

## States

States are tracked independently for the label and icon regions:
- **Enabled** — default resting state
- **Hover** — visual change on mouseover; tooltip may appear
- **Active** — pressed state

---

## Adaptability

- Label text **wraps** to multiple lines — never truncated. Labels should be kept concise.
- When labels wrap, corner radius = half the button's minimum height (for consistent rounding).
- When button groups are in tight space, they stack vertically — most critical action at the top.
- **Internationalization:** Prioritize semantic accuracy over literal translation. Design for text length variation. Avoid abbreviations that may not translate.

---

## Accessibility

**Target sizes:**
- Web default: 48px
- Web compact: 32px (use sparingly)
- iOS / Android: 48px

**Keyboard:**
- `Tab` — moves focus to the button. If a tooltip is available, it appears on focus.
- `Enter` — activates the focused button region.
- `Esc` — dismisses the tooltip (if present).

**Name, Role, Value:**

*Main action (label region):*
- Inherits Button properties.
- Name: use visible label text. If the programmatic name differs from the visible label, it must include the visible label text (MAS 2.5.3).

*Supporting action (icon region):*
- Inherits Button properties.
- A11y name: provided via tooltip text. The tooltip name must be predictable and describe what the dropdown will offer (e.g., "Select pipeline stage to save to").

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
