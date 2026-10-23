# Horizontal Scrolling Action List (HSAL)

**Component:** `Horizontal Scrolling Action List SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Presenting actions in a limited horizontal space.
- Grouping similar components to enhance usability and clarity.
- Navigation elements, filter options, or action lists.

**Do NOT use when:**
- Actions are few enough to fit without scrolling.
- Actions are not closely related and don't benefit from grouping.
- Vertical space is more abundant than horizontal space.
- Presenting large datasets that progressively load.

---

## Best practices

**Use for related and grouped actions:**
- **Do:** Use HSAL for actions or options that are related and logically grouped. Use consistent styling for all elements within the list and provide clear visual feedback on element selection.
- **Don't:** Mix different component types within the same HSAL (e.g., don't combine plain buttons with filled/emphasized buttons and Pill Filter Rollups in the same list — it creates visual inconsistency).

**HSAL vs. Carousel:**
- **Do:** Use HSAL for sets of actions or options that need immediate user interaction (buttons, filters, quick actions) — users can view and interact with all choices by scrolling horizontally.
- **Don't:** Use a Carousel for action sets. Carousels are best for showcasing content (images, cards) with an emphasis on sequential visual presentation — they are not designed for interactive action selection.

---

## Anatomy

| Slot | Rule |
|---|---|
| **Container (A)** | Bounding box that holds list contents. |
| **List Items (B)** | Two or more identical components in a list. Supports: Buttons, Pills, Tabs. |
| **Navigation Controls (C)** | Web only. Gradient overlays or chevrons at start/end to indicate additional content. Keyboard focus NEVER lands on navigation controls. |

---

## List item types

| Type | When to use |
|---|---|
| **Buttons** | Each item is a distinct, actionable command. For filtering or triggering immediate actions. |
| **Pills** | Representing categories, tags, or selectable options. Good for filtering and tagging. |
| **Tabs** | Navigation between content sections. |

---

## Accessibility

**Target size:**
- Default: 48px
- Compact: 32px

**Keyboard:**

*Focus order:*
- Focus moves sequentially through all list items (same as a vertical list, even though items scroll horizontally).
- Each list item may have multiple focusable elements — focus moves through each in order.
- Disabled elements cannot receive focus.
- When a list item receives focus on web, it must be fully visible; view scrolls to bring focused element into view.
- On mobile, the list automatically scrolls focused items into view.
- **Keyboard focus never lands on navigation controls** (chevrons/gradients).

*Operation:*
- `←` / `→` — scrolls the list without changing focus
- `Tab` — changes focus; if the focused item is out of view, scrolls it back into view
- `Enter` — triggers the focused item's action
- When HSAL has no value selected, sub-focus starts at first item without selecting it; any arrow key press immediately updates the selection.

**Name, Role, Value:**

- **HSAL container:** `List`
- **Each list item:** `List Item`
- Screen readers should identify both the item's position in the list and the total number of list items.
- If a page has multiple HSALs, product teams must append all a11y labels with contextual information to disambiguate.
