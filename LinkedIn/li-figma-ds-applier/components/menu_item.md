# Menu Item

**Component:** `Menu Item SDUI`, `Menu Item Submenu SDUI`, `Menu Item Selection SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use as an individual action or option within a Menu or Bottom Sheet.
- **Do not use Menu Item by itself** — always use within a group (Menu, Bottom Sheet, or Popover).
- Can function as a standalone anchor link for within-page navigation (jump links).

---

## Best practices

**Use it as a group:**
- **Do:** Use Menu Items together as a group from different contexts within the same Menu or Bottom Sheet.
- **Don't:** Use a Menu Item by itself in isolation — it has no standalone meaning outside of a group.

**Max number:**
- **Do:** Aim for 5–7 items max to reduce cognitive load (Miller's Law). Users can comfortably process 5–7 options without feeling overwhelmed.
- **Don't:** Add too many items without grouping — beyond 7 items, the menu becomes visually cluttered and harder to scan. For 10+ items, use category headers.

**Clear order:**
- **Do:** Organize items in a logical order — by steps, time frames, frequency, or alphabetically. Use category headers for 10+ items so users can find options faster.
- **Don't:** Present items in a random or inconsistent order.

**Content design:**
- **Do:** Start labels with a clear action verb. Keep labels concise and scannable. Use consistent phrase construction across all items.
- **Don't:** Use grammar articles ("a", "an", "the") at the start of labels. Don't use sentence case inconsistently or mix verb vs. noun-phrase labels within the same menu.

---

## Menu Item vs. Tabs vs. Nav Links

| Component | Behavior |
|---|---|
| **Menu Item (standalone)** | Scrolls/anchors to a section within the same page |
| **Tabs** | Shows adjacent content panels in the same view |
| **Nav Links** | Loads a new screen or page (URL changes) |

---

## Anatomy

| Slot | Rule |
|---|---|
| **Indicator (A)** | Selected state indicator. Web only. |
| **Start Icon/Entity (B)** | Optional. Helps interpret the item. Entity = Circle or Square (32). |
| **Label (C)** | Required. Describes the purpose of the menu item. |
| **Helper Text (D)** | Optional. Complementary supporting information. |
| **Additional Label / End Icon (E)** | Optional. End icons limited to: Chevron Up/Down, Link External, Checkmark, Right arrow. For submenu items: Caret Right only. |
| **Container (F)** | Wraps the item. |

---

## Variants

| Variant | Description |
|---|---|
| **Default** | Standard action item |
| **Submenu** | Has Caret Right end icon; opens nested menu on activation |
| **Selection** | Has indicator dot/checkmark for selected state |

---

## Accessibility

**Target size:**
- Default: 48px
- Compact: 32px — only use if sufficient spacing is maintained between items

**Keyboard (in Menu / Bottom Sheet):**
- Focus starts at the first enabled item. Disabled items cannot receive focus.
- `↓` / `↑` — navigate between items; wraps at first/last
- `Enter` — activate focused item
- `ESC` — dismiss the menu

**Keyboard (Single Select):**
- `→` — move focus to the checkbox or radio
- `Enter` — activate the focused control

**Keyboard (Submenu):**
- `↓` / `↑` — navigate submenu items; wraps
- `→` — open submenu without triggering the item's action
- `Enter` — activate focused submenu item
- `ESC` / `←` — close submenu and return focus to parent menu item

**Name, Role, Value:**

*Menu Item (in Menu or Bottom Sheet):*
- Role: `menuitem` (web) / `Button` (mobile)
- `role="menuitem"` must be inside a `role="menu"` container
- A11y Label: use visible label text
- A11y Hint: use visible text, programmatically linked
- If triggers submenu: use `aria-haspopup`

*Menu Item (Standalone anchor link):*
- Role: `Link`
- A11y Label: clear visible link text that matches the section it targets

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
