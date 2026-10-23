# Entity

**Component:** `Entity SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to visually represent members (people) or other entities (organizations, groups, events, etc.).
- Supports quick recognition and navigation within dense content.
- Always use with supporting context — text, other components, interaction points. Never use an Entity alone.

---

## Types

| Shape | Use for |
|---|---|
| **Circle** | Individual members (people) only. |
| **Square** | All other entities: Company, Group, School, Freelancer, Product, Service, Newsletter, Showcase, Event. |
| **Ghost** | Placeholder when image is unavailable, not provided, or fails to load. Conveys entity type by shape. |

**Shape language is intentional.** Circles = members, squares = everything else. Never swap shapes — this consistency supports navigation and recognition across the platform.

---

## Sizes

Available in 9 sizes for both Circle and Square: `160` · `128` · `96` · `80` · `64` · `48` · `40` · `32` · `24`

Choose size based on context — larger for profile/content headers, smaller for lists and dense layouts.

---

## Placement

- Use as profile headers or content headers — strong visual anchor for identity.
- Use in lists and tables to identify members or entities.
- Always pair with supporting details (name, role, supporting text) and interaction points.

**Keep shape consistent:** Circle = member (person), Square = all other entities. Never swap. This consistency supports navigation and trust across the platform.

**Use in context — never alone.** Entities are high-visibility designs that spotlight individual members and objects. They must always be supported by text and other meaningful elements that provide context. Avoid placing an Entity without accompanying labels, actions, or other components.

---

## Applying Realish fill styles

Realish Fake Entities exposes entity photos as fill styles. Apply them by setting `fillStyleId` directly on the Entity SDUI **instance node** — not on any interior child shape. The component exposes no selectable children at depth > 0.

```js
const style = await figma.importStyleByKeyAsync('REALISH_FILL_STYLE_KEY');
entityInstance.fillStyleId = style.id;
```

---

## Interaction

- Entity is not interactive on its own.
- When used inside `Entity Stack` or `Entity Lockup`, it can be a link navigating to a profile or entity page. Target size is covered by the wrapper component.

---

## Accessibility

**Name, Role, Value:**
- Role: Image.
- Alt text for user-generated content: Construct meaningful alt text using the entity name and relevant descriptors.
  - Person example: `"Virgie Caldwell's profile image"`
  - Company example: `"Flexis"`
- Alt text for ghost entities: Use the entity type as alt text.
  - Examples: `"Person"`, `"Group"`, `"Company"`
- **Avoid redundancy:** If the entity appears alongside a visible text element containing the entity's name, suppress the alt text — the visible text serves as the accessible equivalent.

**Color & Contrast:**
- Ghost entity images contain at least one element meeting minimum contrast for light and dark modes.
- User-generated logos and photos are exempt from LinkedIn's contrast obligations.
