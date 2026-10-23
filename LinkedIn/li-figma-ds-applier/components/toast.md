# Toast

**Component:** `Toast SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to deliver brief, non-blocking notifications confirming the outcome of a user action.
- Best for ephemeral confirmations that are minimally interruptive and don't require user action.

---

## Toast vs. alternatives

| Scenario | Use instead |
|---|---|
| User must respond before continuing (e.g., confirming a risky action) | **Confirmation Dialog** |
| Outcome must be persistent or missing it degrades usability | **Inline Feedback** |
| Errors that need to persist | **Inline Feedback** (errors rarely belong in Toasts) |
| Urgent system-wide status updates affecting the entire app | **Global Alert** |
| Avoid using both Toast and Inline Feedback together — choose one. |  |

**Toast vs. Confirmation Dialog:**

**Do:** Use Toast for ephemeral confirmations — e.g. "File uploaded ✓" after a completed action.
**Don't:** Use Toast to ask the user a question or confirm a risky action (e.g. "Upload to?") — that requires a Confirmation Dialog, which blocks interaction and ensures the user can't miss it.

**Toast vs. Inline Feedback:**

**Do:** Use Inline Feedback when layout allows — it appears in context, directly related to the field or action that caused the issue.
**Don't:** Use Toast for form errors or validation messages — Toast appears in a fixed location away from the problematic field, which breaks the spatial relationship and degrades the experience.

---

## Anatomy

| Slot | Rule |
|---|---|
| **Icon (A)** | Non-configurable. Corresponds to the semantic variant (positive/neutral/negative). |
| **Message (B)** | Required. Brief text about the outcome. Max 2 lines English; up to 3 lines for translations. |
| **Action (C)** | Optional. Inline link or short link after the message. Max 1 action; 2–3 words. |
| **Dismiss button (D)** | Required. "X" button always available for manual dismissal. |

---

## Semantic variants

| Variant | When to use |
|---|---|
| **Positive** | Reaffirm the success of a completed action (e.g., "File uploaded.") |
| **Neutral** | Supplementary information about the current experience |
| **Negative** | Draw attention to a critical issue requiring immediate awareness |

---

## Interaction

**Auto-dismiss (required):**
- **Short (default):** 3 seconds — for messages under 5 words with no action.
- **Long:** 7 seconds — for longer messages, messages with actions, or where there's risk of losing data or trust.

**Manual dismiss:**
- X button (all platforms).
- Mobile also supports vertical swipe gesture (like OS notifications).

**Consecutive Toasts:**
- One at a time — a new Toast immediately replaces any existing Toast.

**Async:**
- Toast closes when the user navigates away or when focus shifts predictably (e.g., a modal opens).

---

## Placement

| Platform | Position |
|---|---|
| **Web** | Bottom-left of the browser window. 32px from bottom and left edges. Left-aligned to layout. |
| **Mobile** | Above the bottom nav, overlapping the main content area. Appears over FABs and other floating elements. |

---

## Content rules

- Keep to the outcome of a single specific action — not general status updates.
- Keep English copy to **2 lines max** (3 lines max for translations).
- **No user-generated content** — unpredictable length can make the message difficult to read.
- **Max 1 action** — clear and concise; follow the message without line breaks. No unnecessary actions.
- **Punctuation:** Full sentences end with a period. Link/action copy has no period.
- **Format:** Noun + verb phrases. "File uploaded." not "Your file has been successfully uploaded!"
- Be mindful of frequency — too many Toasts interrupt attention, especially for users with cognitive or visual disabilities.

---

## Accessibility

**Target sizes:**
- Web close button: 32px minimum
- Mobile close button: 48px minimum
- Inline action: exempt from target size minimum (inline links are exempt)

**Focus behavior:**
- Toasts appear **at the beginning of the focus order** — but focus must **not** move to the Toast when it appears.
- Focus remains on whichever element triggered the Toast.
- When a Toast is dismissed, focus moves to the next focusable element in page order.
- Toasts are **non-modal** — they do not trap focus. Users can navigate freely as if it's inline content.

**Keyboard:**
- `Tab` — moves focus between interactive elements within the Toast (action link, dismiss button)
- `Enter` — activates the link or button in focus
- `Esc` — dismisses the currently-showing Toast

**Name, Role, Value:**

*Message:*
- Role: `status` live region (or platform equivalent)
- `aria-live="polite"`, `aria-atomic="true"`
- The full message (including link text) is announced by screen readers when the Toast appears — no focus movement needed

*Action:*
- Role: `link`
- Name: use visible text

*Dismiss button:*
- Role: `button`
- Name: `"Dismiss"`

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
