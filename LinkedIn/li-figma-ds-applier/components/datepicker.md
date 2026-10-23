# Datepicker

**Component:** `Datepicker SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to let users select a date or date range in a form.
- Currently available for **Web only** — mobile touch target specs are not defined.

---

## Types

| Type | Description |
|---|---|
| **Single** | One date input field + Calendar Button that opens the Calendar View. |
| **Range** | Separate start/end date inputs — four total tab stops (start text → start calendar btn → end text → end calendar btn). |

---

## Anatomy

The Datepicker is composed of two parts:

**Calendar Button Input:**
- A Text Input where users can type a date directly.
- A Calendar Button (icon button) that opens the Calendar View.

**Calendar View:**
- A calendar grid showing selectable dates.
- Navigation controls for month/year traversal.
- "Go to Today" and "Cancel" actions.

---

## Behavior

- Users can type directly into the Text Input OR use the Calendar Button to open the Calendar View.
- **Mobile (native):** The entire input acts as a button — typing directly is disabled. Interaction opens the native date picker.
- Calendar View closes on date selection or click outside.

---

## Keyboard (Calendar View)

| Key | Action |
|---|---|
| `←` / `→` | Move focus between days |
| `↑` / `↓` | Move focus between weeks |
| `PgUp` / `PgDn` | Navigate months |
| `Alt + PgUp` / `Alt + PgDn` | Navigate years |
| `Enter` | Select focused date; close Calendar View |
| `Esc` | Exit Calendar View; return focus to Calendar Button |

---

## Accessibility

**Target sizes:**
- Text Input: inherits Text Input target sizes
- Calendar Button: 32px
- Date Cell: 40px minimum
- Other Calendar View buttons (Previous Month, Next Month, Go to Today, Cancel): 32px

**Name, Role, Value:**

*Text Input (web):*
- Role: `Textbox`
- Name: use visible label text

*Text Input (mobile):*
- Role: `Button`
- Name: `"Calendar View"`

*Calendar Button:*
- Role: `Button`
- Name: `"Calendar View"`

*Calendar Grid:*
- Role: `Grid`
- Name: `"[Month Year]"` (e.g., `"January 2024"`)
- Hint: day-of-week column headers

*Previous / Next Month buttons:*
- Role: `Button`
- Names: `"Previous Month"` / `"Next Month"`

*Date Cell:*
- Role: `Button`
- Name: `"[DD/MM/YYYY]"`
- Hint: `"Selected Date"` or `"Today's Date"` when applicable

*Go to Today:*
- Role: `Button`
- Name: use visible label text

*Cancel:*
- Role: `Button`
- Name: use visible label text

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
