# Slider

**Components:** `Slider Continuous SDUI`, `Slider Segmented SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to select a number within a defined range — settings, preferences, or value entry.
- Only when changes apply in real time. Do not use if the change requires a delay in user feedback.
- For large ranges where precision is critical, or in limited space: consider Text Input, Select, or Pills instead.

---

## Best practices

**Real-time adjustments:**
- **Do:** Use sliders for settings that apply immediately — volume, brightness, price range. Users should be able to switch between values and see results reflected instantly.
- **Don't:** Use a slider when the change requires a delay in user feedback — the direct manipulation model breaks down.

**Be wary of large ranges:**
- **Do:** Use a Segmented Slider (which snaps to preset points) when precision within a wide range is required — it's much easier to hit the right value.
- **Don't:** Use a continuous slider for a very wide precise range (e.g., 0–500) without alternative input — users with limited fine motor control will struggle to land on exact values.

**Consider other options:**
- **Do:** When there are limited predefined options or limited space, use Select menus or Pills. When users need exact value entry, use a Text Input paired with the slider.
- **Don't:** Force a slider when the number of valid values is small and could be displayed as discrete options — simpler inputs serve users better.

---

## Types

| Type | When to use |
|---|---|
| **Continuous** | User can drag freely to any value in the range |
| **Segmented** | Snaps to preset stop points — use when precision matters or range is large |

- Avoid too many stop indicators on a Segmented slider — it becomes visually crowded and hard to adjust.
- If range is large (e.g. 0–500) and precision is needed, Segmented is preferable to Continuous.

---

## Anatomy

| Slot | Description |
|---|---|
| **Label (A)** | Optional. Describes the input. |
| **Icon (B)** | Optional. Single or double icon on either side — reinforces purpose or min/max values. |
| **Value (C)** | Optional. Min and max value labels shown above/below or to the side of the track. |
| **Handle (D)** | Required. Draggable control that represents the selected position on the track. |
| **Fill (E)** | Required. Shows the range covered by the current value. Also ensures contrast with the container background. |
| **Track (F)** | Required. Represents the full available range. |
| **Tooltip (G)** | Optional. Appears on hover, active, and focus states — displays the current value in real time as handle moves. |
| **Stop Indicator (H)** | Segmented only. Marks the predefined values along the track. |

**Faint track constraint:** A faint track may only be used if:
- At least one visible label or icon conveys the proportional or absolute current value, **or**
- The slider spans the full width of its container (start/end points are inferrable).

---

## Behavior

- Users can drag the handle **or** click directly on the track to select a value.
- Tooltip shows current value above the handle during hover, active state, or keyboard focus.
- Handle enlarges from 12px to 16px and gains a shadow on interaction (all platforms except Android native).

---

## States

- **Enabled** — default
- **Hover** — web only; tooltip appears
- **Active** — during drag/interaction; tooltip appears
- **Disabled** — not interactive

---

## Sizes / Target sizes

| Context | Handle target size |
|---|---|
| iOS / Android | 48px (default) |
| Web compact | 32px (use sparingly) |

---

## Accessibility

**Keyboard:**
- `Tab` — moves focus to the handle (tab order: slider → number input if present)
- `←` / `→` — changes the slider value by one step
- `Shift` + `←` / `→` — changes value by a larger increment (e.g., 10 instead of 1)
- Users can also directly enter a value in a paired text input if one is present

**Name, Role, Value:**
- Role: `Slider`
- Name: use the visible label
- Current value: numerical value (e.g., `"25.2"`)
- Value text: where units are needed, provide a string with the value and units (e.g., `"25.2 degrees Celsius"`)
- Minimum value: the minimum allowed value
- Maximum value: the maximum allowed value
- Orientation: `Horizontal`

**Color & Contrast:**
- Fill and track are distinguishable by thickness (not color alone) — satisfies contrast through shape.
- All other default colors meet minimum contrast requirements for light and dark modes.
