# Rich Text Editor

**Component:** `Rich Text Editor + Text Area (Web) SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use when users need to format text with bold, italic, underline, links, or lists.
- Always paired with a Text Area component.

---

## Anatomy

| Slot | Rule |
|---|---|
| **Toggle Buttons (A)** | Text formatting controls (bold, italic, underline, etc.) |
| **Divider (B)** | Separates logical groups of buttons for clarity |
| **Ghost Buttons (C)** | Related action buttons (e.g., insert link, add list) |
| **Container (D)** | Wraps the toolbar; product teams configure button arrangement |

Product teams compose toolbars from these parts — there is no fixed default set of buttons.

---

## Toggle button state behavior

| Selection state | Toolbar behavior |
|---|---|
| **Text selected (uniformly formatted)** | Show "Pressed" for all formats present in the selection |
| **No selection, cursor in field** | Show "Pressed" for what will be applied to the next character typed |
| **Mixed/partial selection** | Do NOT show "Pressed" — only pressed when entire selection is uniform |
| **Disabled button** | May appear to show that an action is not applicable in context |

---

## Keyboard shortcuts (default)

| Action | Shortcut |
|---|---|
| Bold | `Ctrl/Cmd + B` |
| Italic | `Ctrl/Cmd + I` |
| Underline | `Ctrl/Cmd + U` |
| Add link | `Ctrl/Cmd + K` |
| Bulleted list | `- + Space` |
| Numbered list | `1. + Space` |

Product teams may optionally add shortcuts for custom buttons.

---

## Placement

**Web:**
- Position toolbar at top or bottom of the text area.
- When toolbar exceeds available width, items collapse into an overflow button that triggers a Popover.

**Mobile:**
- Toolbar appears above the on-screen keyboard.
- Supports swipe gestures to access additional options.
- When multiple RTE inputs exist on the same page, the toolbar is shared — it's visible whenever any RTE field is focused.
- Toolbar hides when the on-screen keyboard is dismissed (external keyboard paired, or user dismisses on Android).

**Mobile overflow:** Toolbar becomes horizontally scrollable; Dismiss button remains fixed on the right.

---

## Best practices

**Logical grouping:**
- **Do:** Group related toggle buttons together (e.g., Bold, Italic, Underline in one cluster; alignment options in another). Use Dividers to separate functional groups.
- **Don't:** Mix unrelated formatting controls without visual separation — this makes the toolbar harder to scan.

**Clear and intuitive icons:**
- **Do:** Use recognizable, industry-standard icons (bold B, italic I, underline U). Add tooltips on hover for additional clarity, especially for less common options.
- **Don't:** Use ambiguous or non-standard icons that users can't identify without reading a tooltip.

**Avoid too many toggle buttons:**
- **Do:** Prioritize the most commonly used formatting options (bold, italic, underline, link, lists). Put secondary options in an overflow menu.
- **Don't:** Clutter the toolbar with every possible formatting option — too many controls increase cognitive load and reduce usability.

- Keep at least 8px spacing between editors.

---

## Accessibility

**Target sizes:** Inherits from Toggle Button and Button components.
- Web: 32px minimum
- Mobile: 48px minimum

**Keyboard:**

*Toolbar:*
- `Tab` — moves focus to the first non-disabled button in the toolbar
- `←` / `→` — moves sub-focus between buttons within the toolbar
- `Space` / `Enter` — activates the focused button

*Overflow:*
- `Tab` — moves focus to the "More" overflow button
- `Space` / `Enter` — expands the overflow menu
- `←` / `→` — moves sub-focus between buttons in the overflow menu

**Name, Role, Value:**

*Toggle Button:*
- Role: `Button`
- Name: Must be defined. Must be predictable based on icon. Include contextual info if needed (e.g., "Bold").
- State: "Pressed" is communicated programmatically and separate from the label.

*Ghost Button:*
- Role: `Button`
- Name: Must be defined and predictable from icon.
- State: "Pressed" communicated separately.

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
