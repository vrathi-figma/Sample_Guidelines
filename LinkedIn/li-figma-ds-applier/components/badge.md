# Badge

**Components:** `Badge SDUI`, `Presence Badge SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## Anatomy

| Slot | Label | Rule |
|---|---|---|
| **Container** | A | The outer shell that positions and sizes the badge relative to its parent element. |
| **Inner Slot** | B | The visual indicator — either a dot, icon, or presence ring depending on badge type. |
| **Counter Text** | C | Optional. Numeric label shown when a count is relevant. Only accepts values 1–99; displays "99+" above that. |

---

## When to use

- Always use in conjunction with another UI element — never place a Badge alone. It is meant to notify users of new or updated information related to the element of interest.
- Use for navigation elements or inline with labels to indicate a specific amount of new or pending notifications.
- **Don't use** Badge color to convey meaning (e.g. caution, negative change in data). Badge Alert is for global navigation only — never repurpose it as a status indicator.
- **Don't use** Badge Count when a text label is needed — use a Tag instead.

**Do:** Use Badge with notification and messaging UI — e.g. a dot on a profile view notification or a count on a Messaging thread.

**Don't:** Don't use Badge color to signal meaning on data metrics (e.g. a red dot next to "-1.3% past 7 days" on an analytics view). Badge color is arbitrary and must not convey status.

---

## Types and when to use each

### Badge Alert
Used exclusively for global navigation, either with navigation icons or Nav Link labels. It is the highest level of notification.
- **Default** (dot): use when a count is not needed
- **Counter**: use to denote a specific number of notifications or status changes

### Badge New
Used in places like **Messaging and Notifications**, appearing inline with blocks of content to show or hint at new available content.
- **Dot**: use in conjunction with a single item or inline with text to indicate there is an update
- **Count**: use when the number is important to know, like the number of unread messages or notifications

### Presence Badge
Used in places like **Messaging, Feed, and Notifications**. Appears with entities to indicate a member is currently active. Does not support a count style.
- Two states: **Active** (solid) and **Available on mobile** (ring)
- Three sizes — match size to the entity it accompanies:
  - **Small**: use with smaller entities, such as the entity on the Messaging bubble overlay
  - **Medium**: use with medium entities, such as the entity in a messaging preview
  - **Large**: use with larger entities, such as the entity at the top of a message in Web

---

## How to configure

**Badge SDUI variants:**
| Property | Values |
|---|---|
| `Type` | `Alert` · `New` |
| `Counter` | `True` · `False` |
| `Size` | `Large` · `Small` |

**Presence Badge SDUI variants:**
| Property | Values |
|---|---|
| `Size` | `Small` · `Medium` · `Large` |
| `Presence` | `Active` · `On Mobile` |

---

## Placement rules

- **Proximity:** Always use in conjunction with a single item to avoid ambiguity about which item is being indicated.
- **Avoid visual collisions:** Place badge on the edge of a lockup. Avoid using a large badge when it might overlap other elements.
- **Badge Alert only:** Strictly positioned to the right of the icon, with an inset of 8px horizontally and 12px vertically. Do not deviate from this.

---

## Badge Count rules

- Use Badge Count to denote a specific number of notifications or status changes — typically smaller in number and personally pointed to the user.
- If no number is passed, accessibility text will read "Some new notifications."
- Count logic: numbers 1–99 show as-is. Above 99 defaults to **99+** (the max, unless teams set their own cap below 99).
- Use Badge Count when the number matters (e.g. unread messages). Use a regular Badge (no count) when the number is unimportant (e.g. new feed content) — the feed updates constantly and a specific count adds no value.

**Do:** Show a count (e.g. "3") on nav icons like Messaging when the number of unread items is relevant to the user.

**Don't:** Don't show an oversized "99+" count badge on a nav icon when the count is not meaningful to the user — use a plain dot badge instead.

---

## Content rules

- Badge Count accepts numeric values only, 1–99.
- Any count above 99 reads "99+" by default.
- A single-digit counter variant is available — any count above 9 reads "9+".
- If the design requires a text label, use a Tag instead.

---

## Interaction

Badges are non-interactive visual indicators tied to interactive elements like buttons or content blocks. Badge appearance is system-dependent and their persistence varies by type. Some badges disappear upon user interaction with the associated UI element; others remain visible. Do not attempt to manually replicate this behavior.

---

## Adaptability

Badge Count counter text and container must not wrap. In tight spaces, badges truncate to "9+" or dot instead of "99+" — this is expected.

---

## Internationalization

- Badge count numbers maintain Left-to-Right (LTR) order even in RTL contexts. The Unicode bidirectional algorithm handles this automatically. Example: "99" remains "99" in both LTR and RTL.
- For other languages, use Locale-Aware Formatting (Intl.NumberFormat for JS; equivalent locale-aware APIs for native platforms).

---

## Accessibility requirements

**Name, Role, Value:**
Badge information is always integrated into the a11y label of the associated UI element — never attached as a hint or description (e.g. aria-describedby). If the UI element is a control, the control name comes first; Badge information is appended.

Default a11y label pattern: state the count (if any) followed by the word "new".

| Badge type | Role | A11y label example |
|---|---|---|
| Badge Alert (Default) | none | "Home, new" |
| Badge Alert (Count) | none | "Messaging, more than 99 new notifications" |
| Badge New (Dot) | none | "Suman Gupta, new" |
| Badge New (Count) | none | "Messages, 3 new" |

**Color & Contrast:**
All default colors meet or exceed minimum contrast requirements for both light and dark modes. Colors are arbitrary and context-dependent — never use badge color to convey meaningful information.
