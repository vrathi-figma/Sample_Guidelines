# Accordion

**Component:** `Accordion SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use when it's acceptable that some users may not notice or read all of the included content.
- Use when users benefit from a high-level overview first, with the ability to drill down into details.
- **Don't use** when users are likely to need to read all of the content — use a full scrolling page with standard Headers instead.

**Do:** In some Accordions, additional elements are always visible adjacent to the Accordion. For instance, an icon and/or a subheading may accompany each Accordion to provide additional hints.

**Don't:** If a user is likely to read all of the content, don't use an Accordion as it adds the burden of an extra click; instead, use a full scrolling page with standard Headers.

---

## How to configure

**Variants:**
| Property | Values |
|---|---|
| `State` | `Enabled` · `Hover` · `Active` · `Disabled` |
| `Expanded` | `True` · `False` |

- Default to `State=Enabled, Expanded=False`.
- Always use the built-in state variants — never approximate Hover, Active, or Disabled with custom styling.
- The chevron end icon is part of the component — do not add or replace it manually.

---

## Anatomy

| Slot | Label | Rule |
|---|---|---|
| **Start Row** | A | Optional. Icon slot at the leading edge of the header. Use only to reinforce the heading. |
| **Heading** | B | Required. The visible label for the accordion row. |
| **End Icon** | C | Always present. Chevron indicating expand/collapse state — do not remove or replace. |
| **Content Panel** | D | The collapsible content area. Hidden until expanded. |

---

## Slots and content

**Heading (required)**
- Keep it short and concise.
- Only add qualifiers if necessary to clarify expected behavior.
- Never truncate — long headings wrap to multiple lines and expand the container. This is expected.
- Don't use long or wordy titles. Extra long titles negatively affect the overall hierarchy.

**Start Icon (optional)**
- Use only to reinforce the heading.
- If used, ensure the icon meaning is reflected in the visible label or provide an aria-label equivalent.

**Content Panel**
- Any content can go here — it is hidden until expanded.
- Clicking anywhere in the Header (not just the chevron) expands and collapses the panel.

---

## Adaptability

When headings are long they will wrap to multiple lines and expand the container. Headings should never truncate.

**Do:** Keep the title short and concise. Only add additional qualifiers if it's necessary to clarify the expected behavior.

**Don't:** Don't use long or wordy titles. Extra long titles can negatively affect the overall hierarchy. **Never truncate Accordion headings.**

---

## Accessibility requirements

**Target size:** Min tap target is 48px — already encoded in the component. Do not override height.

**Focus indicator:** Must be visible and unobscured when focused via keyboard. Do not remove or override it. Appearance may vary by platform or device settings — this is expected.

**Keyboard operation** (non-disabled only):
- `Tab` — moves focus to Headers
- `Enter` or `Space` — expands/collapses content

**Name, Role, Value:**
- Role is Button
- A11y label must use visible text
- Expandable state must be programmatically indicated when a user triggers an expandable list view

**Color & Contrast:**
- All default colors meet or exceed contrast requirements in both light and dark modes — do not override.
- Disabled state has no contrast requirement. Assume some users will not be able to perceive a disabled Accordion.
