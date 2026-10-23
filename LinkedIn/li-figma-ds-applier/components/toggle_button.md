# Toggle Button

**Component:** `Toggle Button SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use inside a Rich Text Editor (RTE) toolbar to let users switch a formatting option on or off (e.g. bold, italic, list).
- Not a general-purpose toggle — this component is scoped to RTE contexts. For standalone binary settings, use Switch.

---

## Anatomy

| Slot | Rule |
|---|---|
| **Icon** | Required. Represents the formatting action. |
| **Container** | Always present, including in default/unchecked state. |

---

## Spacing

- Minimum **8px horizontal gap** between adjacent toggle buttons.
- Visual size: 32×32px. Touch target: 32×48px (default) or 32×32px (compact mode).
- Compact mode reduces touch target height to 32px; horizontal spacing between buttons is unchanged.

---

## Best practices

**Enough space between buttons:**

Toggle buttons have a min 32×48px touch target but the actual visual is 32×32px. Make sure there is at least 8px of horizontal space between each button.

**Do:** Maintain at least 8px gap between adjacent toggle buttons in the toolbar.
**Don't:** Pack toggle buttons with no gap — they become hard to distinguish and tap accurately.

---

**Avoid too many toggle buttons.** Avoid cluttering the editor with too many toggle buttons. Prioritize the most commonly used formatting options and provide additional options in a secondary menu if needed.

**Keyboard shortcuts required.** All toggle buttons in an RTE must be operable via keyboard shortcuts — not just mouse/tap.

---

## States

**Unchecked:** Enabled / Hover (Web only) / Active / Disabled

**Checked (Pressed):** Pressed / Pressed Hover (Web only) / Pressed Active / Pressed Disabled

Both states show a Tooltip on hover.

---

## Accessibility

**Target size:**
- Default: 48px touch target
- Compact: 32px touch target (use when space constraints require it)

**Keyboard:**
- `Tab` — moves focus to the toggle button or group of buttons
- `Space` / `Enter` — activates the focused button
- `←` / `→` — moves sub-focus between toggle buttons within a group

**Focus indicator:** Must be visible and unobscured. Appearance may differ by browser or device settings.

**Name, Role, Value:**
- Role: `button`
- a11y label: Must always be defined. Should be predictable based on the icon. Include contextual info if needed (e.g. "Bold", "Italic").
- State: The "pressed" state is communicated programmatically (`aria-pressed`) separately from the label.

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
- Disabled state is exempt from contrast requirements — some users may not perceive a disabled Toggle Button at all.
