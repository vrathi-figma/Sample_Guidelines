# Filter Panel (Web)

**Component:** `Filter Panel SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- To let users narrow down large datasets by applying filter attributes, without a scrim background change.
- Use in LinkedIn Enterprise products as a side panel alongside the main content.
- Filters help users view available options based on specific criteria and accelerate decision-making.

---

## Filter panel items

Product teams can customize filter panel items based on their needs. Supported item types:

| Type | Notes |
|---|---|
| **Text Input / Search Input / Typeahead** | Selected/typed values appear as Input Pills below the input. |
| **Select** | Single or multi-select. Can include a range. |
| **Radio / Checkbox** | For grouped input selections. |
| **Pills** | For category or state-based filtering. |

Panel items can optionally be expanded or collapsed using the Accordion component.

---

## Best practices

**Right-positioned:**
- **Do:** Position the filter panel on the right side of the screen. It should only contain supplementary content — filter controls and criteria — not tools or navigation.
- **Do:** Use the filter panel to display contextual information specific to the content being filtered. It has the lowest hierarchy within a layout and should be positioned below any horizontal tabs.
- **Don't:** Use the filter panel as a general-purpose content area or place primary navigation within it.

---

## Anatomy

| Slot | Rule |
|---|---|
| **Heading (A)** | Brief description of the filter panel's purpose. |
| **Container (B)** | Holds overlay elements; separates from the rest of the screen. |
| **Close Button (C)** | Lets users exit via the X button. |
| **Content (D)** | Filter panel items with filter attributes. |
| **Divider (E)** | Optional when content is not scrollable. Required when content scrolls — differentiates sticky header/footer. |
| **Action Bar (F)** | Fixed at the bottom while scrolling. Contains button group. |
| **Clear All Button (G)** | Resets all selected filters to default state. |
| **Apply Button (H)** | Confirms selected filters, closes panel, updates search results. |

---

## Interaction

**Trigger:** Explicit user action only (click, keyboard, touch). Never triggered automatically. Panel appears without a scrim background change.

**Dismiss:**
- Close button (X)
- Click outside the panel — closes without applying changes
- Apply or Clear All button

On close, return focus to the element that triggered the panel.

---

## Accessibility

**Target size:** All buttons = 48px. Content area controls must meet or exceed MAS 2.5.8.

**Keyboard:**
- On open, focus is set to the filter panel container (even though the container is not normally focusable — ensures screen readers start at the beginning).
- Sequential focus: Close button → content area elements → footer action buttons.
- `Tab` — moves to next focusable element
- `ESC` — dismisses the panel (same as pressing Close)
- All interactive elements must be keyboard operable. [MAS 2.1.1]

**Name, Role, Value:** [MAS 4.1.2]

| Element | Role | A11y Label |
|---|---|---|
| **Filter Panel (A)** | `Dialog` | Use visible heading text |
| **Close Button (C)** | `Button` | "Close" |
| **Action Bar Buttons (G, H)** | `Button` | Use visible text ("Clear all", "Apply") |

**Color & Contrast:**
- All default colors meet or exceed minimum contrast requirements for light and dark modes. Customizations must also meet MAS requirements.
