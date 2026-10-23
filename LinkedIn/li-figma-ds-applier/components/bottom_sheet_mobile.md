# Bottom Sheet (Mobile)

**Component:** `Bottom Sheet (Mobile) SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to surface contextual content or actions in a non-fullscreen overlay on mobile (iOS/Android).
- **Web equivalent:** Use Modal (web) or Popover (web) — Bottom Sheet is not available for web.
- Menu defaults to Bottom Sheet on native mobile. Only override to Menu with careful consideration.

---

## Anatomy

| Slot | Rule |
|---|---|
| **Grip (A)** | Drag handle — visual cue for swipe-to-dismiss. Tap target is 32px. |
| **Close Button (B)** | Required when the sheet cannot be dragged to dismiss. |
| **Header (C)** | Optional. Provides context or a title for the sheet. |
| **Content (D)** | Free-form — can contain any components. Follow each component's own rules. |
| **Scrim (E)** | Always include except for persistent bottom sheets. |

---

## Height

| Configuration | When to use |
|---|---|
| **Hug content** | Content is short and predictable |
| **Half-height** | Medium content; user can expand |
| **Full-height** | Long or complex content |

Maximum height = screen height. Height is content-driven, not fixed.

---

## Behavior

**Triggers:** User-initiated (tap a trigger) or system-initiated.

**Dismissal:**
- Swipe down or tap scrim to dismiss.
- If swipe-to-dismiss is disabled, a Close button must be present.

**Persistent bottom sheets** do not have a scrim and cannot be dismissed — they remain visible as part of the layout.

**Include a Close Button:** Bottom sheets can be dismissed by swiping or tapping out of the panel, but not all users are aware of this. Always include a close button so users know they can close and control the sheet.

**Do:** Include a visible close or collapse button in the header.
**Don't:** Rely solely on swipe-to-dismiss without a visible close button — users on some devices or in some contexts may not discover swipe.

**Avoid overlaying Bottom Sheets:** Do not open a Bottom Sheet on top of another Bottom Sheet. If one is needed while a Bottom Sheet is already active, consider a Fullscreen alternative (see iOS HIG).

**Don't:** Stack multiple bottom sheets on top of each other.

---

## Platform

| Platform | Use Bottom Sheet |
|---|---|
| iOS | Yes |
| Android | Yes |
| Web | No — use Modal or Popover |

---

## Accessibility

**Target size:** Grip tap target is 32px. Avoid placing interactive elements directly below the grip bar — they may fall within the tap target area. All other controls inherit from their respective component specs.

**Keyboard:**
- Focus moves into the bottom sheet as soon as it appears.
- All interactive elements receive focus in sequential order.
- Focus stays trapped within the bottom sheet until it dismisses. [MAS 2.4.3]

**Name, Role, Value:**

*Close button:*
- Role: `Button`
- A11y label: "Close"

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
