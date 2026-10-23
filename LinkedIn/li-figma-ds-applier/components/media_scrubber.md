# Media Scrubber

**Component:** `Media Scrubber SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Provides intuitive control over media playback position.
- Lets users seek to specific moments, review key sections, or skip/revisit parts.
- Changes must apply in real time — do not use when there is a delay in user feedback.

---

## Best practices

**Real-time adjustments:**
- **Do:** Use scrubbers for changes that apply immediately — users should be able to quickly switch between values and see results reflected instantly.
- **Don't:** Use a scrubber when the change requires a delay in user feedback. Deferred updates break the expected direct-manipulation experience.

**Be wary of large ranges:**
- **Do:** Keep the value range as narrow as the task requires.
- **Don't:** Design a scrubber with a very wide precise range (e.g., 0–500) without an alternative input method — users must be exact with thumb or cursor placement, which raises issues for users with fine motor control difficulties.

---

## Anatomy

| Slot | Rule |
|---|---|
| **Fill (A)** | Shows the range covered by the selected value. Must contrast sufficiently with parent container background. |
| **Handle (B)** | Optional. Draggable/tappable element indicating current playback position. Enlarges from 12px to 16px on interaction (with shadow), except on Android native. |
| **Buffering Indicator (C)** | Optional. Communicates that content is actively loading. |
| **Track (D)** | Full range of selectable values. |
| **Timestamp (E)** | Optional. Time duration text to the right of the scrubber. |

---

## States

- **Enabled**
- **Hover** (web only)
- **Active**

---

## Interaction

- Users drag the handle or click directly on the track to select a value.
- Click-on-track is especially useful for pointer-based interactions (no drag needed).

---

## Accessibility

**Target size:**
- Default: 48px
- Compact: 32px (use sparingly)

**Keyboard:**
- `Tab` — moves focus to the handle
- `←` / `→` — changes the slider value
- `Shift` + arrow — changes value by a larger increment

**Name, Role, Value:**
- Scrubbers must declare their role and current value for assistive technology.
- A11y label must be present even when there is no visible label.

| Slot | Role | A11y Label |
|---|---|---|
| Handle (minimum) | `Slider` | "Minimum slider" |
| Handle (maximum) | `Slider` | "Maximum slider" |
