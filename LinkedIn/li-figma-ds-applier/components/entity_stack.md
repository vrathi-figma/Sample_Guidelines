# Entity Stack

**Component:** `Entity Stack SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to summarize a group of related entities in a compact format — mutual connections, event attendees, companies hiring for a job, group members.
- Great for confined spaces where listing entities individually would be too heavy.
- Always pair with supporting text that describes the relationship (e.g. "25 mutual connections"). Never use alone.
- Rollup count always needs a text description alongside it.

---

## How to configure

**Types:**
| Type | Use for |
|---|---|
| Circle | Members (people) only |
| Square | All other entities: Company, School, Group, Event, etc. |
| Mixed | Combination — circles strictly for people, squares for everything else |

**Stacked vs Unstacked:**
| Layout | When to use |
|---|---|
| Stacked | Overlapping entities. Limited space; stack serves as entry point to full list. |
| Unstacked | Side-by-side entities. When showcasing top-level entities without obscuring images. |

**Sizes (entity size):** `64` · `48` · `40` · `32` · `24` · `16`

**Rollup:**
- Default: shows 3 entities + rollup count (`+n`).
- Example: 5 entities → shows 3 + `+2`.
- 100+ entities: labeled as `99+`.
- Size 16 exception: SPS context only — no rollup text, max 5 sources visible.

---

## Best practices

**Mixed Entity Stacks — circles for individuals only:**

**Do:** In a mixed stack, use circles for individuals and squares for companies/groups/institutions.
**Don't:** Use circles for non-person entities in a mixed stack — this undermines user trust and the visual language system.

---

**Never use alone — always provide context:**

**Do:** Pair an Entity Stack with supporting text (e.g. "122 mutual connections").
**Don't:** Show just the stack and a count (+2) with no descriptive label.

**Do:** In an overview section, combine an Entity Stack with the names of the contributors (e.g. "Top Contributors" + entity photos + listed names).
**Don't:** Show the stack and count without the supporting names or label.

---

**Rollup needs context:**

**Do:** "Arianne, Filip, and 15 others you know followed" — describes who and what the number means.
**Don't:** Show "15+" with no supporting text — the number alone is meaningless.

---

## Interaction

- Entity Stack is not interactive on its own.
- Typically used as part of a larger interactive pattern (e.g. clicking the row reveals the full entity list).

---

## Adaptability

- Max 3 entities always visible, regardless of zoom level.
- Rollup count font scales to maintain readability at higher zoom levels.

---

## Accessibility

**Name, Role, Value:**
- Role: Image. Alt text is typically suppressed when accompanying text describes the group.
- If no accompanying text, provide alt text describing the entities shown.

**Color & Contrast:**
- Ghost entity elements meet minimum contrast for light and dark modes.
- User-generated images are exempt from contrast requirements.
