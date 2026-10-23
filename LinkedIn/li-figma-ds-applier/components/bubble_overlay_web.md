# Bubble Overlay (Web)

**Component:** `Bubble Overlay SDUI`, `Detail Bubble Overlay SDUI`, `List Bubble Overlay SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to give users quick access to supplementary or secondary information without leaving the current page.
- Can expand into a Detail Bubble Overlay (rich content) or a List Bubble Overlay (persistent list, e.g., messaging inbox).

---

## Types

| Type | Trigger | Sizes | Use case |
|---|---|---|---|
| **Detail Bubble Overlay** | Explicit user action (click only — never hover/focus change) | Max, Mid, Min | Conversations, contextual detail panels |
| **List Bubble Overlay** | May appear by default or via user action | Max, Min | Persistent inbox lists (e.g., homepage messaging) |

---

## Anatomy

| Slot | Rule |
|---|---|
| **Heading (A)** | Required. Brief description of the bubble's purpose. |
| **Subheading (B)** | Optional. Clarifying detail for the heading. |
| **Container (C)** | Holds overlay elements; visually separates from the page. |
| **Overflow Menu (D)** | Optional. For secondary actions on the bubble. |
| **Action Button (E)** | Optional. For specific quick actions (e.g., start video call, star). |
| **Maximize/Minimize Button (F)** | Required. Toggles between sizes. List = max/min; Detail = max/mid. |
| **Close Button (G)** | Required. Detail Bubble Overlay closes via Close ("X") button. |
| **Entity Image (H)** | Optional. Circle or square entity image. |
| **Online Indicator (I)** | Optional. Indicates online/offline status. |
| **Divider (J)** | Required. Separates the sticky header from scrollable content. |
| **Content (K)** | Main content area. Can contain any components. |
| **Badge (L)** | Optional. Indicates new content. |

---

## Interaction

**Triggers:**
- Detail Bubble Overlay: Explicit user click only. Never trigger on hover, focus change, or text input.
- List Bubble Overlay: May be present by default or triggered by user interaction.

**User Control:** Regardless of the bubble size, each should include at least a close or collapsible icon button in the header. This gives users the flexibility to minimize or resize the bubble if they don't want to interact with too much of the inner content, ensuring a more adaptable experience.

**Do:** Always include a visible close/minimize control in the Bubble Overlay header.
**Don't:** Omit the close or collapse control — users have no way to dismiss the overlay.

**Managing Multiple Bubbles:** When multiple bubbles need to be on screen, additional bubble content should exist one at a time without overlapping. If a bubble reaches the screen's edge, reposition all other detachable overlays. If it's still too cluttered, dismiss the detachable bubble overlay.

**Don't:** Stack or overlap multiple bubble overlays — this creates a confusing, cluttered interface. Bubbles are independent of each other and have no built-in focus or dismiss button to collapse.

**Be Simple:** If the task within the bubble is complex or requires significant user focus, consider using a full-page instead.

**Switching sizes:**
- List Bubble: Click collapse icon or click anywhere on the header.
- Detail Bubble: Click maximize/minimize icon toggles max/mid; click header toggles min/non-min.

**Multiple bubbles:**
- When a new Detail Bubble opens at max size, minimize all existing ones first.
- If still cluttered, dismiss the rightmost Detail Bubble.

**Dismiss:**
- Close button (Detail Bubble) or collapse (List Bubble).
- If closing would discard changes, confirm with a Confirmation Dialog first.
- On close, return focus to the element that opened the bubble.

---

## Accessibility

**Target size:**
- Clickable header exception: header target size is 56. This applies to messaging-style designs where the header signals new content and is interactive.
- Detail Bubble header buttons (icon buttons): default 56×32.
- List Bubble header buttons: compact 32.
- Content area controls: must meet or exceed MAS 2.5.8.

**Keyboard:**
- Bubble Overlays are **non-modal dialogs** — focus is NOT trapped; users can interact with both the overlay and the page.
- On open, focus is set manually to the Bubble container.
- Sequential focus: header elements first, then content area.
- Keyboard shortcut: product teams are encouraged to provide a shortcut for quickly entering the bubble.
- `Tab` — move to next focusable element
- `ESC` — dismiss the bubble (mirrors Close button)
- Detail Bubble (Min): Focus set to header; header is operable for collapse/expand; then Close button.

**Name, Role, Value:**

*Bubble container:*
- Role: `Dialog`
- A11y Label: visible header text (heading + subheading)

*Buttons (icon buttons in header):*
- Role: `Button`
- A11y Labels: "More actions" / "Collapse" or "Expand" / "Minimize" or "Maximize" / "Close"
- Add contextual info to disambiguate (e.g., "More actions for your conversation with [Name]")

*Entity Title (when a link):*
- Role: `Link`
- A11y Label: visible heading + subheading combined

*Keyboard-only expand/collapse control (Detail Bubble):*
- Role: `Button`
- A11y Label: "Collapse" or "Expand"

*Badge:* Refer to Badge component guidance.

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
