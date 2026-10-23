# Reorder List

**Component:** `Reorder List SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- When users need to manually sort or reorder a list of items.
- Provides both drag-and-drop (pointer) and move mode (keyboard/accessibility) interaction patterns.

---

## Anatomy

| Slot | Rule |
|---|---|
| **Container (A)** | Wraps the full reorder list. |
| **Reorder Handle (B)** | Drag handle; the only interactive element for initiating reorder. |
| **List Items (C)** | Individual items in the list. |
| **Title (D)** | Item label; may be a link. |
| **Divider (E)** | Separates list items. |
| **Move Mode Dialog (F)** | Dialog that appears when move mode is activated via keyboard. |
| **Arrow Up (G)** | Moves item up one position in move mode. |
| **Contextual Action (H)** | Close (cancel) or Checkmark (confirm) in move mode. |
| **Arrow Down (I)** | Moves item down one position in move mode. |

---

## Interaction

### Drag and drop (pointer)
- Only the drag handle initiates reordering — no other part of the item is draggable.
- Long press: 500ms to begin drag on mobile.
- Item repositions when its center crosses the 50% midpoint of an adjacent item.
- No swapping — only one item moves at a time.
- Reorder is limited to lists (no grid reorder).

### Move mode (keyboard / accessibility)
- Activated by clicking the handle or pressing `Enter` / `Space` on it.
- Up/Down arrow buttons move the item one step at a time.
- Confirm (✓) commits the new position.
- Clicking outside the dialog cancels; `Esc` also cancels.

---

## Accessibility

**Target size:**
- Reorder Handle: 48px
- Title links: full text width
- Move mode buttons (Up/Down/Confirm/Cancel): 32px

**Keyboard:**
- `Tab` — moves focus through interactive elements; in move mode, Tab moves through the move mode buttons
- `Enter` / `Space` — activates the handle to enter move mode; confirms new position
- `↑` / `↓` — moves item one position up or down while in move mode
- `Page Up` / `Page Down` — moves item to top or bottom of list
- `Esc` — cancels move mode

**Focus management:**
- Focus is trapped inside the move mode dialog while active.
- On exit (confirm or cancel), focus returns to the drag handle.

**Name, Role, Value:**

| Element | Role | A11y Label |
|---|---|---|
| **Title** | `Link` | Visible text |
| **Handle** | `Button` | "Press Enter to activate move mode, then use Up and Down arrow keys to change {item} position." |
| **Move Mode Dialog** | `Dialog` | `aria-live="polite"` |
| **Arrow Up** | `Button` | "Move {item} up one position" |
| **Contextual Action (Cancel)** | `Button` | "Close" |
| **Contextual Action (Confirm)** | `Button` | "Confirm" |
| **Arrow Down** | `Button` | "Move {item} down one position" |

**Live region announcements:**
- On move mode activation: *"{Item} at position, 4 of 7, is activated to be repositioned. Press up and down keys to change position, enter or space to confirm, Escape to cancel."*
- On move: *"{Item} is moved to position, _ of 7, press space or enter to confirm new position, escape to cancel."*
