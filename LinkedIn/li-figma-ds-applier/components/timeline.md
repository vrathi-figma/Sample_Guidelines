# Timeline

**Component:** `Timeline SDUI`, `Timeline Item SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to display events, milestones, or role changes in chronological order.
- Common use case: showing a progression of job titles within the same company on a LinkedIn Profile.
- Minimum 2 points — a single point fails to communicate progression or comparison.

---

## Timeline vs. Stepper

| Component | When to use |
|---|---|
| **Timeline** | Chronological display of historical events/milestones |
| **Stepper** | Step-by-step task progress with Completed / Current / Future states |

Do not use a Timeline to represent states like Completed, Current, or Future — use a Stepper instead.

---

## Anatomy

| Slot | Rule |
|---|---|
| **Timeline Node (A)** | Structural anchor for the timeline indicator (decorative, not a target) |
| **Label (B)** | Required. The main event title — the only region with visible hover/active state |
| **Subtitle (C)** | Optional. Supporting detail (e.g., employment type) |
| **Time Metadata (D)** | Optional. Start/end dates or timestamps |
| **Location Metadata (E)** | Optional. Work location or location type |
| **Placeholder (F)** | Optional. Slot for media, skills, or other supplemental content |
| **Connector Line (G)** | Decorative. Connects nodes. Not part of the interactive target. |

---

## Interaction

- The **label (title)** is the only visually interactive region — it changes color and becomes underlined on hover and active.
- Subtitle, metadata, and surrounding target area remain visually unchanged on hover (no color change) to reduce visual noise.
- Labels wrap on narrow or mobile viewports.

---

## Accessibility

**Target size:** 76px for the full timeline item (title, subtitle, and metadata are all within the interactive region). The node indicator and connector line are decorative and not part of the target.

**Keyboard:**
- `Tab` — moves focus to the timeline title (link)
- `Enter` — activates the link
- Focus then moves sequentially to any interactive elements inside the placeholder area (nested content)

**Name, Role, Value:**

*Timeline node:*
- Role: `List Item`

*Timeline title:*
- Role: `Link`
- Name: concatenate visible strings — title + subtitle + metadata (time and location) into the accessible label

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes. Customizations must also meet MAS minimums.
