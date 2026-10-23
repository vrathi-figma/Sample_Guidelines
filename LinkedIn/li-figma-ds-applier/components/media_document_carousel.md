# Media Document Carousel

**Component:** `Document Carousel SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Displaying documents shared within posts in feeds and compact surfaces (PDFs, presentations, image-based documents).
- Provides in-context document interaction without leaving the feed.

**Do NOT use for:**
- Non-document content (articles, videos).
- Content requiring inconsistent controls across platforms.
- Unconventional interactions (zooming, panning, navigation should follow common UI patterns).

---

## Best practices

- **Do:** Clearly indicate the document type (e.g., "PDF", "Presentation") so users know what they're viewing.
- **Do:** Utilize Document Carousels for displaying relevant documents shared within posts — PDFs, presentations, and image-based documents.
- **Do:** Provide a download option when appropriate.
- **Do:** Use clear and intuitive navigation, zooming, and full-screen controls that follow common UI patterns.
- **Don't:** Use Document Carousels for non-document content (articles, videos) — they are not designed for that format.
- **Don't:** Use inconsistent or non-standard controls across platforms — zooming, panning, and navigation should follow expected UI conventions.
- **Don't:** Force unnecessary features — only include controls relevant to the intended use of the document.

---

## Anatomy

| Slot | Rule |
|---|---|
| **Header** | Document title and page count (e.g., "[Document title] — [#] pages"). |
| **Page** | Document carousel items. |
| **Document Toolbar** | Pagination controls (Previous/Next buttons, page number selector). |

---

## Accessibility

**Target size:**
- Default: 48px
- Compact: 32px

**Keyboard:**
- `Tab` — moves focus logically through interactive elements (toolbar buttons, etc.)
- `↑` / `↓` arrow keys — vertical scrolling
- `←` / `→` arrow keys — horizontal scrolling (when active)
- `Page Up` / `Page Down` — navigate document pages
- `Ctrl/Cmd` + `+`/`-` — zoom in/out
- `Ctrl/Cmd` + `0` — reset zoom to default

**Focus order:**

*Web:* All focused elements must remain visible. Carousel scrolls to bring focused items into view.
- Navigation controls receive focus after the last carousel item.
- Pagination controls (pointer-based, e.g., mouse/touch) cannot receive keyboard focus.

*Mobile:* Carousel automatically moves items into view as focus moves to off-screen elements.
- Pagination dots for Spotlight Carousels receive distinct focus after the last carousel item.

**Name, Role, Value:**

| Element | Role | A11y Label |
|---|---|---|
| **Carousel** | `List` | — |
| **Each carousel item** | `List Item` | — |
| **Previous / Next buttons** | `Button` | "Previous" / "Next" (append `{carousel name}` if multiple carousels on page) |
| **Pagination dots** | Per Pagination guidelines | "Page {number}"; current page programmatically indicated |

- If a page has multiple Document Carousels, product teams must append all a11y labels with contextual information (e.g., "Previous" → "Previous {carousel name}").
