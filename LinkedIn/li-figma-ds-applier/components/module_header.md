# Module Header

**Component:** `Module Header SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- To label a section of a page and make the page skimmable and navigable.
- Always place content below a Module Header — never use it at the bottom of a section with nothing following.

**Do NOT use when:**
- Two module headers would appear within the same section.
- The page already has too many headers, which adds visual noise and reduces navigability.

---

## Best practices

**Place the header contextually:**
- **Do:** Place Module Headers before a supporting section of content. Only use headers when there is content directly below them.
- **Don't:** Stack multiple headers within the same section without content between them — the page feels visually loud and harder to navigate.

**Include only what is necessary:**
- **Do:** Keep the header minimal — just the heading text is often enough. Add subheader, buttons, or premium branding only when they serve a clear purpose.
- **Don't:** Fill every optional slot by default. Optional elements should be used contextually, not universally.

**Button styling:**
- **Do:** Use the button type that best fits your product experience. Be mindful of consistency across headers on the same page.
- **Don't:** Override the built-in button styles. Use only the button styles built into the Module Header component.

**Premium branding:**
- **Don't:** Use Premium branding elements if the module is not part of a Premium product.

---

## Component property keys

| Property | Key | Default |
|---|---|---|
| Header text | `Header text#61592:0` | `"Module header"` |
| Subheader text | `Subheader text#61592:3` | `"Module subheader"` |
| Show Button 1 | `Show Button 1#64977:0` | `true` — **both buttons are visible by default. Always hide them unless the design explicitly requires a CTA.** |
| Show Button 2 | `Show Button 2#64977:13` | `true` |
| Subheader | `Subheader` (variant) | `"True"` |
| Button Type | `Button Type` (variant) | `"Secondary"` |
| Surface | `Surface` (variant) | `"Web"` |
| Premium | `Premium` (variant) | `"False"` |

---

## Anatomy

| Slot | Rule |
|---|---|
| **Header (A)** | Required. Section title. |
| **Subheader (B)** | Optional. Supporting description. |
| **Buttons (C)** | Optional. Secondary, Ghost, or Ghost Icon buttons only. |
| **Premium Branding (D)** | Optional. Premium products only. |

---

## Sizing

- **Web:** Larger padding.
- **Mobile:** Smaller padding.
- Height hugs content. Width fills parent container.

---

## Accessibility

- Buttons must meet MAS 2.5.5 target size requirements.
