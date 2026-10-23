# Switch

**Component:** `Switch SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use for a binary on/off setting that takes effect immediately — no submit button needed.
- Use for persistent settings that the user controls independently (e.g. notifications, feature toggles).
- The setting must be self-contained; the Switch alone communicates the full action.

**Do not use when:**
- The change requires a separate confirmation step — use Checkbox paired with a Submit button instead.
- The choice is one of several mutually exclusive options — use Radio instead.

---

## Best practices

- **Max width ~500px recommended (600px hard limit).** It's recommended that the component be set no greater than 500px to ensure the visual connection between label and switch is maintained. There is no minimum width, but a default of 520 is recommended where possible.
- **Never require an extra button.** If a submit action is needed, switch to Checkbox.
- **Use for binary and immediate actions.** Don't use a Switch if the user will have to do something else or go somewhere after — if any extra step is required for changes to be effective, use a Checkbox and corresponding button in place of a Switch.
- **Avoid hiding "On" and "Off" labels.** Avoid hiding these default labels whenever possible in order to maintain consistency. When absolutely necessary: (1) maintain consistency — labels should be hidden in both on and off positions of the Switch, (2) avoid flipping the order of the value or using double negatives, as this can create confusion. In languages read right to left, a switch to the left is off (false); a switch to the right is on (true).
- **LTR layout:** Left position = Off, Right position = On. This directionality is intentional and consistent.

---

## Content rules

- Label: noun phrase, sentence case. No verbs, no questions.
  - Correct: "Email notifications"
  - Incorrect: "Enable email notifications?" / "Turn on email notifications"
- Keep labels concise — the Switch communicates the binary action; the label names what's being toggled.

---

## Internationalization

- **RTL:** Switch flips direction. On/Off position logic mirrors accordingly.

---

## Accessibility

**Keyboard:**
- `Tab` — moves focus to the Switch
- `Enter` / `Space` — toggles the Switch

**Name, Role, Value:**
- Role: `switch`
- Value: `"On"` / `"Off"` — must be communicated programmatically (via `aria-checked`) even if the On/Off label is not visually displayed.
- a11y label: visible label text

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
