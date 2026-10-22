# Icons for Figma Make kit

## Icons

All icons use Font Awesome Pro. Never use lucide-react, heroicons, or any other  
icon library. Never render icons as inline SVG.

## Packages

@fortawesome/fontawesome-svg-core @fortawesome/react-fontawesome @fortawesome/pro-solid-svg-icons @fortawesome/pro-regular-svg-icons @fortawesome/sharp-solid-svg-icons @fortawesome/sharp-regular-svg-icons @fortawesome/pro-duotone-svg-icons

## Import pattern

```js
```tsx
import { FontAwesomeIcon } from '@fortawesome/react-fontawesome'
import { faSearch } from '@fortawesome/sharp-solid-svg-icons'

<FontAwesomeIcon icon={faSearch} />
```

## Style selection rules

| Use case | Package | Prefix |
| --- | --- | --- |
| Default — all UI icons | `@fortawesome/sharp-solid-svg-icons` | `fass` |
| Secondary / lower emphasis | `@fortawesome/sharp-regular-svg-icons` | `fasr` |
| Fallback if sharp variant unavailable | `@fortawesome/pro-solid-svg-icons` | `fas` |
| Softer contexts (tooltips, helper text) | `@fortawesome/pro-regular-svg-icons` | `far` |
| Empty states and illustrations only | `@fortawesome/pro-duotone-svg-icons` | `fad` |

**Default to sharp-solid for every icon unless a reason to deviate is present.** Never mix styles within the same component or surface.

## Naming convention

Font Awesome icon names are camelCase with a `fa` prefix matching the style:

```js
// sharp-solid (default)
import { faTrashCan } from '@fortawesome/sharp-solid-svg-icons'

// sharp-regular
import { faTrashCan } from '@fortawesome/sharp-regular-svg-icons'

// duotone
import { faBoxOpen } from '@fortawesome/pro-duotone-svg-icons'
```

When two styles export the same name, alias the import to avoid collisions:

```js
import { faTrashCan as faTrashCanRegular } from '@fortawesome/sharp-regular-svg-icons'
import { faTrashCan as faTrashCanSolid } from '@fortawesome/sharp-solid-svg-icons'
```

## Sizing

Use the `size` prop — never set `fontSize` or `width/height` directly on the icon.

| Prop value | Rendered size | When to use |
| --- | --- | --- |
| `"xs"` | 0.75rem | Dense UI, badges |
| `"sm"` | 0.875rem | Inline with small text |
| *(none)* | 1rem | Default — matches body text |
| `"lg"` | 1.25rem | Buttons, input adornments |
| `"xl"` | 1.5rem | Section headers |
| `"2x"` | 2rem | Empty state supporting icons |
| `"3x"`–`"5x"` | 3–5rem | Duotone illustration icons only |

## Color

Never set color directly on `<FontAwesomeIcon>`. Inherit from the parent's `color` property via CSS, or wrap in a `<span>` with a Tailwind text utility:

```html
// Correct
<span className="text-muted-foreground">
  <FontAwesomeIcon icon={faCircleInfo} />
</span>

// Wrong
<FontAwesomeIcon icon={faCircleInfo} color="#717182" />
```

For duotone icons, control the two layers via CSS custom properties:

```
<FontAwesomeIcon
  icon={faBoxOpen}
  style={{
    '--fa-primary-color': 'var(--primary)',
    '--fa-secondary-color': 'var(--muted-foreground)',
    '--fa-secondary-opacity': '0.4',
  } as React.CSSProperties}
/>
```

## Empty states

Always use duotone icons for empty state illustrations. Pair with a primary layer color matching the context (error → `--destructive`, neutral → `--primary`) and a secondary layer at 30–40% opacity.

```
// Example empty state icon
<FontAwesomeIcon
  icon={faFolderOpen}        // from pro-duotone-svg-icons
  size="4x"
  style={{
    '--fa-primary-color': 'var(--primary)',
    '--fa-secondary-color': 'var(--muted-foreground)',
    '--fa-secondary-opacity': '0.35',
  } as React.CSSProperties}
/>
```

## What not to do

- Do not use `fasl` / `fat` (light, thin) — not in our licensed set
- Do not use `fixedWidth` unless icons are in a list or nav that requires alignment
- Do not wrap icons in `<i>` tags — always use `<FontAwesomeIcon>`
- Do not guess icon names — verify against the Font Awesome icon search at [fontawesome.com/icons](http://fontawesome.com/icons)

## Icon vocabulary

```
## Icon vocabulary

When one of these use cases applies, always use the specified icon — do not
substitute a visually similar alternative.

### Navigation icons
Used in navigation components (e.g. menu). Represent concepts or objects.

| Icon name | Style | Package | camelCase import | When to use |
|---|---|---|---|---|
| `user` | solid | `@fortawesome/pro-solid-svg-icons` | `faUser` | Profile |
| `user-group` | solid | `@fortawesome/pro-solid-svg-icons` | `faUserGroup` | Users |
| `check-square` | sharp-solid | `@fortawesome/sharp-solid-svg-icons` | `faCheckSquare` | Roles |
| `truck` | sharp-solid | `@fortawesome/sharp-solid-svg-icons` | `faTruck` | Organizations |
| `money-bill-transfer` | solid | `@fortawesome/pro-solid-svg-icons` | `faMoneyBillTransfer` | Product: Billing Management |
| `warehouse-full` | solid | `@fortawesome/pro-solid-svg-icons` | `faWarehouseFull` | Product: 3PL Management |
| `cart-flatbed-boxes` | solid | `@fortawesome/pro-solid-svg-icons` | `faCartFlatbedBoxes` | Product: Order Management |
| `chart-network` | solid | `@fortawesome/pro-solid-svg-icons` | `faChartNetwork` | Product: Network Management |
| `shelves` | solid | `@fortawesome/pro-solid-svg-icons` | `faShelves` | Product: Warehouse Management |
| `cart-shopping-fast` | solid | `@fortawesome/pro-solid-svg-icons` | `faCartShoppingFast` | Product: Integration Management |
| `shop` | solid | `@fortawesome/pro-solid-svg-icons` | `faShop` | Product: Fulfillment Marketplace |
| `user-plus` | solid | `@fortawesome/pro-solid-svg-icons` | `faUserPlus` | Product: Signup |
| `chart-mixed` | solid | `@fortawesome/pro-solid-svg-icons` | `faChartMixed` | Product: Business Analytics |
| `barcode-read` | solid | `@fortawesome/pro-solid-svg-icons` | `faBarcodeRead` | Product: Smart Scan |
| `calculator` | solid | `@fortawesome/pro-solid-svg-icons` | `faCalculator` | Product: Accounting Integration |
| `mobile-screen-button` | solid | `@fortawesome/pro-solid-svg-icons` | `faMobileScreenButton` | Product: Warehouse Management Mobile |

### Action icons
Used in interactive components (buttons, row actions, etc.). Represent actions.

| Icon name | Style | Package | camelCase import | When to use |
|---|---|---|---|---|
| `ellipsis-vertical` | solid | `@fortawesome/pro-solid-svg-icons` | `faEllipsisVertical` | To open a menu of actions |
```
