# Select

**Component:** `Select (iOS & Web) SDUI`, `Select (Android) SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to collect a single option from a predetermined list within a form.
- Only for form data collection — not for commands, filtering, or sorting (use Menu instead).

---

## Select vs. alternatives

| Component | When to use instead |
|---|---|
| **Radio** | Fewer than 5 options — show all choices immediately |
| **Checkbox / Filter Rollup Pill** | Multi-select — user can choose more than one option |
| **Menu** | Taking an action, filtering, or sorting content (not form submission) |

**Key distinction from Menu:** Select triggers native platform UI (listbox on web, picker on iOS, spinner on Android). Menu is a LinkedIn-designed component. The rendered list appearance is determined by the browser or OS — not LinkedIn.

**Select vs Radio Buttons:**

**Do:** Use Radio Buttons when there are fewer than 5 options — e.g. "Current Status: Available / Pending / Unavailable" (3 options, all visible).
**Don't:** Use a Select dropdown for 3 options — the collapsed state forces an unnecessary extra interaction.

**Select vs Checkbox:**

**Do:** Use Checkboxes when the user can select more than one option — e.g. "Africa / North America / United States / Europe / Europe Economic Area."
**Don't:** Use a Select dropdown for multi-select scenarios.

---

## Anatomy

| Slot | Rule |
|---|---|
| **Label (A)** | Required. States the purpose of the input. |
| **Hint (B)** | Optional. Shown when no default value is set and field is empty. |
| **Value (C)** | The currently selected option. Truncates (does not wrap) on overflow. |
| **Helper text (D)** | Optional. Additional instructions or context. Wraps on overflow. |
| **Caret icon (E)** | Required. Indicates the field expands to show options. |

---

## States

Each size has Unfilled and Filled variants, each with four interactive states:
- **Enabled** — default resting state
- **Hover** — web only
- **Active** — while the dropdown is open / interaction in progress
- **Disabled** — not interactive; exempt from contrast minimums

---

## Error state

- Error is indicated by a border color change **and** required error text below the field.
- **Never hide error text** — the border color change alone may not be perceivable by all users.
- Triggered when a required Select is left blank on form submission.

---

## Sizes

| Size | Target size (Web) | Target size (iOS/Android) |
|---|---|---|
| **Small** | 32px | 48px |
| **Large** | 48px | 48px |

Clicking the label should also focus the Select.

---

## Content rules

- Use predictable, logically ordered values (e.g., alphabetically sorted lists).
- Members may need to scroll through hidden options — ordering matters for scanability and speed.

---

## Adaptability

- Label, helper text, and error text wrap when content is long.
- Selected value **truncates** — does not wrap.
- When forms have multiple dense fields, ensure enough padding so wrapping helper/error text does not obscure adjacent fields.

---

## Accessibility

**Keyboard:**
- `Tab` — focuses the Select
- `Space` / `↓` — expands the list of options; or sets value to highlighted option and collapses if open
- `↑` / `↓` — moves highlight through options (also expands list on web if collapsed)
- Character keys — jumps to the next option starting with that character
- `Esc` — collapses the list without changing the value

**Focus indicator:** Must be visible and unobscured. Appearance varies by platform and device settings.

**Name, Role, Value:**
- Role: `Select` (`listbox` on web / `picker` on iOS / `spinner` on Android)
- Name: use visible label text; if programmatic label differs, it must start with the visible label text (MAS 2.5.3)
- Value: `null` when empty / currently selected option when filled
- Helper text: programmatically linked (e.g., `aria-description`)
- Caret icon: represents the ability to expand — decorative, no separate a11y label needed

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
- Disabled state is exempt from contrast minimums.
