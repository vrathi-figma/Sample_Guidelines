# Entity Grid

**Component:** `Entity Grid SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to display a compact 2×2 grid of multiple entities in a contextual insight (e.g. mutual connections, group members, event attendees).
- Must be paired with accompanying text that describes the group — never use alone.

---

## How to configure

**Variants:**
| Property | Values |
|---|---|
| `Size` | `48` · `56` *(56 deprecated)* |
| `Type` | `Circle` · `Square` · `Mixed` |
| `Number of Entities` | `2` · `3` · `4` · `5+` |

**Grid composition (size 48):**
| Count | Layout |
|---|---|
| 2 entities | 2× size 32, stacked with visible gap |
| 3 entities | 3× size 24 in 2 rows |
| 4 entities | 4× size 24 in 2 rows |
| 5+ entities | 2× size 24 in row 1 + rollup count in row 2 |

**Rollup count format:**
- 5–101 entities beyond visible: `+n`
- 102+ entities: `n+` or `99+`
- Minimum of 3+ for rollup to appear.

---

## Types

- **Circle Grid:** Members (people) only.
- **Square Grid:** All other entities — Company, School, Group, Event, etc.
- **Mixed Grid:** Combination of Circle and Square entities. Circles must remain strictly for people.

---

## Interaction

- Entity Grid is not directly interactive.
- Used as a supporting element within a larger interactive experience (e.g. a message thread row).
- When interacted with (as part of the parent), the full list of entities should be displayed.

---

## Accessibility

**Name, Role, Value:**
- Role: Image. Alt text is typically suppressed since accompanying text describes the group.
- If no accompanying text is present, provide meaningful alt text describing the entities.

**Color & Contrast:**
- Ghost entity elements meet minimum contrast for light and dark modes.
- User-generated images are exempt from contrast requirements.
