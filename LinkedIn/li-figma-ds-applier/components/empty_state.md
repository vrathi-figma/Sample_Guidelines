# Empty State

**Component:** `Empty State SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use when there is no content or data to show in a particular section or page.
- Fill the void, guide new users, introduce features, and prevent experience "dead ends."
- Tailor the depth and quantity of content to the specific situation — avoid cognitive overload.

---

## Anatomy

| Slot | Rule |
|---|---|
| **Illustration (A)** | Spot or Microspot. Decorative — no alt text needed. |
| **Heading (B)** | Required. Short, specific. States the current circumstance. |
| **Body (C)** | Optional. Describes the situation and a resolution. Limit to 3 lines. |
| **Button (D)** | Optional. Helps direct the user to the next best action. |

---

## Illustration types

| Type | Image sizes | When to use |
|---|---|---|
| **Spot** | Large (128), XLarge (256) | Significant portions of a page or screen lack content — landing pages, dashboards, main content areas |
| **Microspot** | Small (48), Medium (64) | Smaller UI elements — Typeahead, dropdowns, individual sections within a page |

A well-chosen illustration communicates the "story" at a glance and can inspire users to act. Reference Intro to Illustration for guidance on appropriate Spot selection.

---

## Buttons

- The button appears by default to avoid a dead end — it can be switched off if there is no call to action.
- For visual balance and focus, use an emphasized secondary or tertiary button.
- Do not add too many buttons — one clear action is better than multiple competing options.

**Do:** Use an emphasized secondary or tertiary button when a CTA is needed — keeps visual hierarchy clear without competing with the illustration.
**Caution:** Avoid using a primary (filled) button in an empty state unless the call to action is the most critical action on the entire page — a prominent primary button can feel out of place in an empty context.

---

## Position

- Always center the empty state within the page or container.
- Minimum 16px padding from edges.

---

## Content rules

- **Heading:** Describe what is missing — not what went wrong.
- **Body:** Describe what happened and suggest next steps. Max 3 lines.
- Tone: Human, upbeat, and trustworthy. Help users feel supported, not at fault.
- Always provide a descriptive heading for accessibility — never leave the empty state unlabeled.

---

## Adaptability

- Text and buttons mirror direction (LTR/RTL).
- Illustrations always maintain default LTR direction regardless of locale.
- Height is not a fixed value — it's driven by text height + spacing to accommodate long strings and language-specific line heights.

---

## Accessibility

**Target size:** Follow Button component target size guidance.

**Keyboard:** The button is the only keyboard-focusable element. Follow Button keyboard behavior.

**Name, Role, Value:**

*Button:*
- Role: `Button`
- Name: use visible label text

*Illustration:*
- Decorative — no alt text.

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
