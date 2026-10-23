# Link Preview

**Component:** `Link Preview SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- In an edit view (e.g., post composer, comment input) when a member inserts or types a recognizable URL.
- Provides a visual preview of the linked content including image, title, and source.
- A Link Preview is a placeholder/mockup in edit view — it may not exactly match how the link appears after publishing.

---

## Best practices

**Use appropriate source information:**
- **Do:** Display the source as a simplified domain-only URL (e.g., `domain.com`).
- **Don't:** Show the full URL with protocol and path (e.g., `https://www.domain.com/sub/page.html`).

**Prefer 1st-party source information:**
- **Do:** When a link points to a first-party LinkedIn target (a LinkedIn article, Company page, or other LinkedIn entity), display the entity name that authored or owns the content as the source — not the domain URL.
- **Don't:** Default to the raw domain (e.g., `linkedin.com`) for 1st-party LinkedIn content when the author or entity name is available.

- Link Previews are block elements — not intended to appear inline with text.
- Appears automatically at the bottom of a text input after a recognizable URL is entered.

---

## Anatomy

| Slot | Rule |
|---|---|
| **Container (A)** | Differentiates Link Preview from other content in the editor. |
| **Remove Button (B)** | Ghost Button with Close icon; no visible text label. |
| **Image (C)** | Optional. Relevant image from the link target. |
| **Title (D)** | Title of the link target. Has built-in padding to avoid colliding with Remove button target area. |
| **Source (E)** | Simplified URL (default) or other source info for 1st-party LinkedIn content. |
| **Meta (F)** | Optional. First sentences of content, follower count, or other metadata. |

---

## Sizes

| Size | Viewport width |
|---|---|
| **Small** | ≤423px (mobile) |
| **Large** | ≥424px (desktop) |

---

## Accessibility

**Target size:** Remove Button = 48px.

**Keyboard:**
- Only the Remove Button receives keyboard focus. All other keyboard operation is standard.
- `Tab` — moves focus to the Remove button
- `Enter` / `Space` — activates the button

**Name, Role, Value:**

| Element | Role | A11y Label |
|---|---|---|
| **Link Preview (A)** | `Group` | Web: derived from Title; Mobile: concatenation of title, source, and meta |
| **Remove Button (B)** | `Button` | "Remove" |

**Color & Contrast:**
- All default colors meet or exceed minimum contrast requirements for light and dark modes.
