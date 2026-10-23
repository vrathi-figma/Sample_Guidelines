# Carousel

**Component:** `Paged Carousel SDUI`, `Continuous Carousel SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Horizontal list where some items are intentionally cut off to signal scrollability.
- 4–16 items. Related items, featured content, galleries, or user-generated content.

**Do NOT use when:**
- Critical navigation or primary content — hidden items may be missed.
- Fewer than 4 items or more than 16 items.

---

## Best practices

**Exceed 5 pages:**

**Do:** When the carousel exceeds 5 pages, add a "Show All" button and link to a dedicated page that holds all the content — prevents users from endlessly scrolling within the carousel.
**Don't:** Let items overflow into many pages without a "Show All" escape — users lose awareness of how much content exists.

---

**Min 16px inner padding:**

Because the prev/next navigation buttons overlap with carousel items, always leave at least 16px inner padding for each carousel item so content is not obscured by the button.

**Do:** Maintain 16px padding so text and images aren't hidden behind nav controls.
**Don't:** Allow carousel content to sit flush to the edge — it gets clipped by the navigation button overlay.

---

**Carousel item count:**

Ensure content adjusts dynamically to container and window sizes while staying clear and legible. Avoid overloading narrow containers with too many items — overflow excess items into the next carousel page. Test different language and longer text for reflow issues to prevent truncation or overlap.

**Do:** 2-card carousel that fits cleanly within the container.
**Don't:** 3-card carousel jammed into the same space, causing items to clip.

---

**End carousel item:**

Besides the "Show All" button on the bottom right, a "Show All" end carousel item that links to the full content page is another way to encourage users to check out the full content. Designers are encouraged to use either the button or the end item — but not both.

---

## Anatomy

| Slot | Rule |
|---|---|
| **Carousel Item (A)** | Individual content unit. |
| **Navigation Controls (B)** | Prev/Next buttons. Web only. |
| **Pagination (C)** | Optional. Web only. |
| **Show All (D)** | Optional. Link to full content page. |
| **Page (E)** | Paged carousels only. |

---

## Carousel types

| Type | Behavior |
|---|---|
| **Paged Carousel** | Responsive width. Min 256px per item. Reduces item count as viewport narrows. |
| **Continuous Carousel** | Fixed item width. Viewport-adaptive item count. |

---

## Sizing and adaptability

- Width fills parent container.
- Items respond to breakpoints.
- Item height must be consistent across all carousel items.

---

## Accessibility

**Target size:** Default = 48px. Compact = 32px.

**Keyboard:**
- `Tab` — move to next focusable element
- `Enter` — activate focused element
- `←` / `→` — change pages (paginated carousels)
- Focus order is sequential through all items, including those not currently visible.
- Carousel automatically scrolls items into view as focus moves to off-screen elements.

**Alternative focus order:** Product teams may omit the focus stop on each carousel item and place focus only on interactive elements within each item.

**Additional focusable elements:**
- Pagination dots receive focus after the last carousel item (each dot receives distinct focus).
- "Show All", when present, is the last focusable element in the carousel.

**Name, Role, Value:**

| Slot | Role | A11y Label |
|---|---|---|
| **Carousel (A)** | `List` | — (each carousel item is a List Item) |
| **Nav Controls (B)** | `Button` | "Previous" / "Next" |
| **Pagination dots (C)** | Per Pagination component guidelines | "Page {number}" (e.g., "Page 2"); current page programmatically indicated |
| **Show All (D)** | `Link` | Use visible label |

- If a page has multiple carousels, product teams must append all a11y labels with relevant contextual information to disambiguate.

**Color & Contrast:**
- All default colors meet or exceed minimum contrast requirements for light and dark modes. Customizations in the content area must also meet MAS requirements.
