# Expandable Text

**Component:** `Expandable Text SDUI`, `_Expandable Text Control SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to collapse long paragraphs of text into a limited number of lines, with an expansion CTA to reveal the full content.
- Common for comments, bios, descriptions, and other user-generated long-form text.

**Note:** Building this exactly to spec is beyond Figma's current functionality. The Figma component is FPO (For Placement Only). Follow written specs — the component may contradict them.

---

## Anatomy

| Slot | Rule |
|---|---|
| **Preview Text (A)** | N lines of text shown in the collapsed state. |
| **Collapsed Line (B)** | The final visible line in the collapsed state — ends before the expansion CTA. |
| **Expansion CTA (C)** | Inline link ("more") that expands the text. |
| **Collapse CTA (D)** | Inline link ("show less") that re-collapses the text. |

---

## Behavior

**Collapsed state:** Shows Preview Text + Collapsed Line + "...more" inline.

**Expanded state:** Shows full text + "show less" below. Expansion CTA is removed.

**Options product teams can configure:**
- Text style (can be overridden)
- Padding (can be adjusted)
- Max number of lines shown
- Remove collapsibility ("show less" capability can be disabled when content should not re-collapse)

---

## Content rules

**Truncation:**
- Ellipsis appears at the end of the last full word — never mid-word.
- Omit the period when truncating at the end of a sentence (to avoid double punctuation: "...").
- Ellipsis color must match the main text color, not the "more" link color.

**Double Return handling:**
- When the Collapsed Line ends at a double return (paragraph break), the expansion CTA appears inline on the same line.
- The Expansion CTA container must NOT contain the ellipsis (`...`) or have a background fill — doing so clips letters.
- The expansion CTA must NOT align flush to the container edge.

**Don't: Clipped letters** — The Expansion CTA container should not house the ellipses (...) or have a fill. This causes the Expansion CTA to clip or cut off individual letters.

**Don't: Truncate mid-word** — Truncation should not appear within individual words, only at the end of the last full word that can be displayed in the available width.

**Don't: Incorrect ellipsis color** — The ellipsis (...) should match the color of the main text content, not the color of the "more" link.

**Do: Omit the period if truncating at the end of a sentence** — When possible, omit the period to reduce the multiplication of punctuation.

**RTL:** "more," ellipsis, and "show less" mirror their LTR counterparts.

---

## Accessibility

**Target size:** The Expansion CTA qualifies for the Link touch target exception — it is inline within a paragraph and has low consequence if accidentally tapped. Target size = the height and width of the "more" string only.

**Critical:** The tap/click target must only be on the word "more" — NOT on the ellipsis + "more" combined.

**Keyboard:**
- Focus moves to the Expansion CTA ("more") as a standard inline link.
- `Enter` or `Space` activates it.
- Focus indicator must be visible and unobscured.

**Name, Role, Value:**

*Expansion CTA / Collapse CTA:*
- Role: `Button`
- Use `aria-expanded="true/false"` to indicate current state.
- Use `aria-controls` to link the button to the content it controls.
- Labels must update when state changes (collapsed → expanded → collapsed).

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
