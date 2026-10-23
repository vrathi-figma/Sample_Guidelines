# Timepicker

**Component:** `Timepicker SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to let users select or enter a time value in a form.
- Currently available for **Web only** — mobile touch target specs are not defined.

---

## Types

| Type | Description |
|---|---|
| **Single** | One time input field + optional Clock Button that opens the Timepicker View (Menu). |
| **Range** | Separate start/end time inputs, each with their own Clock Button — four total tab stops. |

---

## Anatomy

The Timepicker is composed of two parts:

**Timepicker Input:**
- A Text Input where users can type a time value directly.
- An optional Clock Button (icon button) that opens the Timepicker View.

**Timepicker View:**
- A Menu component showing selectable time options.
- Opens when the text input is focused (on some implementations) or when the Clock Button is pressed.

---

## Behavior

- **Web:** Users can type directly into the text input OR use the Clock Button to open the Menu and select a time.
- **Mobile (native):** The entire Timepicker Input acts as a button — typing directly is disabled. Interaction opens a native time picker.
- The Timepicker View is a Menu — it inherits all Menu component behavior (close on selection, close on click outside).

---

## Accessibility

**Target sizes:**
- Timepicker Input: inherits Text Input target sizes
- Clock Button: 32px (small), 48px (large) — same as Icon Button
- Timepicker View: inherits Menu Item target sizes

**Focus indicators:** Each focusable element (input, clock button, menu items) must have a visible, unobscured focus indicator.

**Keyboard:**

*Timepicker Input:*
- `Tab` (1st stop) — focuses the text input
- Character keys — type into the text input
- `Tab` (2nd stop) — focuses the Clock Button
- `Space` / `Enter` on Clock Button — opens or re-invokes the Timepicker View

*Timepicker View:*
- `Tab` on input — in some implementations, opens the View
- `↓` — moves focus to first (then subsequent) items in the View
- `Enter` — selects the highlighted time; closes the View; focus returns to text input
- `Tab` on Clock Button — closes the View (focus highlight not preserved on re-open)
- `Space` / `Enter` on Clock Button (focused) — re-invokes the View

**Name, Role, Value:**

*Timepicker Input (web):*
- Role: `Textbox`
- Name: use visible label text
- Hint: programmatically associated (e.g., placeholder "5:30 PM")
- Helper text: programmatically linked (e.g., `aria-description`)

*Timepicker Input (mobile):*
- Role: `Button`
- Name: `"Timepicker View"`

*Clock Button:*
- Role: `Button`
- Name: `"Timepicker View"`

*Timepicker View:*
- Role: `Menu`
- No visible label; no a11y label needed

*Time Items:*
- Role: `menuitem` (must be within a `role="menu"` container)
- Name: use visible text (e.g., "6:00 PM")

**Color & Contrast:**
- Inherits from Text Input and Button components — all meet minimum contrast requirements.
