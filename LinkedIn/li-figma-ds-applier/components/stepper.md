# Stepper

**Component:** `Stepper SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to show users where they are in a multi-step process.
- Steppers are a **visual display of progress only** — they are not interactive.
- Do not use for fewer than 3 steps (minimum 3 major steps; or minimum 3 major + 1 sub-step for mixed layouts).

---

## Layouts

| Layout | When to use |
|---|---|
| **Horizontal** | Linear sequence, limited number of steps, wide screens. Content is separate from the stepper. |
| **Vertical** | More detail per step, limited horizontal space, sub-steps present. Content is embedded alongside the stepper. |

**Choosing layout:**
- **Horizontal:** Best for linear processes that flow left to right (e.g., checkout, multi-step forms). Ideal when space allows and step count is limited. Works well on wide screens where progress is simple to visualize.
- **Vertical:** Best for processes with more detailed content under each step, or when horizontal space is limited. Effective for long forms, detailed instructions, or flows with sub-steps and nested tasks.

---

## States

| State | Meaning |
|---|---|
| **Checked / Complete** | Step has been finished |
| **Current** | Step the user is on right now |
| **Future** | Steps not yet reached |

---

## Sizes

| Size | Use |
|---|---|
| **Large** | Primary / major steps |
| **Small** | Sub-steps only |

Mix Large and Small sizes to establish visual hierarchy between major steps and sub-steps.

---

## Sub-steps

- A major step stays **Current** until all of its sub-steps are complete.
- Once all sub-steps are complete, the major step becomes **Complete**.
- Show sub-steps only when the parent step is "Current" (optional behavior for compact viewports).

---

## Adaptability

- Step labels **wrap** — never truncate.
- Horizontal stepper handles ~5 steps natively; product teams are responsible for handling more than 5.
- Optional: hide "Complete" labels on narrow viewports to save space.

---

## Content rules

- Labels: **1–5 words**, sentence case, nouns or noun phrases.
- No verbs, no full sentences.

---

## Accessibility

**Interaction:** Steppers are non-interactive — no keyboard navigation is defined for the stepper itself.

**Name, Role, Value:**

*Stepper container:*
- Role: `List`

*Step item:*
- State: Completed / Current / Future (communicated programmatically)
- Name: visible label text, or associated with a nearby heading
- Step number is auto-announced (e.g., `"Step 1, [a11y label]"`)

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
