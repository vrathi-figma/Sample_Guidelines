# External Application Button

**Component:** `External Application Button SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to let a member take an action that opens a third-party application already installed on their device.
- Do not use to represent LinkedIn's own app — this component is exclusively for external applications.
- Most commonly used in sharing experiences (e.g. share a post via WhatsApp, Email, Instagram).

---

## Anatomy

| Slot | Rule |
|---|---|
| **Brand Asset** | Application logo. Comes directly from the client device — does not need to be provided to engineers. |
| **Label** | Required. Shows the application name (e.g. "WhatsApp", "Gmail"). |

---

## Placement

- Use only when the member's action will open an external application — never for internal LinkedIn navigation.
- When multiple external application buttons appear together, group them in a **single horizontal scrollable row**. The number of apps a member has installed is unpredictable — never use multiple rows.
- External application buttons can be grouped with other button types, but formatting must match.
- Typical placement: inside a Bottom Sheet for sharing experiences.

---

## Ordering

Default order (iOS): WhatsApp → Messages → Apple Mail → Facebook → Gmail → Messenger → Instagram → X

Default order (Android): WhatsApp → Messages → Facebook → Gmail → Messenger → Instagram → X

*(Apple Mail does not appear on Android.)*

After the default order, buttons rearrange based on the member's most frequently clicked apps. If a member does not have an app installed, that button does not appear.

---

## States

- **Enabled:** Default resting state.
- **Active:** Pressed/tap state.

**First-time open (iOS):** On the first click of an external app from LinkedIn, iOS presents a native system prompt: "LinkedIn wants to open [App]" with Cancel / Open options. This only appears once per app.

---

## Best practices

- **Be relevant.** If triggered from a specific piece of content, the buttons should correspond to actions for that content — not generic sharing options unrelated to what the member was viewing.
- **Be aware of priority.** Button order is determined by product teams. Follow the ordering guidelines and let usage patterns reorder over time.

---

## Accessibility

**Target size:** Minimum 80px.

**Name, Role, Value:**
- Role: `button`
- a11y name: Must match the visible button label exactly (e.g. "WhatsApp", "Gmail").

**Color & Contrast:**
- Button colors meet contrast requirements.
- Brand assets are controlled by third-party apps and will not change in dark mode. This is expected behavior — LinkedIn does not control third-party brand assets.
