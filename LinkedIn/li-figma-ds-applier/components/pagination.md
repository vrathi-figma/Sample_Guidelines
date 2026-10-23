# Pagination

**Components:** `Pagination Control Number Group (Web) SDUI`, `Pagination Dot SDUI`, `Pagination Indicator SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to divide high-volume content across multiple pages — search results, tables, carousels.
- Do not use for navigating between workflow steps — use Stepper instead.
- Do not use for unrelated content sections — use Tabs instead.
- Do not use Pagination Indicator for interaction — it is purely decorative.

**Do not use Pagination to navigate between steps in a workflow:**

**Do:** Use Stepper, specifically for taking the user through a series of stages (e.g. "Enhance your profile → Stand out with slideshow covers → Update your page").
**Don't:** Use page number pagination to walk users through a multi-step workflow.

**Unrelated content:**

**Do:** If the content sections are unrelated to each other, use Tabs or another form of navigation (e.g. Explore / Flights / Trips as separate tabs).
**Don't:** Use Pagination to navigate between unrelated content types.

**Do not use Pagination Indicator for interactivity:**

**Do:** Use Pagination Indicator as a read-only position indicator (e.g. carousel dots).
**Don't:** Make Pagination Indicator interactive or tappable — it is strictly decorative.

---

## Types

| Type | Platform | Interactive | Use |
|---|---|---|---|
| **Pagination Number** | Web only | Yes | Fixed number of pages; direct jump to page number. Previous/Next buttons for linear navigation. |
| **Pagination Dot** | Web + Mobile | Yes | Dynamically changing page counts; better alternative to infinite scroll. |
| **Pagination Indicator** | Web + Mobile | No (decorative) | Read-only position indicator for carousels, slideshows, media galleries. |

---

## Anatomy

**Pagination Number:**
- Previous button (hidden on first page)
- Page number links (each links to a specific page)
- Selected page indicator (filled container)
- Next button (hidden on last page)

**Pagination Dot:**
- Selected dot (enlarged, current page)
- Inactive dots (other pages)
- Helper text (optional)

**Pagination Indicator (read-only):**
- Active page: horizontally elongated indicator
- Large dot: inactive indicator
- Medium dot: overflow preview
- Small dot: overflow boundary

---

## Interaction

**Pagination Number:** Click any page number to jump directly, or use Previous/Next for linear navigation.

**Pagination Dot:**
- Web/Android: tap a dot to navigate to that page.
- iOS: swipe gesture OR tap left/right side of parent container. Cannot tap individual dots.

**Pagination Indicator:** Not interactive. On mobile, swipe or tap parent container to open expanded view.

---

## Position

Place directly beneath the main content it controls. Typically sits at the bottom of the page.

---

## Adaptability

**Pagination Number reflow:**
- Default max: 11 indicators (excluding Previous/Next).
- At medium width: number of visible indicators reduces.
- When fewer than 7 fit: switches to a Select (listbox) component.
- At smallest width: icon-only Previous/Next buttons with Select.

**Pagination Dot overflow:**
- ≤8 indicators: all visible, stable center alignment.
- When space limited: enters compact overflow state — second-to-last visible dot scales to medium (6×6px), last scales to small (4×4px).
- Active indicator always stays within visible viewport, re-centers as user navigates.
- At end of range, trailing dots scale back up to restore symmetry.

---

## Accessibility

**Target size:**
- Web: Pagination Number and Dot use compact 32px target size.
- Mobile: Pagination Dot uses default 48px. No compact variant on mobile.
- Pagination Indicator: decorative, 24–32px height.

**Focus indicator:** Must be visible and unobscured.

**Keyboard operation — Web:**
- `Tab` — moves focus to next pagination element
- `Enter` — activates button or link
- On first page: focus starts at page "1" (Previous button is hidden).
- On last page: focus ends at last page number (Next button is hidden).

**Keyboard operation — Mobile:**
- `Shift` — moves focus to next pagination control
- `Enter` — activates control

**Name, Role, Value:**
- Previous/Next buttons: Role = Button, a11y label = `"Previous"` / `"Next"`
- Page numbers: Role = Link, a11y name = `"Page [n]"`. Current page has programmatic `"Current"` state.
- At small breakpoints (Select): a11y label = `"Page"`, each page appears as a Select option with current page as selected value.

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
