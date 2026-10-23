# Anti-patterns — li-figma-ds-applier

Encoded failure modes. The skill reads this file at Step 1 of every invocation.

When you are about to do any of the following, stop and re-read the linked rule. Each entry was added because the same failure surfaced repeatedly during real generation.

---

## Components

### `renamed-instance`

Calling `instance.name = '...'` on any imported component, icon, or illustration.

**Why it fails:** Detaches the instance's display name from its library origin. In inspection, the node becomes indistinguishable from a custom frame. The library component name is the source of truth — leave it as-is.

→ See: Rule 1 — Components

### `reconstructed-component`

Recreating an SDUI component or any of its variants from scratch — e.g. building a custom red border instead of using the input component's built-in error variant.

**Why it fails:** Loses all encoded states, accessibility metadata, and library updates. The visual approximation will drift from the source over time.

→ See: Rule 1 — Components

### `raw-shape-entity`

Applying a Realish fill style to a raw rectangle or ellipse instead of using an entity component.

**Why it fails:** There is no fallback path. A correctly-shaped raw rectangle is not an entity in the inspection tree, even if it looks right.

→ See: Rule 1 — Components, Rule 6

### `ghost-entity`

Leaving the default ghost image inside an entity lockup component **in Thinking mode**.

**Why it fails:** Ghost defaults exist so that components can render before content is wired in. In Thinking mode, always replace with the matching Realish photo unless the scenario explicitly calls for a missing photo (new member without a profile photo, company with no logo on file).

**Flash mode exemption:** Ghost photos are the expected Flash default — do not import Realish fills in Flash mode. See `search-for-realish-in-flash`.

→ See: Rule 6

### `component-set-vs-single`

Calling `importComponentByKeyAsync(key)` on a key that points to a component **set** (component with variants).

**Why it fails:** Component sets must be imported via `importComponentSetByKeyAsync` — the single-component API throws `Component with key "..." not found` on set keys. Many SDUI components are sets (Top/Bottom Navigation Mobile, Entity Lockup, Button, etc.). `components/index.md` doesn't currently flag which keys are sets, so the safest pattern is: default to `importComponentSetByKeyAsync` for any component that has variants, then pick `set.children[0].createInstance()` (or a specific variant by `variantProperties`).

→ See: Rule 1 — Components

### `text-slot-set-by-index`

Setting text on an imported instance by iterating `findAll(n => n.type === 'TEXT')` and assigning values by array index.

**Why it fails:** The text-node count and order are component-internal and not guaranteed. Entity Lockup, for example, has **six** text slots (`Firstname Lastname`, `•`, `Degree`, `Text`, `Subheading`, `Timestamp`) — not three. Setting by index overwrites the wrong slots (e.g. clobbering the bullet `•` with a headline). Fix: match by `node.name` (or, better, use the component's exposed text **properties** via `instance.componentProperties` + `instance.setProperties({...})` when the design system exposes them). When in doubt, log `textNodes.map(n => n.name)` once to discover the slot layout.

→ See: Rule 1 — Components, Step 5

---

## Icons & illustrations

### `text-glyph-as-icon`

Using a text character or Unicode emoji as a substitute for an icon. This includes:
- ASCII / typographic glyphs: `✕`, `×`, `+`, `>`, `—`
- Unicode emoji: 🌐, 🔍, ⚙️, ➕, ❤️, and any other emoji codepoint

**Why it fails:** No text fallback exists. Emoji also render inconsistently across platforms and OS versions, so they can't double as iconography. All medium icons are pre-documented; import from the DS Icons Library by key.

→ See: Rule 1 — Icons

### `custom-linkedin-logo`

Constructing a LinkedIn logo, wordmark, or inbug from scratch.

**Why it fails:** Brand assets have strict rules. Always source from the nav component or the DS Icons Library.

→ See: Rule 1 — LinkedIn logo and inbug

### `search-for-icons-or-illustrations`

Running `search_design_system` for icons or illustrations.

**Why it fails:** All keys are pre-documented in `foundations/icons.md` and `foundations/illustrations.md`. `search_design_system` is the slowest operation in the toolkit; using it speculatively for assets we already have keys for is pure latency cost.

→ See: Rule 1 — Icons, Illustrations

### `repeated-illustration`

Using the same Spot or Microspot illustration twice within a single group (row of cards, list).

**Why it fails:** Visual monotony — readers stop perceiving the illustrations as content.

→ See: Rule 1 — Illustrations

---

## Tokens & variables

### `hardcoded-numbers`

Using a raw pixel value, hex color, or numeric spacing on a non-component node.

**Why it fails:** Bypasses the DS token system. Only `0` and `auto` are acceptable raw values; everything else must be bound to a variable.

→ See: Rule 2 — No Hardcoded Values

### `unbound-itemspacing`

Leaving `itemSpacing` as a raw number on an auto-layout frame.

**Why it fails:** `itemSpacing` is a spacing token, not a layout setting. Treat it identically to `paddingTop`/`paddingLeft`/etc.

→ See: Rule 2

### `name-string-variable-lookup`

Discovering variables by collection name or by string-filtering the variable name.

**Why it fails:** The library name format is not guaranteed to match what your code expects, and the call will silently fail. Always use `importVariableByKeyAsync(key)` with pre-documented keys.

→ See: Rule 2

### `hardcoded-hex-fallback`

Falling back to a raw hex value (or any raw number) when a variable bind fails.

**Why it fails:** Hides the failure and produces a non-compliant design. Stop and ask the designer instead — there is no acceptable hardcoded fallback.

→ See: Rule 2, Rule 3

### `raw-zero-padding`

Writing `node.itemSpacing = 0` or `node.paddingTop = 0` / `paddingBottom`/`Left`/`Right` as an explicit assignment.

**Why it fails:** Rule 2 carves out `0` and `auto` as fine-as-is, but the DS Token Lint hook (`lint-figma-tokens.sh`) blocks the literal `= 0` assignment on padding/itemSpacing regardless — it pattern-matches `[0-9]` and treats `= 0` the same as any raw px value. The PreToolUse hook will fail the whole `use_figma` call before any code runs. Workaround: **don't write the assignment at all.** Newly-created auto-layout frames already default to `0` padding and `0` itemSpacing. Only assign these properties when you're binding to a non-zero token via `setBoundVariable`.

→ See: Rule 2, Step 6 — Validate Before Completing

---

## Color

### `new-color-variable`

Creating a new color variable when no matching DS token exists.

**Why it fails:** New variables fragment the system. Stop and ask the designer before proceeding.

→ See: Rule 3 — Color

### `hex-from-rgba`

Converting an `rgba()` transparency value to hex.

**Why it fails:** Hex loses the alpha channel. Keep transparency as `rgba()`.

→ See: Rule 3

---

## Typography

### `raw-font-properties`

Setting `fontName`, `fontSize`, `lineHeight`, or `letterSpacing` directly on a text node.

**Why it fails:** Produces detached text — no link back to a named DS style. Always set `textStyleId` after `importStyleByKeyAsync(key)`.

→ See: Rule 4 — Typography

### `font-property-helper`

Writing helper functions that wrap raw font properties (e.g. `makeText(chars, family, style, size, lh)`).

**Why it fails:** Bypasses `textStyleId` entirely. The correct pattern is: import the style by key → set `textStyleId` → set `characters`. A helper that takes raw font props will always produce detached text.

→ See: Rule 4

### `base-dimension-tokens-in-text`

Using `font-size-small`, `line-height-default`, or any base dimension token directly on a text node.

**Why it fails:** Those are implementation internals that named text styles already compose. Use the named style.

→ See: Rule 4

### `inter-font-default`

Preloading `Inter` (any weight) and assuming DS Typography 2.0 styles will resolve against it.

**Why it fails:** DS Typography 2.0 uses **SF Pro** — `SF Pro Text` for most styles, `SF Pro Display` for the Display group. Inter is not the system font. Defaulting to Inter causes the first `set_characters` call after applying a `textStyleId` to throw `Cannot write to node with unloaded font "SF Pro Text Regular"`, killing the batched Flash build mid-flight. Always preload SF Pro Text + SF Pro Display weights in the start-of-call `Promise.all`. Inter may be loaded as a backup, never as the primary.

→ See: Rule 4 — Typography, `foundations/typography.md` → Fonts

---

## Elevation

### `shadow-on-static-card`

Applying an elevation effect to a card or container that does not float above surrounding content.

**Why it fails:** Elevation is reserved for overlays, popovers, dropdowns, modals. For same-color separation, use a `1px color-border-faint` stroke instead.

→ See: Rule 5 — Elevation

### `hardcoded-shadow`

Setting drop-shadow values directly on a node instead of applying `effectStyleId` from DS Typography 2.0.

**Why it fails:** Bypasses the effect style system. Even when an import "seems unavailable," do not fall back to raw shadow values — stop and report instead.

→ See: Rule 5

---

## Content & entities

### `invented-entity`

Making up a person name, company name, avatar, or logo from scratch.

**Why it fails:** Realish Fake Entities is the source of truth for system-generated content. Inventing data breaks continuity and makes the design feel ad-hoc.

→ See: Rule 6

### `repeated-entity-in-list`

Using the same entity for multiple items in a list or feed of the same type **in Thinking mode**.

**Why it fails:** Visual monotony and unrealistic data shape. Use different entities for each row.

**Flash mode exemption:** Flash uses ghost photos for everything and does not differentiate per-row content — this anti-pattern does not apply.

→ See: Rule 6

### `search-for-realish-in-flash`

Running `search_design_system` for Realish fill styles while in Flash mode (e.g. searching `Realish Person Ayaka` or `Realish Company Flexis`).

**Why it fails:** Flash mode skips Realish entirely. The built-in ghost photos inside entity components are the Flash default. Searching for Realish adds latency and re-introduces the iteration Flash mode is designed to avoid.

→ See: Rule 6 — Flash mode entity defaults

### `realish-fillstyleid-override-in-flash`

Calling `node.fillStyleId = <realish-style>.id` on any node inside an entity component while in Flash mode.

**Why it fails:** Flash entity defaults are ghost photos. Overriding fillStyleId means importing a Realish style first (which Flash mode forbids), and then traversing the instance tree to find the right node — both expensive operations. Keep ghost defaults.

→ See: Rule 6 — Flash mode entity defaults

---

## Generation procedure

### `children-before-sizing`

Appending children to an auto-layout frame before `layoutMode`, sizing modes, and dimensions are set.

**Why it fails:** A FILL child in a parent with unresolved sizing collapses the container to 1px, which corrupts every text node inside.

→ See: Step 5 — Frame construction order

### `unverified-variable-bind`

Setting a variable bind without reading back `node.boundVariables` to confirm.

**Why it fails:** Silent failures leave the raw value in place. The bind appears set in code but isn't actually applied. Always verify after every `setBoundVariable` call.

→ See: Step 5 — Variable binding — verify every bind

### `strokeweight-bind-verification`

Calling `setBoundVariable('strokeWeight', variable)` and then verifying `node.boundVariables.strokeWeight`.

**Why it fails:** The bind itself works, but Figma stores the result under per-side keys — `strokeTopWeight` / `strokeBottomWeight` / `strokeLeftWeight` / `strokeRightWeight` — *not* under `strokeWeight` directly. Checking `boundVariables.strokeWeight` returns falsy and throws a false-positive verification failure. Fix: bind per-side and verify per-side:

```js
node.setBoundVariable('strokeTopWeight', variable);
node.setBoundVariable('strokeBottomWeight', variable);
node.setBoundVariable('strokeLeftWeight', variable);
node.setBoundVariable('strokeRightWeight', variable);
// Verify on any one side (or all of them):
if (!node.boundVariables.strokeTopWeight) { /* retry or report */ }
```

→ See: Step 5 — Variable binding — verify every bind

### `no-text-reflow`

Changing a text node's containing width without forcing a reflow.

**Why it fails:** Figma caches the wrap width on the node itself and will not recalculate from the parent. The required pattern is `textAutoResize = NONE` → `resize(targetWidth, 40)` → `textAutoResize = HEIGHT`.

→ See: Step 5 — Text node width and reflow
