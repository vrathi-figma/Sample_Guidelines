# Global Search

**Component:** `Global Search SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Top-level navigation / discovery entry point for searching across multiple categories (people, companies, jobs, content).
- **Do NOT use** for single-dataset search or page-level filtering — use a dedicated search input component instead.

---

## Anatomy

| Slot | Rule |
|---|---|
| **Search Icon (A)** | Decorative icon; not interactive. |
| **Hint Text (B)** | Placeholder text; must never contain critical information (it is not announced on focus). |
| **Value (C)** | User-entered search query. |
| **Clear Button (D)** | Appears when a value is present; clears the input. |

---

## Technical notes

- Based on Text Input, minus the counter and error states.
- Rendered as `input type="search"`.
- Includes a decorative search icon (non-interactive) and built-in clear functionality.

---

## States

| State | Notes |
|---|---|
| **Empty** | Default; no value entered. |
| **Enabled** | Ready for input. |
| **Hover** | Visual feedback on pointer hover. |
| **Active / Pressed** | Input is focused and receiving input. |
| **Typing** | Value present; Clear button visible. |
| **Disabled** | Available in both unfilled and filled variants. |

---

## Accessibility

**Target size:**
- Input: 48px
- Clear button: 32px

**Focus:**
- When empty: one focus stop (the input).
- When a value is present: two focus stops (input + Clear button).

**Keyboard:**
- `Tab` — moves focus to the input
- `←` / `→` — moves cursor within input
- Character keys — insert text
- `↓` — moves sub-focus into the typeahead/autocomplete menu (when present)
- `Enter` — submits search
- Clear button inherits keyboard behavior from the Button component

**Name, Role, Value:**

| Element | Role | A11y Label |
|---|---|---|
| **Search Input** | `Search` | Programmatic, non-visible label starting with "Search" (e.g., `aria-label="Search"`) |
| **Clear Button** | `Button` | "Clear search" (use a more specific label if other Clear buttons exist on the page) |

- Placeholder text is never the primary source of accessible naming — always provide a programmatic label.
