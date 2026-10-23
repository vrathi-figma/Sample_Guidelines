# Elevation Tokens

**Library:** DS Typography 2.0 — effect styles

---

## Overview

Elevation is applied via named effect styles. Never hardcode box-shadow values — always use one of the styles below.

---

## Effect styles

### Raised
Default elevation for cards, panels, and surfaces that sit above the page background.

| Layer | X | Y | Blur | Spread | Color |
|---|---|---|---|---|---|
| Shadow 1 | 0 | 0 | 1 | 0 | `color-shadow-supplemental` |
| Shadow 2 | 0 | 4 | 12 | 0 | `color-shadow` |

### Raised Active
Use for the pressed/active state of a raised surface (e.g. a card that is being tapped).

| Layer | X | Y | Blur | Spread | Color |
|---|---|---|---|---|---|
| Shadow 1 | 0 | 0 | 1 | 0 | `color-shadow-supplemental` |
| Shadow 2 | 0 | 3 | 9 | 0 | `color-shadow` |

### Raised Faint
Subtler elevation — use when a surface needs to be lifted but with less visual weight than Raised.

Apply via effect style: `Raised Faint`

### Raised Active Faint
Pressed/active state of a Raised Faint surface.

Apply via effect style: `Raised Active Faint`

---

## Default: no elevation

**Containers and cards default to no elevation.** Do not apply a shadow unless the surface genuinely needs to feel lifted above surrounding content.

To distinguish a surface from its background without elevation, use a `1px` stroke with `color-border-faint`. This is the correct treatment when a surface and its background share the same color token (e.g. `color-background` on `color-background`) — the border creates separation without adding visual weight.

**Do:** Use `color-border-faint` stroke to separate a card from a same-color background.
**Don't:** Default to elevation just to make a card visible — reach for the border approach first.

## When to use elevation

Only apply an elevation style when the surface must feel physically lifted — overlays, popovers, dropdowns, and modals that float above page content.

| Style | Use for |
|---|---|
| `Raised` | Popovers, dropdowns, modals — surfaces that float above the page |
| `Raised Active` | Active/pressed state of a Raised surface |
| `Raised Faint` | Surfaces that need subtle lift without drawing attention — secondary panels, inline overlays |
| `Raised Active Faint` | Active/pressed state of a Raised Faint surface |

---

## Rules

- Always apply elevation as an effect style — never as a manually entered box-shadow
- The two shadow layers (`color-shadow` + `color-shadow-supplemental`) are composed into the named style — do not apply them individually
- Elevation applies to the surface itself, not to child elements within it
- When in doubt between elevation and a border, use the border (`color-border-faint`) — elevation is the exception, not the default

---

## Effect style keys (DS Typography 2.0)

Use `importStyleByKeyAsync(key)` and set `effectStyleId` on the node. Never hardcode drop-shadow values.

```js
const style = await figma.importStyleByKeyAsync(key);
node.effectStyleId = style.id;
```

| Style | Key |
|---|---|
| `Raised` | `bafc1250b580de43f4c73d851c7801757f802750` |
| `Raised Active` | `03ac872e6ac13e4c95f5787b0db439bf593e110e` |
| `Raised Faint` | `2a2e938385f36dac4864b4d446e5c6b8e6b841d5` |
| `Raised Faint Active` | `29df8b72f81aab0d8b1bc2c79cc6f897db29e984` |

Default for cards and panels: `Raised`.
