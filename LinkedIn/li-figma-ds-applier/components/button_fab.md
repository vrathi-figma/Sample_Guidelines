# Button FAB

**Component:** `Button FAB SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

> Also apply all Button component guidelines — this doc is additive and specific to FABs.

---

## When to use

- Use for the primary or most common action on a screen.
- FABs float above UI, typically in the bottom-right corner.
- Common actions: Create, Add Contacts, Share, start a process, refresh content (e.g. "New posts", "New notifications").
- Avoid for minor, ambiguous, or destructive actions: Archive, Trash, alerts, controls better suited to a toolbar.

---

## How to configure

**Anatomy:**
| Slot | Rule |
|---|---|
| Icon | Required. Must clearly communicate the action, especially when no label. |
| Container | Has elevation — visually floats above other UI elements. |
| Label | Optional. Use when the icon alone may be ambiguous. |

**Variants:**
| Property | Values |
|---|---|
| `Size` | `Medium` · `Small` |
| `Label` | `True` (with label) · `False` (icon only) |
| `State` | `Enabled` · `Hover` · `Active` |

---

## Placement rules

- Valid positions: bottom-right corner, top center, or bottom center of a screen.
- Maintain 16px spacing between the FAB and edges of the toolbar or screen.
- Individual components (e.g. cards) cannot each have their own FAB — one FAB per screen.

---

## Best practices

**Be relevant.** A FAB should be relevant to the screen on which it appears. For example, use it in list views to browse content that is new or important for users in that context.

**Do:** Use a single FAB for a clear, screen-specific primary action (e.g. compose on Feed).
**Don't:** Use a FAB for a generic action that doesn't match the current screen context.

---

**Avoid multiple FABs.** A floating action button is a primary button on the page. Having multiple FABs or distinct primary actions on the same screen creates ambiguity.

**Don't:** Display two FABs on the same screen.

---

**Be aware of priority.** A FAB promotes important, constructive actions: Create, Add Contacts, Share, Starting a process, refreshing content (New posts), Minor notifications.

**Do:** Use a FAB for constructive, high-value actions (e.g. compose, add, share).
**Don't:** Use a FAB for minor, ambiguous, or destructive actions (e.g. Archive, Trash, alerts, thumbs down — use a toolbar instead).

---

**Don't use with badge.** Never layer a badge or other element in front of a FAB.

**Don't:** Place a badge on top of a FAB.

---

## Interaction

A FAB can:
- Trigger an action on the current screen, or
- Open a new screen or dialog.

---

## Accessibility

**Target size:**
- Web: Medium = 48px, Small = 32px.
- Mobile (iOS/Android): All sizes = 48px minimum.

**Focus order:**
- FAB should be near the top of the focus order to reflect its visual prominence.
- Mobile order: top app bar → nav bar → FAB → scrollable content.

**Keyboard operation (non-disabled only):**
- `Tab` — moves focus to FAB
- `Enter` — activates FAB

**Name, Role, Value:**
- Role: Button.
- Icon-only: Always define an a11y name (e.g. "Call", "Create post").
- With label: Ensure any icon meaning is also reflected in the a11y name (e.g. "AI Insights").

**Tooltips:**
- Consider displaying a tooltip when an icon-only FAB receives keyboard focus.
- Tooltip must match the a11y name.
- Never rely on a tooltip alone for usability — it may not be available on all platforms.

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
