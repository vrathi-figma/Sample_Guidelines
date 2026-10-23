# Tooltip (Web)

**Component:** `Tooltip (Web) SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to provide supplementary, non-essential information when a user hovers or focuses on a control.
- Tooltip content should expand and support an existing label — it must not duplicate it.
- If the information is necessary to understand how the interface works, do not hide it in a tooltip — surface it inline instead.

**Do not use for:**
- Interactive content — Tooltips cannot hold links, buttons, or other interactive elements. Use Popover instead.
- Mobile — Tooltip does not exist on mobile (no hover interaction). Replace with visible labels or inline text.

---

## Tooltip vs. Popover

| Component | Trigger | Interactive content | Dismissal |
|---|---|---|---|
| **Tooltip** | Hover or keyboard focus | No | On blur/mouseout |
| **Popover** | Press/click | Yes (or static) | Explicit dismiss |

Toggletip no longer exists as a separate component — its behavior has been merged into Popover.

---

## Sizes

| Size | Use |
|---|---|
| **Small** | Short, concise text — a single word, abbreviation, brief phrase. Ideal for icon or button labels. |
| **Large** | Short sentences, brief instructions, formatted content, or contextual explanations. |

- Keep tooltips lightweight. Avoid huge tooltips with overwhelming content.
- Prefer Small whenever a word or two suffices.
- Reserve Large for cases where additional context is genuinely needed.

**Be simple and concise:**

**Do:** Small tooltip with a single concise phrase — e.g. "This is meant to communicate."
**Don't:** Large tooltip that displays an overwhelming paragraph of content — if you need that much text, it belongs inline or in a Popover.

**Avoid overuse of large tooltips:** While large tooltips can provide more information, overusing them leads to a cluttered interface. Reserve Large tooltips for cases where additional context is genuinely needed and choose the tooltip size that balances providing enough information with maintaining a clean and efficient UI.

---

## Anatomy

| Slot | Description |
|---|---|
| **Container** | Wraps tooltip content |
| **Text** | Tooltip content — should be concise |

---

## Behavior

- Appears on hover or keyboard focus over the trigger element.
- Disappears when cursor or focus moves away.
- The tooltip itself does not receive focus and cannot hold interactive elements.

---

## Position

Default placement: **bottom centered**. Configurable to any of 12 positions:

Top: centered, left-aligned, right-aligned
Bottom: centered (default), left-aligned, right-aligned
Left: centered, bottom-aligned, top-aligned
Right: centered, bottom-aligned, top-aligned

**Viewport clipping avoidance:** Tooltip automatically flips or adjusts position to stay within the visible viewport. For example, a tooltip above a trigger near the top of the screen will flip to appear below.

---

## Adaptability

- Tooltip width and height are driven by content.
- Long content wraps to the next line — no truncation.

---

## Accessibility

**Target size:** N/A — Tooltip does not receive focus and holds no interactive elements.

**Keyboard:** Tooltip does not receive focus. It appears when the trigger element receives keyboard focus.

**Name, Role, Value:**
- Role: N/A (not an interactive element)
- The tooltip content is programmatically linked to its trigger as a description or hint (e.g. `aria-description` or `UIAccessibilityHint`).

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
