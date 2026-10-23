# Text Input and Text Area

**Components:** `Text Input (iOS & Web) SDUI`, `Text Input (Android) SDUI`, `Text Area (iOS & Web) SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to collect free-form text in forms — names, emails, addresses, descriptions, messages.
- **Not** when the user can only choose from a predefined list — use Select, Radio, or Pills instead.

---

## Types

| Type | Use |
|---|---|
| **Text Input** | Single-line. Short, specific data: names, emails, URLs, phone numbers, short answers. Fixed height. |
| **Text Area** | Multi-line. Longer entries: paragraphs, comments, descriptions, messages. Default 3 rows; resizable by user. |

---

## Input types

Set the appropriate input type to enable autocomplete and the correct mobile keyboard:
- `text` — general-purpose
- `email` — shows `@` on mobile keyboard
- `tel` — shows number pad
- `password` — masks characters
- `date` — date formatting

---

## Anatomy

| Slot | Rule |
|---|---|
| **Label (A)** | Required. Describes what to enter. Wraps on overflow. |
| **Value (B)** | The user's input. In Text Input: single line, overflows horizontally. In Text Area: wraps within the field. |
| **Helper text (C)** | Optional. Instructions or tips. Replaced by error text in error state. |
| **Counter (D)** | Optional. Real-time character count (e.g. "15/200"). |
| **Contextual action (E)** | Optional. A complementary action inside the input (e.g. "Show password" toggle, datepicker trigger). |

---

## Sizes

| Size | Use |
|---|---|
| **Small (default)** | Compact UIs, dense layouts, logged-in experiences |
| **Large** | Low information density, spacious layouts |

---

## States

State changes are primarily reflected through border color:
- **Enabled** — default, awaiting interaction
- **Hover** — web only
- **Active/Pressed** — immediate response on click/tap
- **Focused/Typing** — cursor visible; value shown in real time
- **Disabled** — not interactive; visually distinct

---

## Error state

- Border color changes to error color **and** error text appears where helper text was.
- Error text **replaces** helper text — never shown simultaneously.
- **Trigger:** `onBlur` (when focus leaves the field) or on form submission. Never trigger on `onChange`.
- Error persists until the user corrects the input.

---

## Content rules

**Labels — for identifying, not instructing:**
- 1–3 words; sentence case; use nouns or noun phrases.
- Never use verbs. Use "First name" not "Enter first name".
- Never use the label slot for instructions — that's what helper text is for.

**Do:** "First name" / "Date file name" — short, clear noun phrase.
**Don't:** "Enter file name" / "Enter your real name" — verb phrases or instructions in the label.

---

**Helper text — for instructions, not labels:**
- For critical instructions or formatting constraints (e.g., "Passwords must contain at least 12 characters").
- Use sparingly — only when the label alone is insufficient. Use in a way that complements the label and other contextual cues.

**Do:** Brief helper text that adds value beyond the label.
**Don't:** Overly long helper text that dominates the field and increases cognitive load.

---

**Hint/Placeholder text — for non-critical information:**
- For non-critical suggestions (e.g., format examples like "name@email.com").
- Disappears when the user starts typing — never put critical information here.
- Never use hint text as a substitute for a label.

**Do:** Short, clear format hint (e.g. "username@company.com").
**Don't:** Put required instructions in hint text — users won't see them once they start typing.

---

**Error messages — clear and actionable:**
- Side with the user. Identify the problem and guide the fix.
- Error language should state the issue and offer practicalities — not just flag the error.

**Do:** "This value should be a valid email address." — identifies the problem and implies the fix.
**Don't:** Vague messages like "Invalid input" that don't explain what's wrong or how to fix it.

---

## Form layout best practices

- Stack form elements **vertically** to accommodate varied viewports and zoom levels.
- Group related fields with visible headings or `fieldset` labels.
- Use dividers to separate specialized groupings in complex forms.
- For long forms: use Inline Feedback after major sections; provide success confirmation text.

---

## Adaptability

- Labels and helper text **wrap** when content is long.
- Text Input value **overflows horizontally** — does not wrap; single row maintained.
- Text Area value **wraps** within the field. Users can scroll vertically or resize using the browser resize grip.
- **RTL:** Elements flip horizontally. Required asterisk moves to after the label: LTR `Label*` → RTL `*Label`. Character count fraction stays in the same numeral format (e.g., "0/200").

---

## Accessibility

**Target sizes** (label click also focuses input — helper/error text/counter not included):
- Web / iOS Small: 52px minimum
- Web / iOS Large: 70px minimum
- Android Small: 54px minimum
- Android Large: 64px minimum

**Keyboard:**
- `Tab` — moves focus to the Text Input; on focus, entire value is selected automatically (standard behavior)
- `←` / `→` — moves cursor within the value
- Character keys — insert at cursor position
- Text Input is a **single focusable element** — label, helper text, and counter are programmatically associated but not separately focusable
- Trailing button (if present) is a **separately focusable element**

**Focus indicator:** Must be visible and unobscured.

**Name, Role, Value:**

*Text Input:*
- Role: `Textbox`
- Type: `text` / `tel` / `number` / `email` / `password`
- Name: use the visible label. If purpose is inferred from context, include that context in the programmatic name (e.g., `"Postal Code for Mailing Address"`)
- Helper text: programmatically linked (e.g., `aria-description`)
- Character count: programmatically linked (concatenated into `aria-description`). Announced as "15 of 200" — not "15 slash 200"
- Hint/placeholder: programmatically associated but not reliably announced by screen readers — never put critical info here

*Trailing button:*
- Role: `button`
- Name: must be descriptive and predictable — include disambiguating context (e.g., `"Show password"`, `"Open datepicker, start date"`)

*Text Area:*
- Role: `Textbox` (multi-line)
- All other a11y attributes inherited from the single-line variant

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
- Disabled state is exempt from contrast minimums.
