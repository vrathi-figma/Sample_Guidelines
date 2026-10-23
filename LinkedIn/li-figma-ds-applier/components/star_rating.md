# Star Rating

**Component:** `Star Rating Group SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to let users view (read-only) or set (interactive) a star rating for a product, service, or item.
- Common in review flows, feedback forms, and aggregate rating displays.

---

## Modes

| Mode | Behavior |
|---|---|
| **Interactive** | User can select a rating. Has Enabled / Hover / Active / Disabled states. |
| **Read-only** | Displays an existing rating — no interactive states. Supports half-checked stars for aggregate ratings. |

---

## Anatomy

| Slot | Rule |
|---|---|
| **Stars (A)** | Always 5 stars. Do not increase or decrease the count. |
| **Rating label (B)** | Optional. Describes what is being rated (e.g., "Project satisfaction"). |
| **Value (C)** | Optional. Displays the numerical value (e.g., "2.5/5"). |

---

## Emphasis

| Style | When to use |
|---|---|
| **Default / Muted** | Subtle appearance; use when rating doesn't need to stand out |
| **Emphasized (yellow)** | Greater visual prominence; preferred in forms, dialogs, and scenarios where the rating must be noticeable |

---

## Sizes

Available sizes: **Large**, **Medium**, **Small**. Size affects visual dimensions only — star count is always 5.

---

## Interaction behavior

- All stars start unchecked. Clicking/tapping a star sets the rating to that value.
- **Clear:** To clear a rating, click/tap the already-selected star one more time (click on the highest selected star).
- **Reset:** Not built in — product teams implement reset if needed.
- **Error:** Use the Inline Feedback component when a required rating has not been submitted.
- **Disabled:** Entire group is disabled — individual stars cannot be disabled independently.

---

## Best practices

**Clear grouping:**
- **Do:** When multiple rating groups appear on the same page, use clear layout and visual grouping so users can easily identify which rating applies to which item.
- **Don't:** Stack multiple rating groups without clear labels or visual separation — users won't know which item each rating refers to.

**Don't customize the number of stars:**
- **Do:** Always use 5 stars. The 5-star scale is universally understood.
- **Don't:** Increase or decrease the star count to fit a container or visual preference — it breaks the standard rating scale and accessibility expectations.

---

## Accessibility

**Target sizes:**
- Default: 48px per star with 8px between stars
- Compact: 32px per star (use sparingly)
- iOS / Android: 48px

**Keyboard:**
- The star rating group is a **single tab stop** — arrow keys navigate within.
- `Tab` — moves focus to the star rating group.
- `←` — increases rating by one (up to 5).
- `→` — decreases rating by one (down to 1).
- When no prior value: sub-focus starts on the first star without selecting it.
- When a value exists: sub-focus starts on the currently selected star. Any arrow press immediately updates the value.

**Focus indicator:** Must be visible and unobscured. Appearance varies by platform/device settings.

**Name, Role, Value:**

*Star Rating Group:*
- Role: `radiogroup`
- Label: use the visible group label text

*Individual Star:*
- Role: `radio`
- Label: human-readable name ("One star" / "Two stars" / "Three stars" / etc.)
- Value: numerical value (1–5)

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
- Disabled state is exempt from contrast minimums — assume some users will not perceive a disabled rating.
