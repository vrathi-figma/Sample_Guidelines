# Overflowing Content

**Reference:** `◾️ Overflowing content`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

Cross-cutting guidance on how to handle content that exceeds its available space.

---

## Best practices

- **Priority content:** Always consider which elements are most critical for users — ensure they remain visible.
- **Test responsiveness:** Ensure your indicator scales across various device sizes and orientations.
- **Maintain usability:** Whether reflowing content or using an overflow menu, users should still be able to access all necessary information and the content remains clear.

---

## Reflow to the next available line

A component must reflow to maintain readability and visibility within the available horizontal space, preventing the need for horizontal scrolling.

**Use when:**
- Text with multiple fields where maximizing readability is essential.
- Forms with multiple fields that need to remain aligned and accessible.

---

## Overflow clipped elements into a Menu or Drawer

When content exceeds available space, place overflow items into a Menu or Drawer that can be accessed by an overflow element represented by three dots. This ensures all elements remain accessible without cluttering the interface.

**Use when:**
- Navigation bars with many action items.
- Navigation bars with many menu items.

---

## Navigation controls for horizontal scrolling

Enable horizontal scrolling with navigation controls (e.g., chevrons) when there are more elements than can fit in the available space. This approach allows accessible scrolling without overwhelming the user.

**Use when:**
- Tables or lists with a large number of items.
- Media galleries with many images or thumbnails.

---

## Visually hide non-critical elements

Hide non-essential content when space is constrained — particularly when the same functionality can be conveyed another way. For instance, you may hide the label of a button if the icon effectively communicates its purpose and relies on the tooltip.

**Use when:**
- Tables where some columns are less important.
- Actions where space is highly constrained.

**Avoid:** When the icon itself is not clearly understood — you should use accessible techniques (tooltips, aria-labels) rather than relying on icon alone.

---

## Truncation

Truncation cuts off text and replaces the end with an ellipsis (`…`). Use as a last resort — it causes real problems:

1. **Loss of information** — Truncation often hides important information, making it harder for users to understand content at a glance. The loss can make labels difficult to distinguish from one another.
2. **Inconsistent user experiences** — The same content may display in full on larger screens but get truncated on smaller ones, leading to an inconsistent experience.
3. **Accessibility issues** — Truncation is not a substitute for using screen readers as expected. When truncated, content might be read aloud in full, confusing users by presenting content differently from what they see.

**Actions must always be clear:** Truncating the labels of buttons or other interactive elements is especially problematic. Actions need to be clearly understandable and accessible. If an action is unclear due to truncation, users may hesitate or omit it altogether, leading to a poor user experience — or see critical errors. Truncating actions might make them unrecognizable in other languages.
