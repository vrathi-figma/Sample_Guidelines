# Inline Feedback

**Component:** `Inline Feedback SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

Use to show short, contextual messages after user actions or triggered by the system.

| Type | When to use |
|---|---|
| **Positive** | Confirm a successful action: save, submit, correction, change applied. |
| **Negative** | Something went wrong and blocks completion. Reserve for true blockers only — not general informational states. |
| **Neutral** | Non-critical info, status updates, tips, empty state descriptions. Informs without blocking. E.g. "No results. Try a different term." |
| **Caution** | Warnings — something may go wrong or requires user awareness before proceeding. |

---

## Anatomy

| Slot | Rule |
|---|---|
| Icon | **Required.** Ensures type is not communicated by color alone. (MAS 1.4.1) |
| Text | Main feedback message. |
| Link | Optional. Supplemental follow-up action related to the message. |

---

## Interaction

- Triggered by user action or system event.
- Product team decides when inline feedback disappears (e.g. error is resolved, page reloads).
- Text wraps to multiple lines when content is long. Never truncate.

---

## Internationalization

- **RTL:** All content flips to match locale reading direction.
- **Other languages:** Write messages with translation in mind. Avoid vague text that may not adapt well across languages.

---

## Accessibility

**Screen reader announcement:**
- When inline feedback appears, it must be announced to screen readers.
- Web: use a live region.
- iOS/Android: use a11y notification or alert.

**Keyboard:**
- If a link is present: inline feedback receives focus in sequential order.
- If no link: inline feedback does not receive focus.
- Never auto-move focus to the inline feedback when it appears.

**Name, Role, Value:**
- Icon: Role = Image. Alt text must be `"Success"`, `"Error"`, `"Info"`, or `"Caution"` to match type.
- Link: Role = Link. A11y label = visible link text. Avoid vague labels like "Learn more" when possible.

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
