# Radio

**Component:** `Radio SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to let a user select exactly one option from a predefined group.
- Always use in a group — minimum 2 options. Never use a single Radio in isolation.
- Use in forms and settings where the user must commit to one choice.

**Do not use when:**
- Multiple selections are needed — use Checkbox instead.
- The choice is a simple binary on/off with immediate effect — use Switch instead.

**Single option choice:**

**Do:** Use Radio when only one answer is valid — e.g. "Will you be attending the party? Yes / No / Maybe."
**Don't:** Use Radio when multiple answers could be correct — e.g. "Which fruits do you enjoy?" (should be Checkbox).

**Switch vs Radio:**

**Do:** Use Switch when there are only two options that represent a binary true/false or on/off state — e.g. "Autoplay videos that appear on LinkedIn" (one toggle, immediate effect).
**Don't:** Use Radio for a simple binary on/off — Switch is the right component.

**Keep it simple:**

**Do:** Keep radio options short and their context focused. A simple billing cycle choice (Monthly / Annual) with a supporting summary is enough.
**Don't:** Overload a Radio group with complex multi-column layouts, extensive helper text per option, or decisions that require a lot of context — if that much explanation is needed, reconsider the design.

---

## Types

| Type | Layout |
|---|---|
| **Default** | Label appears to the right of the control |
| **Flipped** | Label appears to the left of the control |

---

## Radio group behavior

- **Pre-select a default** when a sensible default exists. Avoid presenting a radio group with no selection.
- Selecting a new option automatically deselects the previously selected one — no multi-select is possible.
- Validation errors: display error state on the affected radio(s) and pair with an Inline Feedback component at the bottom of the group.

---

## Content rules

- Write radio selections in sentence case as a single word or short phrase that clearly distinguishes each option.
- Use bullets for items where the order isn't vital. Use numbers if order is important.
- Organize selections clearly — by number, chronology, subject, or alphabetically.
- Use consistent phrase construction — all nouns or all verbs, so selections read similarly.
- Avoid overlapping or ambiguous labels within the same group.

**Do:** "Who can see when you are on LinkedIn: Your connections only / All LinkedIn members / No one" — short, parallel labels.
**Don't:** Use the same group with verbose helper text per option that spills into paragraph-length explanations — readers lose the comparison.

**Do:** "Which outdoor activity do you prefer? Hiking / Running / Surfing" — all present-participle form.
**Don't:** "Hiking / Running / Surf" — inconsistent grammatical form.

---

## Accessibility

**Target size:** Meets minimum touch/click target requirements.

**Keyboard — Web:**
- The entire radio group is a single tab stop.
- `Tab` — moves focus to the checked radio (or the first radio if none is checked).
- `↓` / `→` — moves to next option and auto-selects it.
- `↑` / `←` — moves to previous option and auto-selects it.
- `Space` — mobile only; activates the focused radio.

**Name, Role, Value:**
- Role: `radio`
- a11y label: visible label text
- Helper text (if present): associated via `aria-description`
- Group label: wrap the group in a `<fieldset>` with a `<legend>` (or equivalent ARIA grouping)

**Color & Contrast:**
- Radio circle indicator: minimum 3:1 contrast ratio.
- Label and helper text: minimum 4.5:1 contrast ratio.
- All default colors meet requirements for light and dark modes.
