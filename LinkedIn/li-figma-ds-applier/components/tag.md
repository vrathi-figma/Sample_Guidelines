# Tag

**Component:** `Tag SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to label or categorize content — skills, job types, content topics, status indicators.
- Use sparingly. Tags communicate metadata; they are not decorative elements.
- Always include a visible text label. Never rely on color alone to convey meaning.

**Be wary of context and spacing:** Do not use multiple Tags inline with each other in limited space to avoid wrapping and unnecessary stacking. Use Tags contextually to draw out the most pertinent and important information. For example, on a post it may be best to draw attention to the member's role like "Author." On a profile page, highlighting a degree connection with a Tag may be more appropriate.

**Use sparingly:** Tags are not a replacement for metadata. They should highlight an important quality about the design or content. Include more open space when using Tags to break up content and support consistent structure.

**Don't rely on color alone:** Color alone cannot be used to convey the Tag "state" or meaning. The text provided in a Tag should always be useful independent of the Tag's color.

---

## Types

| Category | Variant | Use |
|---|---|---|
| **Signal** | Default | General labeling, neutral context |
| **Signal** | Neutral | Secondary or de-emphasized labels |
| **Signal** | Positive | Success states, verified, approved |
| **Signal** | Negative | Error states, rejected, removed |
| **Signal** | Caution | Warning states, pending, at risk |
| **Supportive** | 5 brand color variants | Brand-aligned categorization (e.g. topic areas, product lines) |

Signal tags communicate semantic meaning. Supportive tags are for brand-aligned grouping without inherent status meaning.

---

## Sizes

| Size | Height | Use |
|---|---|---|
| **Small** | 20px | Dense layouts, inline with body text |
| **Medium** | 24px | Default; standard content contexts |

Size affects padding, not the text size or label content.

---

## Behavior

- Tags are **static and non-interactive**. They do not receive focus, cannot be clicked, and have no keyboard interaction.
- If you need interactive tags (selectable, dismissible), use Pills instead.

---

## Position

| Context | Placement |
|---|---|
| Long text or localized labels | Place **above** the content (top-aligned) to avoid layout compression |
| Limited vertical space | Place **beside or inline** with content |

---

## Adaptability

- Text **wraps** — tags do not truncate. Ensure labels are concise enough to avoid excessive wrapping.

---

## Accessibility

**Name, Role, Value:**
- Role: static text / label (no interactive role).
- Do not assign button or link roles — Tags are not interactive.
- Color meaning must always be supplemented with a text label.

**Color & Contrast:**
- All Signal and Supportive tag colors meet minimum contrast requirements for light and dark modes.
- Never use color as the sole differentiator between tag types.
