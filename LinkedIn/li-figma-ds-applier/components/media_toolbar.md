# Media Player Toolbar

**Component:** `Video Control Toolbar`, `Document Control Toolbar`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Controls for interacting with video players or document viewers.
- Flexible template; customize with Media Buttons, Scrubber, Pagination, and Timestamps based on product needs.

---

## Toolbar types

| Type | Use case | Controls |
|---|---|---|
| **Video Toolbar** | Video/audio players. Appears as an overlay at the bottom. | Autoplay, Playback Speed, Closed Captions, Volume, Fullscreen, Scrubber (always with timestamp) |
| **Document Toolbar** | Document viewers (PDFs, presentations). Persistent UI. | Fullscreen, Zoom In/Zoom Out (fullscreen only), Pagination (navigation + location indicator) |

---

## Anatomy

| Slot | Rule |
|---|---|
| **Media Buttons (A)** | Ghost icon buttons for toggling playback states. |
| **Scrubber / Pagination (B)** | Video: scrubber with time indicator. Document: pagination with prev/next controls. |
| **Container (C)** | Transparent container housing all controls; sits on top of the media player container. |

---

## Best practices

**Clear and intuitive icons:**
- **Do:** Use recognizable, universally understood icons for video controls (play/pause, volume, closed captions, fullscreen). Include tooltips on hover to provide additional clarity.
- **Don't:** Use custom or non-standard icons — users should be able to identify control functions at a glance without needing to guess.

**Minimize distractions:**
- **Do:** Keep the toolbar concise. Only include controls that are directly relevant to the media experience.
- **Don't:** Add unnecessary elements to the toolbar — extra controls increase cognitive load and distract from the media content.

**Visual feedback:**
- **Do:** Provide clear visual feedback when a control is activated (e.g., icon state change, highlight).

- Default layout: horizontal overlay at the bottom of the video player.
- Scales from min width 320px up to 400% zoom without reflowing controls.

---

## Accessibility

**Target size:** Refer to Media Button and Ghost Button guidelines.

**Keyboard:**
- `Tab` — moves focus between interactive elements (non-disabled only)
- `Space` / `Enter` — activates the focused button
- `←` / `→` — changes scrubber/seekbar value
- `↑` / `↓` — changes volume slider value

**Name, Role, Value:**

*Video Toolbar:*
- **Media buttons:** Role: `Button`; A11y label must always be defined and predictable based on the icon; pressed state programmatically indicated separately.
- **Scrubber:** Role: `Slider`; refer to Media Scrubber guidelines.

*Document Toolbar:*
- **Pagination buttons:** Role: `Button`; A11y label: "Previous", "Next"
- **Page selector:** Refer to Select component guidelines.
