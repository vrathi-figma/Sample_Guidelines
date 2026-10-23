# Tabs

**Component:** `Tab SDUI`, `Tab Group SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to switch between related content panels within the same view without navigating to a new page.
- Content groups should be of equal importance and similar type.
- Limit to 2–7 tabs for clarity. Order by frequency of use or natural progression.

---

## Tabs vs. similar components

| Component | When to use |
|---|---|
| **Tabs** | Shows adjacent content in the same view — no URL change |
| **Nav Link** | Loads an entirely new screen or page (URL changes) |
| **Menu Item (standalone)** | Scrolls/anchors to a different section within the same page |

Users expect tab content to appear immediately below/beside the tab list. If the experience navigates away, use Nav Link instead. Don't open new tabs/windows unless the UI clearly sets that expectation first.

**Label tabs vs. Illustration tabs:**
- **Do:** Use Label tabs by default — simpler, more space-efficient, better for consistency across experiences.
- **Do:** Use Illustration tabs only for visual differentiation or emphasis when there are very few tabs and there is ample space.
- **Don't:** Use Illustration tabs in compact or space-constrained layouts — the visual weight can feel overwhelming with insufficient breathing room.

**Tab content behavior:**
- **Do:** Only change the content directly associated with the selected tab. Keep all other page content stable.
- **Don't:** Trigger actions or load data that hasn't been requested yet just because a tab is active. Don't let tab changes affect content outside their own panels.

**Make it reliable:**
- **Don't:** Show a disabled tab when content is unavailable — hide it entirely instead. A disabled tab makes the experience unpredictable and leaves users unsure why an option exists.

---

## Anatomy

| Slot | Rule |
|---|---|
| **Label (A)** | Required. Short noun phrase in sentence case. |
| **Icon (B)** | Optional. Helps users interpret the tab. |
| **Indicator (C)** | Marks the selected/current state. |
| **Container (D)** | Supplemental info slot. |
| **Overflow Menu (E)** | Only shows when tab count exceeds available width. |
| **Microspot (F)** | For premium illustrations only. Fixed 32px. |

---

## Types

**Horizontal:**
- **Hug:** Width based on label length. Best for >4 tabs or highly variable label lengths.
- **Fill:** Each tab fills equal width. Best for 2–4 tabs of similar length, equal importance.
- Default left/right label spacing: 16px; minimum 8px.

**Vertical (Web only):**
- Use when horizontal space is generous, or when sections exceed what fits in a row.
- Can also serve as anchor/jump links to sections on a page.
- Vertical tabs scroll within their parent container if height is constrained (scrolling is controlled by parent, not tabs).

**Illustration:**
- Left-right alignment: For limited viewport height (web).
- Top-bottom alignment: For limited viewport width (mobile).

---

## States

States: Enabled, Hover (web only), Active, Current, Current Hover, Current Active.

**No Disabled state.** Never disable a tab when content is unavailable — hide the tab entirely instead. Showing a disabled tab makes the experience unpredictable.

---

## Overflow behavior

**Web:** When tabs exceed container width, a "More" button appears. Overflowed tabs move into a dropdown Menu. When the selected tab is in the overflow, "More" updates to show the selected label. Product teams can manually configure how many tabs show before overflow.

**Mobile (iOS/Android):** Tabs scroll horizontally — no "More" button.

---

## Adaptability

- Tab min-width: 48px (target size).
- RTL: Icons flip to right of label; labels flow right-to-left.
- Each tab must be paired with a tab panel. Switching tabs shows adjacent panel content — not new pages.
- Tabs should not affect content outside their own panels.

---

## Accessibility

**Target size:** 48px tall, variable width.

**Focus behavior:** When focus enters the tab list, it goes to the current tab.

**Keyboard:**

*Tab list navigation:*
- `Tab` — moves focus to the tab list
- `↓` / `→` — move to next tab (wraps to first)
- `↑` / `←` — move to previous tab (wraps to last)

*Overflow:*
- `Tab` — moves focus to the "More" overflow button
- `Space` / `Enter` — expands overflow menu

**Focus indicator:** Must be visible and unobscured. Avoid clipping it with parent containers.

**Name, Role, Value:**

*Tab list:*
- Role: `Tablist` (web) / `UITabBar` (iOS) / `Tabview` (Android)
- Name: provide a meaningful name for the tab group

*Tab item:*
- Role: `Tab`
- Name: use visible text; include text equivalent for any accompanying icon
- Current state: programmatically linked (not part of the label)

*Overflow button:*
- Inherits Button component behavior

*Overflow menu:*
- Inherits Menu component behavior

**Color & Contrast:**
- All default colors meet minimum contrast requirements for light and dark modes.
