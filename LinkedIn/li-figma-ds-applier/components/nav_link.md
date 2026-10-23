# Nav Link

**Component:** `Nav Link SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to provide high-level navigation between major areas of a product — displaying top-level locations and enabling quick movement between them.
- Use Nav Links to group content locations of equal importance and similar type in your information architecture.
- Interacting with a Nav Link affects the state of the view — equivalent to navigating to another page. Nav Links typically = a URL change.

---

## Nav Link vs. Tabs vs. Menu Items

| Component | Interaction result |
|---|---|
| **Nav Link** | Navigates to a new page / URL change |
| **Tabs** | Reveals adjacent content within the same view — no URL change |
| **Menu Items (Standalone)** | Scrolls to a section within the same page (anchor/jump links) |

These look visually similar but behave completely differently. Use the right one for the right interaction pattern.

- **Nav Links for primary navigation:** Use when clicking changes the page or URL.
- **Nav Links + Tabs together:** Use Nav Links for primary navigation areas and Tabs to control visibility of adjacent content panels within those areas.
- **Menu Items (Standalone) as content scroll/anchor links:** Use when the "navigation" scrolls within the same page, not to a new page.

---

## Variants

**Horizontal:**
- Use to organize navigation within a specific section or feature.
- Optional: icon, caret icon (for dropdown menus).
- Width options: Fixed (consistent sizing) or Fill to Container (evenly distributed, flexible).
- States: Enabled / Hover / Active / Current / CurrentHover / Current Active.

**Vertical:**
- Use when horizontal space is generous or when there are more sections than can fit horizontally.
- Can also serve as anchor link navigation (shortcuts to sections within a single page).
- Optional: icon, helper text, additional label, caret icon, arrow indicator, illustration (micro-spot).
- States: same as horizontal.

**Pill:**
- Variant of vertical nav links using a pill visual treatment.
- States: same as horizontal.

**Illustration:**
- Includes a micro-spot illustration alongside the label.
- Two layout options: Left-right (use when viewport height is limited) / Top-bottom (use when viewport width is limited).
- Micro-spot size is fixed at 32px.
- Width: "Hug" based on label length or "Fill parent container."

---

## Anatomy

| Slot | Rule |
|---|---|
| **Label** | Required. Describes the destination. |
| **Indicator** | Required. Marks selected/current state. |
| **Icon** | Optional (horizontal); optional with entities for vertical. |
| **Caret icon** | Optional. Indicates dropdown submenu. |
| **Helper text** | Optional. Vertical layout only. |
| **Additional label** | Optional. Vertical layout only. |
| **Arrow indicator** | Optional. Vertical layout only. |
| **Illustration** | Optional. Illustration variant only (micro-spot). |
| **Container** | Always present. |

---

## Overflow behavior

**Web:**
- When Nav Links exceed the container width, overflow items move into a "More" button with a dropdown menu.
- If the selected Nav Link is in the overflow menu, the "More" button changes to the selected value and is highlighted.
- Option 1: All visible nav links shown; overflow in "More" dropdown.
- Option 2: Fixed visible nav links; remaining items in "More" dropdown menu.
- Vertical Nav Links do not have an overflow menu — vertical space is sufficient.

**Mobile (iOS/Android):**
- Horizontal scroll for overflow (no "More" button).
- Option 1: Scrollable nav links within the container.
- Option 2: Fixed visible nav links; overflow triggers a Bottom Sheet.

---

## Content rules

- Labels: short noun phrase, sentence case.
- Labels describe the content destination — keep them concise.

---

## Internationalization

- **RTL:** Icons flip to the right of the label. All labels flip direction (left to right becomes right to left).

---

## Accessibility

**Target size:** Minimum 48px tap target for all Nav Link items.

**Keyboard:**
- The Nav Link list is a **single tab stop**. Use arrow keys to navigate within the list.
- `Tab` — moves focus to/from the Nav Link list
- `←` / `→` — moves focus between Nav Link items (horizontal)
- `↓` / `↑` — moves focus between Nav Link items (vertical or overflow menu)
- `Enter` / `Space` — activates the focused Nav Link; or opens the overflow menu if focused on "More"
- Focus wraps around at the ends of the list.
- When the "More" button is focused, `↓` also opens the overflow menu.
- On activation: displays the associated panel, keeping focus on the Nav Link; or expands overflow menu.

**Focus indicator:** Must be visible and unobscured.

**Name, Role, Value:**

*Nav Link group:*
- Role: `navigation`
- a11y label: `"Primary"` / `"Secondary"` / `"Tertiary"` / `"Quaternary Navigation"` — based on hierarchy level

*Nav Link item:*
- Role: `link`
- a11y label: visible text label (no custom override needed)
- Helper text: additional supporting information via programmatic association
- State: programmatic `"Current"` state to indicate which item represents the current location

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
