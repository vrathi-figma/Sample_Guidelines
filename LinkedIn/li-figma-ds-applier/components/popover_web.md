# Popover (Web)

**Component:** `Popover (Web) SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to show contextual information or interactions that are hidden by default and revealed on demand.
- Content is highly flexible: text, entities, controls, forms, profiles, etc.
- **Web-only.** Use Bottom Sheet on native mobile.

**Historical names:** Web = Dropdown, Dropdown Menu, Contextual Dialog; Android = Menu; iOS = Popover Menu, Popovers.

---

## Popover vs. similar components

| Component | Contents | Trigger | Mobile |
|---|---|---|---|
| **Popover** | Anything | Click | Web only — use Bottom Sheet on mobile |
| **Menu** | Menu items only (no checkboxes, radios, buttons) | Click | Available (defaults to Bottom Sheet) |
| **Tooltip** | Static text only; no interactive elements | Hover or focus | N/A |
| **Modal / Side Sheet** | Large, complex content | User action | N/A |

- Tooltips show supplementary info on hover/focus; they cannot receive focus or hold interactions. **Toggletip** no longer exists — its behavior is merged into Popover.
- Do not nest Popovers — one Popover cannot open within another.

---

## Anatomy

| Slot | Rule |
|---|---|
| **Container (A)** | Free-floating or with a corner pointer. 12 position variants. |
| **Close Button (B)** | Optional. If hidden, another exit action (Cancel, Done) must be present. |
| **Content (C)** | Anything. |

---

## Position

12 positions relative to the trigger. **Bottom centered is the default.**

- Top centered, Top-left, Top-right
- Bottom centered (default), Bottom-left, Bottom-right
- Left centered, Left-bottom, Left-top
- Right centered, Right-bottom, Right-top

Popover **flips** automatically when near the edge of the page.

---

## Sizing

**Width:** Set based on content or use a fixed width. Recommended surface dimension tokens: 256, 320, 384. Avoid excessive width that requires horizontal eye movement.

**Height:** Hug content or fixed, with scrolling enabled when height reaches the window edge. Avoid popovers that require excessive scrolling — consider alternatives for heavy content.

---

## Best practices

**Be lightweight:**
- **Do:** Keep Popovers lightweight. Use them for small, focused content like a quick form, profile preview, or filter options.
- **Don't:** Design large Popovers with overwhelming amounts of content. For large or complex content, use a Modal or Side Sheet instead.

**Avoid nesting:**
- **Don't:** Open a Popover inside another Popover. One Popover cannot be nested or opened within another — opening a new Popover will close the currently open one.

---

## Content design

- **Do:** Add secondary information that expands on an existing topic without duplicating primary content.
- **Don't:** Hide information that is necessary for the user to understand the interface — if understanding the UI depends on it, put it inline instead.

---

## Interaction

**Trigger:** Click on a button or other control.

**Dismissal:**
- Click the Close button
- Internal action (e.g., Cancel, Done)
- Click the trigger again
- Press ESC
- Click outside the Popover
- Open a new dialog

---

## Accessibility

**Target size:** Close button = compact 32. Other controls in content area = default target size unless otherwise required.

**Keyboard:**

Two explicit variants: **modal** and **non-modal**. Modality is a design decision — chosen based on intent, not by the presence of interactive elements. Align with engineering; consult the Design System team if needed.

*Modal dialog:*
- `Tab` — cycles through interactive elements in the content area, then the Close button
- `ESC` — exits the Popover at any time
- Focus is **trapped** while open

*Non-modal dialog:*
- On open, focus may remain on the trigger OR land on the first focusable element inside
- Focus is **not trapped** — users can Tab to elements outside the dialog

**Name, Role, Value:**

*Popover:*
- Role: `Dialog`
- A11y Label: name derived from the button that triggered the Popover

*Dismiss button:*
- Role: `Button`
- A11y Label: "Dismiss"

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes. Any customizations in the content area must also meet MAS requirements.
