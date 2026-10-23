# Typeahead

**Component:** `Typeahead (Web) SDUI`, `Typeahead (Mobile) SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

**Use Typeahead (Combobox) when:**
- Users need to search within a large dataset (country, city, user directory, product catalog)
- Typing is faster than browsing through a long list
- Precision and filtering are needed
- Space is limited and showing all options at once is impractical

**Do NOT use when:**
- The dataset is small and easily scannable — use a standard Select/dropdown instead
- The primary goal is exploration, not targeted selection

---

## Search logic

**Default:** "contains" — results include any item where the search term appears anywhere in the text.

**Customizable to "starts with":** Limits results to items that begin with the search term. Product teams configure this.

---

## Anatomy

| Slot | Rule |
|---|---|
| **Typeahead Input (A)** | Text field that filters results in real time. Supports single and multi-selection. |
| **Search Results (B)** | Web: dropdown Menu. Mobile: Bottom Sheet, Leaf Page, or Full-Screen Modal. Can include Menu Items, Entity Lockups, Checkboxes, or Radio Buttons. Can be pre-loaded or dynamically fetched. |
| **Option (C)** | Selectable item in Search Results. Must be keyboard navigable and visually distinct when selected. |
| **Progress Indicator (D)** | Shows when content is loading. |

---

## States

- **Enabled** — input ready, no dropdown
- **Active – Empty** — input focused, no query yet
- **Active – Typing** — query entered, results shown
- **Loading** — fetching results
- **Partially Loading** — some results shown; more loading
- **No Results** — query returned nothing

---

## Accessibility

**Target size:**
- Default: 48px (covers label + input area when label is present)
- Compact: 32px (when no label is present)

**Keyboard:**

*Typeahead input:*
- `Tab` — focus moves to input
- `↓` — opens Search Results (if not open) and highlights first option
- `↑` — moves to last option when Search Results are open
- `Enter` — selects highlighted option; closes dropdown (single) or adds as input pill (multi)
- `ESC` — closes Search Results without selection, returns focus to input

*Multi-select selected pills:*
- `←` / `→` — move focus between selected pills
- `Backspace` / `Delete` — removes focused pill

*Clear button (optional):*
- `Tab` — focus on clear button
- `Enter` — clears all selections and resets input; focus returns to input
- `Shift + Tab` — moves focus back to input

*Search results list:*
- `↓` / `↑` — navigate options
- `Enter` — select highlighted option
- `ESC` — close without selection

Focus indicator must be visible and unobscured. `aria-activedescendant` updates dynamically as user navigates options. "No results found" message must be keyboard navigable and announced by screen readers.

**Name, Role, Value:**

*Typeahead Input:*
- Role: `combobox`
- A11y Label: via associated `<label>` (preferred), `aria-label`, or `aria-labelledby`
- `aria-expanded="true/false"` — whether the dropdown is open
- `aria-controls="[listbox-id]"` — links input to the listbox
- `aria-activedescendant="[option-id]"` — identifies currently highlighted option
- `aria-autocomplete="list"` — signals dynamic suggestions
- `aria-multiselectable="true"` — if multi-select is enabled

*Clear button:*
- Role: `Button`
- `aria-label="Clear selection"`

*Search Results list:*
- Role: `listbox`
- ID must match the value in the input's `aria-controls`
- `aria-labelledby="[input-id]"`

*Option:*
- Role: `option`
- Unique ID (referenced by `aria-activedescendant`)
- A11y Label: inner text
- `aria-selected="true/false"`
- Multi-select with checkboxes: follow Checkbox a11y requirements

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
