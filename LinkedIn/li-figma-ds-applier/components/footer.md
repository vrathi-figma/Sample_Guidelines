# Footer

**Component:** `Footer SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Present on every screen of the application; universal to the entire app.
- Position based on content: when page content doesn't fill the first screen, fix the footer to the bottom of the screen.

---

## Footer types

| Type | When to use |
|---|---|
| **Stacked** | Basic elements (logo, copyright, links) in the right or left rail. |
| **Bottom** | Basic elements at the bottom of the page. |
| **Bottom Expanded** | Full footer with all links, columns, and language selector at the bottom of the page. |
| **Bottom Modal** | When additional items need to be included, a "More" button (styled as a link) triggers a footer modal dialog for language selection and additional resources. |

---

## Anatomy

| Slot | Rule |
|---|---|
| **Link (A)** | Links to other pages (About, Accessibility, Help Center, etc.). |
| **Button / link-styled (B)** | Opens a menu or bottom sheet (Privacy & Terms, Business Services, More). |
| **Logo (C)** | Reinforces brand identity. |
| **Copyright label (D)** | Copyright symbol + year + company name. |
| **Icon (E)** | Optional. |
| **Helper text (F)** | Additional information. |
| **Language Select (G)** | Language selector (combobox). |
| **Close Button (H)** | Closes the footer modal dialog. |
| **Container (I)** | Holds footer elements in a bottom panel. |

---

## Accessibility

**Keyboard:**
- `Tab` — moves through footer links and controls in sequential order (1 → 2 → … → n → n+1 → End)
- All footer links and buttons are keyboard navigable in order

**Name, Role, Value:**

| Element | Role | A11y Label |
|---|---|---|
| **Links (A)** | `Link` | Use visible label |
| **Buttons (B)** | `Button` | Use visible label |
| **Language Select (G)** | `Combobox` | "Select Language" |
| **Close Button (H)** | `Button` | "Close" |
