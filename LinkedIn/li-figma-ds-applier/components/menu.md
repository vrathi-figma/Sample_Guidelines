# Menu

**Component:** `Menu SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to display a list of scannable actions or options triggered by a user interaction.
- Triggered from buttons, icon buttons, input fields, or other interactive elements.
- **On native mobile, Menu defaults to Bottom Sheet.** Only override to Menu with careful consideration — Bottom Sheet is preferred for complex/nested menus, many items, or selection states.

**Historical names:** Web = Dropdown / Dropdown Menu; Android = Menu; iOS = Popover Menu / Popover.

---

## Menu vs. Popover

| Component | Contents | Mobile |
|---|---|---|
| **Menu** | Menu items only — no checkboxes, radios, or buttons | Available (defaults to Bottom Sheet) |
| **Popover** | Any content | Not available on native mobile — use Bottom Sheet |

---

## Anatomy

| Slot | Rule |
|---|---|
| **Menu Container (A)** | Contextual dialog that wraps all items |
| **Menu Item (B)** | Label (required); Icon (optional); Helper Text (optional); Selection Indicator (web only). Android: text-only recommended — use Bottom Sheet if icons or helper text needed. |
| **Heading (C)** | Optional. Category label to group related items. |
| **Divider (D)** | Optional. Use to separate sections within the menu. |

---

## Interaction types

| Type | Use | Trigger |
|---|---|---|
| **Action Menu** | Commands related to the trigger (e.g., on a card or table row) | Button or icon button |
| **Overflow Menu** | Secondary or less-used actions | Icon button |
| **Navigation Menu** | Navigate between views or sections | Link, icon, or persistent nav element |
| **Combobox / Typeahead** | Select from preset list or typed input | Text input or Select |
| **Split Button Menu** | Surface a quick default action + secondary options | Left side = action; right side (caret) = menu |
| **Pill Filter Rollup** | Multi-select from a list of filters | Pill Filter Rollup |
| **Pill Single Select** | Single-select from a list of filters with label update | Pill Single Select |

---

## Dismissal

Menus dismiss on any of the following:
- **Item select** — performs action and dismisses
- **Toggle** — press the trigger again
- **Click / tap / tab outside** the menu
- **ESC key**

---

## Position

Menu appears relative to the trigger element and overlays content behind it. 12 placement positions are supported (top-left, top-right, bottom-centered, bottom-left, bottom-right, left-centered, right-centered, and variants). Position is set by the product team based on available viewport space.

---

## Best practices

**Max items:** No hard limit — aim for 5–7 max to reduce cognitive load (Miller's Law). Users can comfortably process and remember around 5–7 items without feeling overwhelmed. Beyond this range, it becomes challenging for users to quickly process and choose from options. A menu with too many items can appear visually cluttered and reduce readability and user engagement.

**Order:** Organize in a clear order — by steps, time frames, or others. For 10+ items, include category headers to help users find options faster and easier.

**Menu vs Popover:** Menus can be seen as a specially designed Popover with the purpose of displaying a list of actions. They share similar visuals and interactions, but Menus have a more focused use case. Menus can contain only menu items — no checkboxes, radios, or regular buttons. Popovers are just containers and can have anything. Additionally, Popover cannot be used in the native mobile experience — use Bottom Sheet in those cases.

---

## Accessibility

**Target size:** All menu items have a tap target of 48px.

**Keyboard:**
- Menu items receive focus in sequential order preserving meaning and operability.

**Name, Role, Value:**

*Menu Item:*
- Role: `Button`
- Name: use visible label text

*Menu container:*
- Role: `Menu`
- Visible label: No; A11y label: n/a

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
