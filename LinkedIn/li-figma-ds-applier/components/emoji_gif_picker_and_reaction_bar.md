# Emoji/GIF Picker and Emoji Reaction Bar

**Component:** `Emoji and GIF Picker (Web) SDUI`, `Emoji and GIF Picker (Mobile) SDUI`, `Emoji Reaction Bar SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- When a member needs to insert an Emoji or GIF into a text area (messaging, commenting, etc.)
- To present groups of related content (similar emojis or GIF types) for navigation without leaving the core experience.

---

## Anatomy

### Emoji/GIF Picker

| Slot | Rule |
|---|---|
| **Search Input (A)** | Filters emojis or GIFs in real time. |
| **Button (B)** | Optional. Appears in picker header navigation. |
| **Close Button (C)** | Exits the picker. |
| **Content (D)** | Collection of selectable emoji or GIF items. |

### Emoji Reaction Bar

| Slot | Rule |
|---|---|
| **Buttons (A)** | Optional. Each button represents a selectable emoji reaction. |

---

## Best practices

**User control:**
- **Do:** Always include a close icon button in the picker header so members can exit the experience at any time.
- **Don't:** Launch the picker without a clear and accessible way to dismiss it.

**Clear and intuitive icons:**
- **Do:** Ensure the optional button in the picker header has a clear, unambiguous action icon that members can instantly recognize.
- **Don't:** Use custom or unclear icons for picker controls — members should be able to understand the action without guessing.

**Using the embedded menu:**
- **Do:** Use the optional header button as an anchor for a secondary action (e.g., skin tone picker, settings). Place it consistently to create a predictable experience across LinkedIn.
- **Don't:** Add header buttons that duplicate functionality already accessible elsewhere in the picker.

---

## Platform behavior

- **Web:** Picker appears as a popover-style overlay. Skin tone picker uses a Menu Item list.
- **Mobile:** Emoji Picker appears inline with the keyboard context. Emoji Reaction Bar on mobile uses a Bottom Sheet.
- **Mobile Expanded:** Full-screen picker available for expanded emoji browsing.

---

## Accessibility

**Target size:** All interactive controls (Close button, optional buttons, Search Input) = 48px minimum on both web and mobile.

**Keyboard:**
- `Tab` — moves focus between interactive elements
- `Enter` — activates the focused interactive element
- `ESC` — dismisses the Emoji/GIF Picker or Emoji Reaction Bar when in focus

**Focus order:**
- **Emoji/GIF Picker:** Focus moves across the header left to right, then through all elements in sequential order. Focus stays within the picker until it is dismissed or the user clicks outside.
- **Emoji Reaction Bar (web):** Focus moves across elements left to right sequentially. Focus stays within until dismissed or clicked outside.
- **Emoji Reaction Bar (mobile):** Focus moves into the Bottom Sheet as soon as it appears. All interactive elements receive focus in sequential order. Focus stays within the Bottom Sheet until it dismisses. [MAS 2.4.3]

**Name, Role, Value:**

This component uses inner components that carry their own NRV requirements. Refer to accessibility guidance for:
- Search Input
- Button
- Bottom Sheet
- Menu Item
