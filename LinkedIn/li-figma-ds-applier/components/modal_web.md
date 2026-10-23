# Modal (Web)

**Component:** `Modal SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to display critical content requiring focus, without navigating away from the current page.
- Use only when it's critical to get attention, or when a task requires its own modal window.
- Avoid modals that interrupt workflow unnecessarily — they impose cognitive load and require immediate action.

---

## Types

| Type | When to use | Footer |
|---|---|---|
| **Passive** | Informational — no action required. Only type that can exclude a footer. | Optional |
| **Transactional** | Validate or confirm a secondary action. Action always required to close. | Required |
| **Progress** | Multi-step focused content in a single modal. Consider adding a Stepper. | Required |
| **Acknowledgement** | System-initiated info the user must acknowledge. Single button. | Required |

---

## Anatomy

| Slot | Rule |
|---|---|
| **Heading (A)** | Optional. Brief purpose description. Lead with a verb in sentence case. |
| **Subheading** | Optional. Clarifies the heading. |
| **Container (B)** | Wraps dialog elements; separates from the page. |
| **Close Button (C)** | Optional. Exit via X, secondary/tertiary button, or scrim click. |
| **Divider (D)** | Optional when content isn't scrollable. Required when content scrolls — differentiates sticky header/footer from scrollable content. |
| **Content (E)** | Overview and basic actions. |
| **Action Bar (F)** | Optional. Up to 3 buttons if a response is required. |
| **Scrim (G)** | Strongly encouraged. Clicking scrim dismisses. If data loss risk, use a Confirmation Dialog instead. |

---

## Footer layout

- **Primary only** — right-aligned
- **Primary + Secondary** — both right-aligned
- **Primary + Secondary + Tertiary** — primary/secondary right-aligned; tertiary left-aligned

Coordinate the primary button label with the modal heading (e.g., "Delete" not "Yes").

---

## Sizes (width)

| Size | Width |
|---|---|
| XSmall | 256px |
| Small | 320px |
| **Medium (default)** | 544px |
| Large | 800px |
| XLarge | 1200px |

---

## Content alignment

- **Left align** — text-heavy content, paragraphs, forms, input fields
- **Center align** — brief visual content, onboarding, feature introductions, splash screens

---

## Error handling

- Place error message near the relevant field or at the top of the modal if it applies to the whole form.
- Highlight fields with a distinct color and icon.
- Auto-focus the first field with an error on submit.
- Keep error message visible until the issue is resolved.
- Disable submit button until all errors are corrected, if appropriate.

---

## Best practices

**Be cautious:**
- **Do:** Use modals only when the content is critical and requires the user's full attention. Focus on simplicity and a single primary task.
- **Don't:** Use modals to display non-critical information, long text, or complex multi-task forms — this imposes unnecessary cognitive load.

**Be simple and focused:**
- **Do:** Keep modal content focused on one clear action or decision. Limit the number of form fields and buttons.
- **Don't:** Pack modals with complex forms, multiple decisions, or nested dialogs — if a task is too complex for a modal, use a full page instead.

**Modal-on-modal:**
- **Don't:** Stack modals. Opening a second modal on top of an existing one creates usability and accessibility issues. Strongly discouraged.

---

## Avoid

- **Modal-on-modal** — stacking modals creates usability and accessibility issues. Strongly discouraged.
- Displaying long strings of text — use a separate page or inline content instead.
- Triggering modals on hover, focus change, or text input — explicit user action only.

---

## Interaction

**Trigger:** Explicit user action (click/keyboard). Never on hover, focus change, or input.

**Dismiss:**
- Close button, secondary/tertiary button, or click scrim.
- If closing would discard changes, confirm via Confirmation Dialog first.
- On close, return focus to the element that triggered the modal.

---

## Accessibility

**Target size:** All modal buttons = default 48px. Content area controls must meet or exceed MAS 2.5.8.

**Keyboard:**
- On open, focus is set to the Modal container.
- Sequential focus: Close button → content area → Action Bar.
- Focus is **trapped** — no elements outside the modal can receive focus while open.
- `Tab` at the last element wraps to the first (and vice versa).
- All interactive elements must be keyboard operable. (MAS 2.1.1)

**Name, Role, Value:**

*Modal:*
- Role: `Dialog`
- A11y Label: use visible heading text

*Buttons:*
- Role: `Button`
- Close button A11y Label: "Close"
- Other buttons: use visible text

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
