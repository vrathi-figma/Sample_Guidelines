# Pills

**Components:** `Pill Choice SDUI`, `Pill Toggle SDUI`, `Pill Input SDUI`, `Pill Action SDUI`, `Pill Filter Rollup SDUI`, `Pill Single Select SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

Pills (also called Chips) are compact, interactive elements for filtering, selecting, sorting, inputting, or triggering actions. Choose the right pill type based on the interaction pattern.

---

## Types

### Choice Pill
- **Use:** Single selection from a group (like a Radio Button, but more compact).
- **Always appear in a group** — never a single choice pill.
- Selecting one auto-deselects all others. Not for multi-select.
- **When to use instead of Single Select Pill:** When there are 2–5 visible options and you want all choices immediately visible.
- **Don't allow label wrapping:** Choice Pill labels must stay on a single line. If a label wraps, it indicates the label is too long — shorten it or reconsider the component choice.

### Toggle Pill
- **Use:** Multi-select filtering (like a Checkbox, but more compact).
- **Always appear in a group** — never use a Toggle Pill independently.
- Each pill toggles independently — checked state shown with a checkmark icon.
- **When to use over Checkbox:** When vertical space is limited. If wrapping is required, prefer Checkbox — unwrapped text is easier to scan.

**Do:** Group multiple Toggle Pills together for multi-select filtering.
**Don't:** Use a single Toggle Pill in isolation — it loses its filtering context.

### Input Pill
- **Use:** Transforming user-generated text or selections into a dismissible pill.
- Tapping an Input Pill clears it — ensure users can re-enter dismissed selections.
- Can appear inside text inputs, as a stacked list, or in a horizontally scrollable list.

### Action Pill
- **Use:** Contextual, dynamic action triggers that appear inline with primary content (e.g. "Add to calendar", "Set reminder", "Share").
- **Always appear in a group** — no single primary action. For persistent/consistent primary actions, use a Button instead.
- Action Pills do not have a Checked state — pressing triggers the action and returns to Enabled.
- Place within or below the primary content they relate to.

### Filter Rollup Pill
- **Use:** Entry point to a multi-select filter dropdown. Pressing the pill opens a filter menu.
- Shows a counter when filters are selected (e.g. "Amenities 3").
- Should begin in an all-selected or all-unselected state — never mixed defaults.
- Updates results in real time as selections change (no submit button needed).
- **Rollup counter:** Format for 100+: `99+` (configurable if teams set their own max — coordinate with DS).

### Single Select Pill
- **Use:** Entry point to a single-select filter dropdown. Only one attribute can be selected per category.
- Displays the currently selected attribute or a default placeholder.
- Use when there are more options than fit as visible choice pills.
- **Caret icon** is a required indicator.

---

## Comparison guide

| Pill type | Behavior | Selection | When to use |
|---|---|---|---|
| Choice | Visible options | Single | 2–5 visible options |
| Toggle | Visible options | Multi | Filter from visible set |
| Input | User-entered | Add/remove | Text-to-pill conversion |
| Action | Contextual | N/A (triggers action) | Dynamic inline actions |
| Filter Rollup | Opens dropdown | Multi | Large filter sets |
| Single Select | Opens dropdown | Single | Sort, single-category filter |

**Nav Link vs. Single Select:** Nav Links navigate to a new page (URL change). Single Select opens a dropdown for a filter within the page. In tight spaces, Single Select is the closest standard component to a custom nav pill, though not ideal.

---

## Anatomy

**Choice Pill:** Label (A) · Icon (optional) (B) · Container (C)

**Toggle Pill:** Label (A) · Plus icon — enabled (B) · Checkmark icon — checked (C) · Container (D)

**Input Pill:** Border (A) · Container (B) · Label (C) · Plus icon (D) · Clear icon (E)

**Action Pill:** Border (A) · Container (B) · Label (C) · Circle Entity (optional) (D) · Square Entity (optional) (E)

**Filter Rollup Pill:** Border (A) · Container (B) · Label (C) · Caret (mandatory in enabled; optional in selected if input comes from elsewhere) (D) · Counter container (E) · Counter (F)

**Single Select Pill:** Border (A) · Container (B) · Label (C) · Caret — required (D)

---

## Placement and layout

- Prefer horizontal, sequential pill groups. Support horizontal scrolling if pills overflow.
- Stacking: ideally limit rows — stacked pills become harder to scan.
- Spacing: 8px between pills horizontally, 12px below each row.
- **Do not stack Filter Rollup or Single Select Pills** — they should scroll horizontally.

---

## Adaptability

- **Target size:** 48px (mobile, all pill types); 32px compact available for web (use sparingly).
- **Wrapping:** Pills wrap when content exceeds container width. Text in wrapped pills is left-aligned. Icons and entities center-align in their state when pills wrap.
- **Scrolling:** Pills that should stay in one line hug content and scroll horizontally.
- No character count limit — but keep labels short and concise.

---

## Accessibility

**Target size:**
- Mobile (iOS/Android): 48px for all pill types
- Web: 48px default; 32px compact (use sparingly — reduces usability)

**Keyboard:**
- `Tab` — moves focus to the pill
- `Enter` — triggers the pill's dedicated action: selects (choice/toggle/input), opens filter menu (filter rollup/single select), or fulfills a contextual task (action)
- Keyboard operability may vary if the pill is nested inside another control.

**Focus indicator:** Must be visible and unobscured.

**Name, Role, Value:**

| Pill type | Role | Notes |
|---|---|---|
| Choice Pill | `radio` | Icon must be included in a11y label if not in visible label |
| Toggle Pill | `checkbox` | Plus = can be checked; Checkmark = is checked |
| Input Pill | `button` (web) / `toggle` (iOS) / `toggleButton` (Android) | Plus = can be added; Clear = can be removed |
| Action Pill | `button` | Entity is decorative; include entity name in a11y label if not in visible label |
| Filter Rollup Pill | `button` | Append counter: `"Amenities 3 selected"`; caret = `aria-haspopup` |
| Single Select Pill | `button` | Caret = `aria-haspopup` |

A11y label: use visible label unless hidden — then provide `aria-label` or equivalent.

**Color & Contrast:**
- All default colors meet minimum requirements for light and dark modes.
- Disabled state is exempt from contrast minimums.
