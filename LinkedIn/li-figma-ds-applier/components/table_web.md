# Table (Web)

**Component:** `Table SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)
**Platform:** Web only — tables do not exist on mobile. Design an optimized mobile experience separately.

---

## When to use

- When a large amount of data needs to be displayed, filtered, or acted on.
- Each row conceptually represents a single item; each cell contains one attribute of that item.

---

## Best practices

### Be simple
- All cells in a column must contain the same data type (dates, numbers, text, etc.).
- Each cell should contain only one value — avoid field sets.
- Nested tables are highly discouraged.

### Alignment
- Left-align text data.
- Right-align numeric data.
- Actions (last column): Right-align by default. Center-align if the column is wide. Left-align if actions relate directly to adjacent column data.

### Hierarchy
- Organize columns and rows based on subject matter, context, task priority, or user needs.
- Consider ordering columns by importance left to right, or alphabetically.

---

## Anatomy

| Slot | Rule |
|---|---|
| **Header (A)** | Column headers at the top of each column; identify the type or category of data in that column. |
| **Cell text (B)** | Individual units containing data values at the row/column intersection. |
| **Checkbox (C)** | Optional. Indicator for selected state (row or header). |
| **Divider (D)** | Separates rows; supplemental structure for the table layout. |
| **Cell Container (E)** | Only visible when the tab group overflows. |

---

## Types

All types can be combined — for example, a sortable table can also have checkboxes.

| Type | Description |
|---|---|
| **Default** | Clean visual style. |
| **Alternate** | Striped rows to increase legibility for long datasets. |
| **Select** | Supports selecting all or a subset of rows for further actions. Uses Checkbox component; refer to Checkbox guidelines for parent/child checkbox interactions. |

---

## Accessibility

**Target size:** 32px minimum for all interactive elements.

**Keyboard:**
- `Tab` — moves focus through interactive elements inside cells (buttons, links, inputs, selects, etc.)
- `←` / `→` — scrolls the table horizontally when columns are fixed
- Focus order: left to right within a row (e.g., checkbox first), then to the next row

**Name, Role, Value:**

| Element | Role | Visible Label | A11y Label |
|---|---|---|---|
| **Select-all Checkbox** (header) | `Checkbox` | No | "Select all" |
| **Row Checkbox** | `Checkbox` | No | n/a |
| **Sort Button** (column header) | `Button` | No | "Sort" |
