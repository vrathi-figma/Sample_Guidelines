# Thread DS — AI Context File

This file gives AI tools (GitHub Copilot, Claude, Loveable, and others) the context they need to generate Thread DS-aware code, tokens, and component suggestions. It is the authoritative reference for naming conventions, token structure, component architecture, and contribution rules.

---

## What is Thread DS?

Thread DS is the ASOS design system. It is:

- Built and maintained in Figma (variables, components, text styles, icons)
- Exported to this GitHub repository via the Thread DS Figma plugin
- Consumed by product teams across web (React), iOS (Swift), and Android
- Governed by a contribution model with three tiers (tokens, variants, new components)

The design system is named **Thread** and uses the tagline **Thread 🧵 DS**.

---

## Repository structure

```
packages/
  tokens/
    exports/
      figma-variables.json        # All Figma variables (global, alias, semantic)
docs/
  figma-make/
    components.json               # All component sets with variant metadata
    component-anatomy.json        # Component structure and layout
    component-render-specs.json   # Component SVG thumbnails + variant specs
    text-styles.json              # All text styles
    icons.json                    # All icon component sets
    icons.index.json              # Icon groups index
    icons/groups/*.json           # Per-group icon files
    design-contract.json          # Master manifest of all exports
figma-plugin/
  thread-ds-sync/                 # Thread DS Figma plugin source
```

---

## Design token architecture

Thread DS uses a three-tier token system. **Always reference semantic tokens in components — never raw globals.**

### Tier 1 — Global tokens (`_1. Global` collection)

Raw foundational values. Never use these directly in components.

Examples:
- `neutral/100` — a raw neutral colour value
- `accent/600` — a raw accent colour value
- `scale/400` — a raw spacing scale value

### Tier 2 — Alias tokens (`2. Alias` collection)

Named aliases that map to globals. Used to build the semantic layer.

### Tier 3 — Semantic tokens (collections 3–11)

Purpose-driven tokens that components must use. These are what engineers and designers should reference.

---

## Token naming convention

Format: `category/context/role`

All lowercase. Slash-separated. No spaces. Hyphens within segments where needed.

### Colour tokens (`3. Colour` collection)

#### Surface tokens
Used for background fills on components and layouts.

```
surface/base/canvas              # Primary page background
surface/base/raised              # Cards, panels, grouped content
surface/base/subtle              # Low-emphasis background
surface/base/inverted            # Dark/inverted surfaces
surface/base/overlay-black       # Modal scrims, dimming overlays

surface/action/primary           # Primary button default
surface/action/primary-hover     # Primary button hover
surface/action/secondary         # Secondary button default
surface/action/secondary-hover   # Secondary button hover
surface/action/accent-primary    # Accent CTA (e.g. Add to Bag)
surface/action/accent-primary-hover
surface/action/disabled          # Disabled state for any action

surface/decision/primary         # High-emphasis semantic surface
surface/decision/secondary       # Lower-emphasis semantic surface
surface/decision/success         # Success states
surface/decision/error           # Error/validation states
surface/decision/warning         # Warning/caution states
surface/decision/information     # Informational messages
surface/decision/neutral         # Non-critical contextual surfaces
surface/decision/invert          # Inverted semantic surfaces
```

#### Text tokens
Used for type colour. Always pair with the correct surface token.

```
text/base/primary                # Default body text
text/base/secondary              # Supporting/muted text
text/base/on dark                # Text on dark surfaces
text/base/on colour              # Text on coloured surfaces
text/action/primary              # Primary button label text
text/action/secondary            # Secondary button label text
text/action/disabled             # Disabled action text
text/decision/primary            # Semantic text (default)
text/decision/on light           # Semantic text on light surfaces
text/decision/on colour          # Semantic text on coloured surfaces
```

#### Icon tokens
Used for icon colour fills.

```
icon/base/primary
icon/base/secondary
icon/base/on light
icon/base/on dark fixed
icon/base/on colour
icon/action/primary
icon/action/primary-hover
icon/action/secondary
icon/action/accent-primary
icon/decision/success
icon/decision/error
icon/decision/warning
icon/decision/information
icon/decision/focus
icon/decision/pressed
icon/decision/on dark
```

#### Border tokens
Used for strokes on components.

```
border/base/subtle               # Low-emphasis separators
border/base/strong               # High-emphasis boundaries
border/action/primary            # Primary interactive border
border/action/primary-hover
border/action/secondary
border/action/accent-primary
border/action/accent-primary-hover
border/decision/primary          # Semantic border
border/decision/focus            # Focus ring
border/decision/invert           # Semantic border on inverted surfaces
```

### Typography tokens (`4. Typography` collection)

Format: `font-size/role/variant`, `font-weight/role/variant`, `line-height/role/variant`, `letter-spacing/role/variant`

### Spacing tokens (`5. Spacing and Padding` collection)

Format: `padding/component/direction/size`

Examples:
- `padding/button/horizontal/small`
- `padding/button/horizontal/large`
- `padding/button/vertical/large`

### Shape tokens (`6. Shape` collection)

Format: `shape/radius/size`

### Elevation tokens (`7. Elevation and Shadows` collection)

```
elevation/light
elevation/medium
elevation/heavy
shadows/none
shadows/x-light
shadows/light
shadows/medium
shadows/heavy
```

### Layout tokens (`8. Layout` and `9. Breakpoints` collections)

```
breakpoint/xx-sm
breakpoint/l
```

---

## Colour modes

Thread DS supports **Light** and **Dark** themes via Figma modes. All semantic tokens automatically adapt. When implementing in code, reference the semantic token — never hardcode a hex value.

---

## Typography system

Thread DS uses **Futura PT** as the primary typeface across all platforms.

Text style naming format: `Category/Role Variant`

Key text styles:

```
# Display
Display/Hero
Display/Large
Display/Medium
Display/Small

# Body
Body/Large
Body/Default
Body/Small
Body/Compact (Android)

# Labels
Label/Button               # 16px Heavy, 0.6px tracking — buttons only
Label/Button Small         # 14px Heavy — compact buttons only
Label/Button Description   # 14px Book — supporting button copy
Label/Tab                  # 14px Heavy — tab navigation
Label/Tab Small            # 12px Heavy — compact tabs
Label/Tag                  # 12px Heavy — tag components
Label/Tag Large            # 14px Heavy — large tags
Label/Tag Emphasis         # 12px Heavy — emphasis tags
Label/Tag Emphasis Large   # 14px Heavy — large emphasis tags
Label/Status               # 14px Heavy — order/status indicators
Label/Status Small         # 10px Heavy — compact status
Label/Accordion            # 16px Heavy — accordion headers
Label/Field Input          # 12px Heavy — input field values
Label/Field Select         # 12px Heavy — select field values
Label/Field Select Large   # 16px Book — large select values
Label/Field Group          # 14px Heavy — grouped field headings
Label/Field Option         # 16px Book — dropdown/radio/checkbox options

# Field support
Field/Description          # 16px Book — field context copy
Field/Helper               # 16px Book — validation/helper text
```

---

## Component library

Components are named in lowercase kebab-case. Variant properties use PascalCase.

### Core components

| Component name | Key variants | States |
|---|---|---|
| `button` | Type: Primary, Secondary, Tertiary, Accent Primary, Accent Secondary | Default, Hover, Disabled |
| `input.field` | — | Default, Focus, Error |
| `select` | — | Default, Focus, Error |
| `tag` | — | Default, Hover, Selected |
| `radio` | Selected: True/False, WithLabel: True/False | — |
| `status-bar` | Stage: Success 1, Success 2, Success 3, Warning | — |
| `web/modals` | Platforms: Desktop/Mobile, CTA: 1 CTA/2 CTAs, Image: True/False | — |
| `icon.button.save` | — | — |
| `badge` | Type: Half-Pill, Discount, New, Social Half-Pill; Size: Default/Large; Filled: True/False; Invert: True/False | — |

### Component rules

- Component sets are named in lowercase kebab-case: `notification-card`, `input.field`, `status-bar`
- Variant properties are PascalCase: `Type`, `State`, `Size`, `Filled`, `Invert`
- Variant values are Title Case: `Primary`, `Default`, `True`, `False`
- All fills must reference semantic tokens — never raw globals or hex values
- All spacing must reference `padding/*` or `spacing/*` tokens
- All radii must reference `shape/radius/*` tokens
- Text layers must use a published Thread DS text style

---

## Icon system

Icons are named using a slash-separated group/name format: `GroupName/icon-name`

This distinguishes them from components (which never contain a slash in their name).

Icons are grouped by category. Each group has a corresponding file at `docs/figma-make/icons/groups/{group-id}.json`.

---

## Figma file links

- **Tokens:** `figma.com/design/9iK6QBbPYLovLw9QEf7bmh/Tokens-Thread-DS-ASOS`
- **Components:** `figma.com/design/FJvN3Nf3cHaQifmwLhiyjM/Components-Thread-DS-ASOS`
- **Icons:** `figma.com/design/kXz9SltcUqECfH3OtQRq3m/Icons-Thread-DS-ASOS`

---

## Contribution model

### Three tiers

**Tier 1 — Token request** (lowest complexity)
New semantic or component tokens, or changes to existing token values.
- Submit via the Thread DS Figma plugin → Request a token
- Creates a GitHub issue with labels `token-proposal` and `tier-1`
- DS team triages within 5 working days

**Tier 2 — Component variant** (medium complexity)
Adding a new variant to an existing component.
- Requires a Figma exploration in the Thread DS Sandbox file
- Submit via GitHub issue with label `component-variant`

**Tier 3 — New component** (highest complexity)
Net new components that don't exist in Thread DS.
- Requires evidence of reuse across ≥2 products
- Requires a Design Decision Record (DDR)
- Submit via GitHub issue with label `component-proposal`

### Governance rules

- No new globals without DS team sign-off
- All component tokens must alias a semantic token — never a global directly
- Naming conventions are enforced before merge
- Components must pass a token audit (no raw values) before review
- Every new component requires a description in the correct format

---

## Code usage guidance

### React / TypeScript

When generating React components that consume Thread DS:

```tsx
// ✅ Correct — reference the CSS variable for a semantic token
style={{ backgroundColor: 'var(--surface-action-primary)' }}

// ✅ Correct — use the token name as a CSS custom property
className="bg-surface-action-primary"

// ❌ Wrong — never hardcode hex values
style={{ backgroundColor: '#2D2D2D' }}
```

Token names map to CSS custom properties by replacing `/` with `-`:
- `surface/action/primary` → `--surface-action-primary`
- `text/base/primary` → `--text-base-primary`
- `border/action/primary` → `--border-action-primary`

### When suggesting tokens for a use case

| Use case | Correct token |
|---|---|
| Page/screen background | `surface/base/canvas` |
| Card or panel background | `surface/base/raised` |
| Primary button fill | `surface/action/primary` |
| Primary button text | `text/action/primary` |
| Success banner background | `surface/decision/success` |
| Error state border | `border/decision/focus` |
| Body text colour | `text/base/primary` |
| Muted/secondary text | `text/base/secondary` |
| Icon on a dark surface | `icon/base/on dark fixed` |
| Disabled component fill | `surface/action/disabled` |

---

## What AI tools should NOT do

- Never suggest hardcoded hex values for colours — always use semantic tokens
- Never reference `_1. Global` tokens directly in components — always go through semantic
- Never create new token names that don't follow the `category/context/role` format
- Never suggest a new component when an existing component with a new variant would suffice
- Never use Futura PT alternatives — this is the brand typeface and not negotiable
- Never generate component variant names in lowercase — use PascalCase for property names and Title Case for values

---

## Maintained by

Thread DS is maintained by the ASOS Product Design team.
Plugin and tooling: David Flynn
Repository: `github.com/asosteam/asos-productdesign-thread-design-system`
Figma plugin: Thread DS (published to Figma Community)

Last updated: June 2026
