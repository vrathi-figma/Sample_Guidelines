# Global Alert

**Components:** `Global Alert (Web) SDUI`, `Global Alert (Mobile) SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

> **Deprecated:** Current library versions of Global Alert are deprecated. Confirm with the designer before using this component.

---

## When to use

- Use for system-level messages only: status updates, platform changes, or errors communicated via a banner near global navigation.
- Only one alert visible at a time.
- Do not use for page-level confirmations, notifications, or in-product messages. Use Inline Feedback, Toast, or other patterns for those.

**Severity:** A Global Alert cites a current system condition or action — not page-level confirmations or notifications. Because an alert is also an interruption, the urgency of the alert should match the severity of the situation.

**System-level only:** Global Alert should be used only for system-level messages. For in-product or quick confirmations and errors, use Inline Feedback or Toasts instead.

**Top level:** Global Alert should always appear at the top layer of screen, never obscured by any other element. If a blocking message is needed, consider using a Modal (web) or Bottom Sheet (mobile).

---

## Types

| Type | When to use |
|---|---|
| **Neutral** (default) | Supplementary info about a user's current experience or important actions to take. |
| **Caution** | Informs users about conditions that may limit their ability to use the platform. |
| **Error** | Critical issue needing immediate attention. No dismiss button — must stay until user acts or system state changes. |

Icons for each type are fixed — do not change them.

---

## Anatomy

| Slot | Rule |
|---|---|
| Icon | Required. Distinguishes alert type. |
| Message | Required. Max 3 concise sentences. |
| Title | Optional. Use for verbose alerts when context is needed before the message. |
| Link | Optional. Directs user to more information. |
| Dismiss button | Optional (default included). Not available for Error type. |
| Buttons | Optional. Use only for explicit user action scenarios like legal consent. Max 2. |
| Container | Neutral background, complements global nav. Never change container colors. |

---

## Configuration

**Concise (default):** Short message, no title, dismiss button only. Use whenever possible.

**Verbose:** Title + message + up to 2 buttons. Reserve for scenarios requiring explicit user consent or action.

**Buttons:** Fill horizontal space, appear inline by default. On mobile with long button labels, buttons may stack vertically.

**Dismissal:**
- Neutral and Caution: dismiss button available by default (can be hidden if consent via action buttons is required).
- Error: no dismiss button. Must stay until user takes action or system resolves.

---

## Position & behavior

- **Web:** Appears adjacent to global navigation. Content area centered, max 1128px wide. Text wraps at max 1000px.
- **Mobile:** Appears at the bottom of the screen.
- Always at the top layer — never obscured by other elements.
- If a blocking message is needed (fully prevents interaction), use a Modal or Bottom Sheet instead.

**Simultaneous alerts:** Stack with only one visible at a time. When topmost is dismissed, the next appears.

---

## Adaptability

- Text wraps to multiple lines; icon and dismiss button remain top-aligned.
- If message height exceeds 70px (web) or 45px (mobile), the content area scrolls vertically.
- At 320px viewport (web): alert unsticks and scrolls with the global header.
- Mobile landscape: spans full screen width with same outer margins.

---

## Content rules

- Use noun + verb phrases. Full sentences get punctuation; link copy does not.
- Keep messages focused on the current system condition. Not promotional.
- Max 2 actions. Keep action labels clear and concise.

---

## Internationalization

- **RTL:** All content (icon, text, buttons, dismiss) flips to match locale reading direction.
- **Other languages:** Use descriptive language and provide translation-ready copy.

---

## Accessibility

**Target size:**
- Dismiss button and action buttons: compact 32px (alert is space-sensitive).
- Inline link: derives target size from body text line height.

**Keyboard:**
- `Tab` — move focus to link or button
- `Enter` — activate focused link or button

**Name, Role, Value:**
- Alert message: Role = `status` (Neutral/Caution) or `alert` (Error). `aria-live` = `polite` (default) or `assertive` (Error). Content = title + message + link text only (not icons or buttons).
- Dismiss button: Role = Button, a11y label = `"Dismiss"`
- Link: Role = Link, a11y label = visible label
- Action buttons: follow Button component guidance

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
