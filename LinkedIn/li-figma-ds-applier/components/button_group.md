# Button Group

**Component:** `Button Group SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to present a set of related actions together in a consistent, aligned grouping.
- Limit to **3 surface buttons maximum**. When more than 3 actions are needed, wrap the extras in an overflow menu (triggered by a "…" icon button).

---

## Grouping button variants

| Type | Rule |
|---|---|
| **Primary** | Use with a primary button only; typically the most important action. |
| **Secondary** | Pair with a primary button; performs the second most important action. |
| **Tertiary** | Use for smaller groups of related secondary actions. |
| **Icon buttons** | Pair with a primary button when multiple compact actions are needed; icon-only on mobile. |

- Primary buttons should only appear once per button group.
- Icon buttons should be displayed with a primary button when there are multiple actions — use icon-only on mobile.

---

## Alignment

| Alignment | When to use |
|---|---|
| **Left-aligned** | Default for in-page designs. Appropriate when main content flows left to right. Use for most standard page layouts. |
| **Right-aligned** | Use in dialogs, modals, forms, and inline tables. The primary action sits at the bottom-right. Also appropriate for headers, footers, and data tables. |
| **Center-aligned** | Use when the button group is the focal point of a centered content section. Not for modals or multi-modal contexts. |

---

## Button order

- When button groups stack vertically (due to space constraints), order from most critical at the top to least important below.
- Horizontal groups: primary action typically rightmost in right-aligned contexts.

---

## Overflow

- **Do:** Limit visible surface buttons to 3 maximum. When more actions exist, wrap additional items in an overflow menu (e.g., a "…" Ghost Icon button triggering a Menu).
- **Don't:** Surface more than 3 buttons at once — it overloads the interface and reduces clarity about the primary action.

---

## Reflow

- Button groups are **horizontal by default**.
- When space is limited (e.g., narrow viewports or cards), buttons should **stack vertically**, be center-aligned, and take up the full width of the parent container.

---

## Component alternatives

Use a different component when:
- **Selecting from options** — use Radio buttons, Checkboxes, or Toggle Buttons instead of a button group.
- **Navigation between views or pages** — use Nav Links or Tabs instead; don't use button groups for navigation.
- **Single prominent action** — a standalone Button is simpler and clearer than a group of one.

---

## Accessibility

- Unless using the list version of a button group, include `role="group"` so assistive technologies are alerted to the grouping.
- Each button within the group must have a clear, unique accessible label.
