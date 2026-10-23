# Link

**Component:** `Link SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use when the action navigates to a different page, opens an external resource, or scrolls to a section within the same page (resulting in a URL change).
- Links offer a lightweight navigation alternative to buttons. They can appear independently or inline with text.
- **Do NOT use a Link** for actions that don't navigate — use a Button instead (e.g., making a choice, submitting a form, triggering in-page interactions like expanding a section).

---

## Link vs. Button

| Use | Component |
|---|---|
| Navigate to a different page or URL | **Link** |
| Open an external resource or document | **Link** |
| Scroll to a section within the page (URL change) | **Link** |
| Perform an action without navigating away | **Button** |
| Make a choice or decision on the page | **Button** |
| Trigger in-page interactions (expand, collapse, open dialog) | **Button** |

---

## Placement and styles

### Standalone links

A standalone link is displayed on its own, not embedded in a paragraph. Common labels: "Learn more," "See details," "View details."

- **Do:** Use **Bolded link style** for standalone links — ensures visibility while avoiding the visual noise of underlining. Paired with color, it makes links clearly recognizable across environments.
- **Don't:** Use Plain link style for standalone links where the link contains important information — plain links are less perceptible and harder to distinguish.

### Inline links

An inline link is embedded within a paragraph or running text. It promotes contextual exploration without disrupting reading flow.

- **Do:** Use **Underlined link style** by default for inline links — underline ensures the link is distinguishable from surrounding non-linked text.
- **Do:** Use Bolded style as an alternative if the contrast with surrounding text is sufficient to clearly identify it as a link.
- **Don't:** Use Plain link style inline — when links need to be perceived and acted upon, plain styling makes them too easy to overlook.

### Plain links

Plain links have no underline and no bold. Use only in contexts where visual prominence is intentionally deprioritized (e.g., footer links, secondary reference links).

- **Don't:** Use plain link style for links containing important information or requiring clear discoverability — consider underlined or bolded style to improve accessibility and perceivability across contexts and surfaces.

---

## Accessibility

**Keyboard:**
- `Tab` — moves focus to the link
- `Enter` — activates the link

**Name, Role, Value:**
- Role: `Link`
- Name: use visible link text. Avoid vague labels like "Click here" or "Learn more" when used standalone — they lack context for screen reader users.
- If link text is vague in context, provide a more descriptive `aria-label`.

**Color & Contrast:**
- All default link colors meet minimum contrast requirements for light and dark modes.
- Do not rely on color alone to distinguish links from surrounding text — use underline or bold in addition to color.
