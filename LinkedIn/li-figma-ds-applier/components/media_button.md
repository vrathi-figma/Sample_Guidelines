# Media Button

**Component:** `Media Button SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Within a Media Toolbar to control playback.
- Provides nuanced binary (toggle) controls, similar to toggle buttons.
- Typically arranged in various ways within the Media Toolbar.

---

## Button types

| Type | Description |
|---|---|
| **Play/Pause** | Toggles between play (start from current position) and pause (halt at current point). Icon switches between Play and Pause. |
| **Fullscreen / Normal Screen** | Toggles between full-screen and standard viewing modes. |
| **Closed Captions (On/Off)** | Toggles caption text display on/off. |
| **Volume** | Controls audio: Mute/Unmute + vertical slider. Only supports Mute, Unmute, and Volume High icons. |
| **Playback Speed** | Ghost Button showing current speed (e.g., "1x"). Opens Popover with Menu Items for speed options: 0.5x, 0.75x, 1x, 1.25x, 1.5x, 1.75x, 2x. |
| **Action (Skip Forward/Back)** | Skip by a predefined interval (e.g., 5s, 10s, 30s). |
| **Overlay** | Used when a button is placed on top of a media element (e.g., prev/next in a carousel). |

---

## Best practices

**Enough space:**
- **Do:** Maintain at least 8px of horizontal space between each Media Button control. Default touch target is 24×48px.
- **Don't:** Pack controls without spacing — accidental taps on the wrong control create frustration, especially on mobile. If using compact mode (32px height), apply it consistently to each control individually.

**Avoid ambiguous or custom icons:**
- **Do:** Use industry-standard, universally recognized icons (play, pause, volume, skip) that users can identify instantly. Add tooltips on hover for additional clarity.
- **Don't:** Use custom or unclear icons for media controls. Screen readers need clear labels; non-standard icons create accessibility barriers, inconsistency, and user confusion.

---

## Accessibility

**Target size:**
- Default: 48px
- Compact: 32px (use when space constraints require it)

**Keyboard:**
- `Tab` — moves focus to (non-disabled) button
- `Space` / `Enter` — activates the button
- `←` / `→` — moves sub-focus between toggle buttons in a group

**Name, Role, Value:**

- **Role:** `Button`
- **A11y Label:** Must always be defined and predictable based on the icon. Include contextual info if needed.
- **State:** The "pressed" state is programmatically indicated separately from the label.

**Color & Contrast:**
- All default colors meet or exceed minimum contrast requirements for light and dark modes.
- Disabled buttons are not required to meet contrast minimums — some users may not be able to perceive them.
