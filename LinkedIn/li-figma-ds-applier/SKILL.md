---
name: li-figma-ds-applier
description: Generate and write designs to Figma following LinkedIn design system rules. Use when a designer wants to create or write back UI to Figma. Two modes — Thinking (full validation, iterative) and Flash (single batched build, quick exploration). Enforces approved libraries, tokens, components, and content standards automatically.
---

# LinkedIn Figma DS Applier

You are writing designs to Figma on behalf of a LinkedIn designer. Follow every rule in this skill exactly. These rules exist to ensure all designs use the LinkedIn design system correctly and consistently.

---

## Data Layer

The following files are available as reference. This section is baked into SKILL.md — no file reads required to understand the structure. Read individual files only when you need the detail they contain.

### Libraries at a glance

| Library | File key | What it contains | How you use it |
|---|---|---|---|
| **DS Components SDUI Library** | `eTFJFet7kxp4d8yFtPZfue` | All UI components: buttons, inputs, entities, nav, modals, feedback, etc. | `importComponentSetByKeyAsync` / `importComponentByKeyAsync` |
| **DS Color Library** | *(variables)* | Semantic color variables only (Background, Text, Border, Icon, Action, Feedback, etc.) | `importVariableByKeyAsync` for fills/strokes |
| **DS Typography 2.0** | *(styles + variables)* | Named text styles (Supportive, Title, Heading, Body, Prose, Display) **and** all dimension tokens: spacing, size, corner radius, stroke width, and elevation effect styles | `importStyleByKeyAsync` for text styles and elevation; `importVariableByKeyAsync` for spacing/size/radius/stroke; set `textStyleId` or `effectStyleId` |
| **DS Icons Library** | `s1GLDCHfC8f6ZV1aYcWmZm` | System icons (Small/Medium/Large, 303 medium) **and** all illustrations (Microspot, Spot, Scene — light + dark variants) | `importComponentByKeyAsync` — keys pre-documented in `foundations/icons.md` and `foundations/illustrations.md` |
| **Realish Fake Entities** | *(fill styles)* | Fake-but-realistic entity photos and logos for people, companies, groups, events, newsletters | Search as fill styles by entity type; apply to entity components |

**Never run `search_design_system` for icons or illustrations** — all keys are pre-documented. Only use `search_design_system` for SDUI components not listed in `components/index.md`.

---

### File structure

**`foundations/`** — token and style guidance per category. Read the specific file when you need actual keys to bind or detailed usage rules.
- `color.md` — semantic color variable categories (Background, Text, Border, Icon, Action, Feedback, etc.), usage rules, disambiguation, and full variable key list
- `typography.md` — text style selection guide, hierarchy decision tree, per-style usage, and full style key list
- `dimension.md` — spacing, size, corner radius, and stroke width tokens, spatial rhythm defaults, and full variable key list
- `elevation.md` — effect styles for raised surfaces (cards, panels, modals) and key list
- `motion.md` — curve and duration token reference. Informational only — not bindable via Plugin API
- `icons.md` — icon sourcing rules, size guidance, and full medium icon key reference (303 icons)
- `illustrations.md` — illustration types (Microspot/Spot/Scene), usage rules, and full key reference for all 9 variant groups

**`components/index.md`** — pre-documented import keys for all major SDUI components. Covers buttons, inputs, entities, navigation, feedback, overlays, and more. Also contains routing guidance for icons and illustrations. Check here before searching.

**`components/<name>.md`** — full guidance for a specific component: variants, properties, usage rules. Read only for components you'll actually place.

### When to read what

- **Before designing:** Read `components/index.md` to identify relevant components and check routing for icons/illustrations.
- **When placing a component:** Read `components/<name>.md` for that component's variants and usage rules.
- **When placing an icon:** Read `foundations/icons.md` for the key — do not search.
- **When placing an illustration:** Read `foundations/illustrations.md` for the key — do not search.
- **When binding tokens or styles during generation:** Read the relevant `foundations/<name>.md` for the actual keys.
- **SKILL.md contains rules and routing.** You do not need to re-read it during execution.

---

## Modes

The skill operates in two modes. The designer picks one in Step 1.

| Aspect | Thinking (default) | Flash |
|---|---|---|
| Best for | Production-ready output | Quick exploration |
| Component reads | Read `components/<name>.md` for each component placed | Skip per-component reads — rely on `components/index.md` keys + Rules 1–5 |
| Realish entities | Search by entity type + maintain continuity across the design | **Skip entirely — accept default ghost photos.** Do not run `search_design_system` for Realish, do not import Realish fill styles, do not apply `fillStyleId` to entity components. The built-in ghost is the Flash default. |
| Realish library check | Verified on first fill style import; stop if missing | Skip — Realish is not used in Flash mode |
| `use_figma` calls | Iterative across multiple calls as needed | Single batched call — build everything at once |
| Font loading | Load fonts as needed during iteration | Batch all required SF Pro Text + SF Pro Display weights in one `Promise.all` at the start of the generation call (see `foundations/typography.md` → Fonts) |
| Screenshots | Multi-step inspection during build | One screenshot at the end |
| Retries | As many iterations as needed | One retry max — re-run from scratch if it's wrong |

**All other rules apply in both modes**, including: components only from SDUI library, no hardcoded values, semantic color variables, named text styles, no renaming imported instances, variable binding verification (`boundVariables` readback), elevation defaults, frame construction order, and text node reflow. These have negligible cost to follow and high cost to violate.

---

## Anti-patterns

The skill maintains a separate `anti-patterns.md` file at the root of the skill directory. It catalogs the failure modes that recurring build failures have taught the team to avoid — each entry has a stable anchor name, the trap to stop doing, why it fails, and a pointer back to the rule that explains the correct pattern.

**`anti-patterns.md` is required reading at Step 1 of every invocation, before any generation work.** Load it once, keep it in working memory, and refer back to entries by anchor name (e.g. `renamed-instance`, `text-glyph-as-icon`, `children-before-sizing`) when an anti-pattern applies to the rule you're currently following.

When you encounter a new recurring failure during generation, the right place to encode it is `anti-patterns.md` — not inline in SKILL.md. The anti-patterns file is the team's shared lessons-learned log.

---

## Step 1 — Confirm Libraries

**Always run this step when the skill is first invoked.** Re-run it if the designer mentions a different file, pastes a new Figma URL, or there is any indication the working file has changed — libraries are per-file and a previous confirmation does not carry over.

### Load `figma-use` (first action — do this before anything else)

The official `figma-use` skill is **MANDATORY before any `use_figma` MCP call** per the Figma MCP server instructions. It primes the correct `use_figma` calling pattern that this skill's LinkedIn DS rules layer on top of.

- Invoke it via the Skill tool: `skill: "figma-use"`.
- Load it once at the start of the session, before talking to the designer.
- If `figma-use` is not in the available skills list, proceed but flag it to the designer so they know the baseline guidance is missing.

### Load anti-patterns

Before showing anything to the designer, read `anti-patterns.md` into working memory. Do this on every skill invocation — the list applies to every generation regardless of mode or scope. Skipping this read defeats the purpose of having the file.

### Confirm libraries and mode with the designer

Tell the designer which libraries will be used and ask them to confirm:

> "Before I start, I'll be pulling from these libraries:
>
> - 📘 DS Components SDUI Library
> - 📘 DS Color Library
> - 📘 DS Typography 2.0 Library
> - 📘 DS Icons Library
> - 🛠 Realish Fake Entities *(Thinking mode only — Flash mode uses ghost photos)*
>
> Please make sure all of these are enabled in your Figma file (**Main menu (☰) → Libraries**). Are there any additional libraries you'd like me to use as well?
>
> Also, which mode would you like to use?
> - **Thinking** — full validation, iterative refinement, per-component rule lookup. Best for production-ready output. *(default if unspecified)*
> - **Flash** — single batched build, one screenshot at the end, one retry max, ghost entity defaults (no Realish). Best for quick exploration."

Wait for their response before proceeding. If they say no additional libraries, continue with the defaults only. Never search across all published Figma libraries.

**Record the chosen mode.** All subsequent steps reference it. If the designer doesn't specify, default to Thinking.

### Verify libraries are enabled in the working file

Once the designer has confirmed, run the following programmatic check. It attempts to import one known variable from each required library — a null result means the library is not enabled:

```js
// Known sentinel variable keys — one per required library
const checks = [
  { name: 'DS Color Library',        key: 'ff25a8c71bee6dd6fcea792b5240e676ca712e42' },   // Text/color-text
  { name: 'DS Typography 2.0',       key: 'fe328f61f0efe8810804c68b914286cea558d1a8' },   // space-1x
];

// DS Components SDUI Library and DS Icons Library are verified via importComponentSetByKeyAsync —
// if those calls fail later, stop and ask the designer to enable the library.
// Realish Fake Entities is verified on first fill style import — same instruction if it fails.

const results = await Promise.all(checks.map(async ({ name, key }) => {
  try {
    const v = await figma.variables.importVariableByKeyAsync(key);
    return { name, enabled: v !== null };
  } catch {
    return { name, enabled: false };
  }
}));

return results;
```

Report the results to the designer before continuing:

> "Library check complete:
> ✅ DS Color Library — enabled
> ✅ DS Typography 2.0 — enabled
> ..."

If any library is missing, **stop immediately** and tell the designer:

> "The following libraries are not enabled in this file: [list]. Please enable them before we continue: **Main menu (☰) → Libraries → search for [library name] → Enable**. Let me know when they're enabled and I'll run the check again."

Wait for confirmation, then re-run the check. Do not proceed with any design work until all required libraries return enabled. This prevents silent failures where components import but variables don't resolve.

---

## Step 2 — Understand the Request

Clarify what the designer wants to create. Identify:
- Is this a **component** (exists in SDUI library) or **free-form** (layout, text, background)?
- What **entity types** are needed (person, company, group, event, etc.)?
- What **surface or context** is this for?

---

## Step 3 — Apply the Rules

### Rule 1: Components

- Always use components from the DS Components SDUI Library — never recreate one from scratch.
- Preserve all encoded states and variants. If a component has a built-in error state, use it — do not construct a visual approximation.
- Example: a form error state must use the input component's built-in error variant, not a custom red border.
- **Preferred:** Use `importComponentByKeyAsync` or `importComponentSetByKeyAsync` directly when you know the component key. Only fall back to `search_design_system` when you need to discover a component you don't have the key for — it is the slowest operation and should not be run speculatively.
- **Component keys are pre-documented in `components/index.md`.** Check that file before searching. It covers all major SDUI components (buttons, inputs, entity lockups, nav, feedback, overlays) with their keys, variant properties, and component property key strings.
- **If a component is not listed in `components/index.md`**, use `search_design_system` with the component's name and DS Components SDUI Library file key (`eTFJFet7kxp4d8yFtPZfue`). Import the result directly — do not reconstruct the component from scratch.
- **Entity images always use an entity component — never a raw shape.** Any time the design includes a LinkedIn entity (person, company, group, event, newsletter), read `components/index.md` to determine which entity component to use.
- **Never rename an imported component instance.** Do not call `instance.name = '...'` after importing — this applies to SDUI components, icons, and illustrations alike. Renaming detaches the instance's display name from its library origin and makes it indistinguishable from a custom frame in inspection. The library component name is the source of truth — leave it as-is.

#### Icons
All icons must come from the **DS Icons Library** (`s1GLDCHfC8f6ZV1aYcWmZm`). This applies in two scenarios:

1. **Icon placeholders inside components** — when a component has a generic icon slot, always swap in the correct icon. Do not leave default placeholder icons in place.
2. **Standalone icon usage** — any time the design calls for an icon (close, chevron, search, add, etc.), import it from the DS Icons Library.

**Read `foundations/icons.md`** for sourcing rules, size guidance, and the full medium icon key reference. Use the pre-documented keys directly — **do not use `search_design_system` for icons**. All medium icons are pre-documented.

**Never use a text character or Unicode emoji (✕, ×, +, >, —, 🌐, 🔍, ⚙️, ➕, or any glyph/emoji) as a substitute for an icon.** There is no fallback that involves text or emoji. Emoji also render inconsistently across platforms and cannot stand in for iconography. See anti-pattern `text-glyph-as-icon`.

#### Illustrations
All illustrations must come from the **DS Icons Library** (`s1GLDCHfC8f6ZV1aYcWmZm`). Three types are available: **Microspot** (object-based, Small/Large), **Spot** (UI states, Small/Large), and **Scene** (people+environment, Small only). Each type has light and dark variants (Scenes have light only).

**Read `foundations/illustrations.md`** for usage rules, sizing, surface placement, and the full key reference for all 9 variant groups. Use the pre-documented keys directly with `importComponentByKeyAsync(key)` — **do not use `search_design_system` for illustrations**. All illustration variants are pre-documented.

**When placing multiple Spot or Microspot illustrations in a group** (e.g. a row of cards, a list), use different illustrations — never repeat the same one. Choose variants that are visually distinct and contextually relevant to each item.

#### LinkedIn logo and inbug
Never construct a LinkedIn logo, wordmark, or inbug (`in` bug) from scratch. Always source the logo from one of these:
- The main navigation component (which includes the logo)
- The DS Icons Library — use the official LinkedIn logo/inbug assets from there

**Related anti-patterns:** `renamed-instance`, `reconstructed-component`, `raw-shape-entity`, `search-for-icons-or-illustrations`, `text-glyph-as-icon`, `custom-linkedin-logo`, `repeated-illustration`.

### Rule 2: No Hardcoded Values

All visual properties on non-component elements must use variables from the DS libraries. Never hardcode pixel values, hex colors, or raw numbers.

**Variable binding method:** Always use `importVariableByKeyAsync(key)` with pre-documented keys. Do NOT use collection discovery or name-string filtering — the library name format is not guaranteed to match and will silently fail. If a key is not listed, call `getAvailableLibraryVariableCollectionsAsync()` filtered by file key. If the variable still cannot be bound, stop and ask the designer — never fall back to hardcoded values.

Token categories: **spacing** (padding/gap) · **size** (width/height) · **corner radius** · **stroke width** — full key lists and spatial rhythm defaults in `foundations/dimension.md`.

**`itemSpacing` must always be bound to a spacing variable** — it is a spacing token, not a layout setting. Treat it identically to `paddingTop`/`paddingLeft`/etc. Never leave `itemSpacing` as a raw number.

**Exception:** `0` and `auto` are always fine as-is — do not replace or flag them.

**Related anti-patterns:** `hardcoded-numbers`, `unbound-itemspacing`, `name-string-variable-lookup`, `hardcoded-hex-fallback`.

### Rule 3: Color

- All colors must use variables from the DS Color Library. Never hardcode hex values.
- Use semantic variables only. Categories: `Background` · `Text` · `Border` · `Icon` · `Action` · `Positive` · `Negative` · `Caution` · `Label` · `Link` — token usage rules, disambiguation, and key list in `foundations/color.md`.
- Never create new color variables.
- If no matching token exists, stop and ask the designer before proceeding.
- If transparency is needed (e.g. `rgba(140, 140, 140, 0.2)`), keep it as `rgba()` — never convert to hex.

**Related anti-patterns:** `new-color-variable`, `hex-from-rgba`, `hardcoded-hex-fallback`.

### Rule 4: Typography

- Use named text styles from DS Typography 2.0 only. Style groups: `Supportive` · `Title` · `Heading` · `Body` · `Prose` · `Display` — hierarchy decision guide and full style key list in `foundations/typography.md`.
- **Apply styles using `importStyleByKeyAsync(key)` and set `textStyleId` on the node.** Never hardcode `fontName`, `fontSize`, `lineHeight`, or `letterSpacing` as a substitute for a named style.
- **Do not write helper functions that wrap raw font properties** (e.g. `makeText(chars, family, style, size, lh)`). These patterns bypass `textStyleId` entirely and produce detached text. The correct pattern is always: import the style by key, set `textStyleId`, then set `characters`.
- Never use base dimension tokens directly (`font-size-small`, `line-height-default`, etc.) — those are implementation internals that the named styles already compose.
- `loadFontAsync` is still required before any text edit even when applying a text style — load the font the style uses before setting `textStyleId` or editing characters.
- **DS Typography 2.0 uses the SF Pro family — not Inter.** Always preload SF Pro Text (Regular/Medium/Semibold/Bold) and SF Pro Display (Regular/Medium/Semibold/Bold) before applying any text style. See `foundations/typography.md` → Fonts for the exact `Promise.all` block. Defaulting to Inter will fail the first `set_characters` call with an unloaded-font error.

**Related anti-patterns:** `raw-font-properties`, `font-property-helper`, `base-dimension-tokens-in-text`, `inter-font-default`.

### Rule 5: Elevation

- **Default: no elevation on cards and containers.** Do not apply a shadow unless the surface floats above surrounding content (overlays, popovers, dropdowns, modals). Read `foundations/elevation.md` for when each style applies.
- To separate a card or container from a same-color background, use a `1px` stroke bound to `color-border-faint` — not a shadow.
- When elevation is appropriate, use effect styles from the DS Typography 2.0 Library: `Raised` · `Raised Active` · `Raised Faint` · `Raised Active Faint`
- **Apply using `importStyleByKeyAsync(key)` and set `effectStyleId` on the node.** Effect style keys are pre-documented in `foundations/elevation.md`. Never hardcode drop-shadow values — not even as a fallback when the import "seems unavailable."

**Related anti-patterns:** `shadow-on-static-card`, `hardcoded-shadow`.

### Rule 6: Content & Fake Entities

- For any design requiring system-generated data (people, companies, schools, groups, events, newsletters, publications), use entities from the **Realish Fake Entities library** — never invent names, avatars, or logos from scratch.
- **Realish Fake Entities exposes assets as fill styles, not components.** Search for them as fill styles, not as components or instances.
- Match entity type to context:
  - Company card / company page → Company entity
  - Person profile / mention → Person entity
  - Group surface → Group entity
  - Event surface → Event entity
  - Newsletter / publication → Newsletter entity
- **Continuity is required.** If a company entity is introduced in one part of the design, all subsequent references (page, card, mentions, follow-up screens) must use the same name, logo, and details.
- In lists or feeds with multiple entities of the same type, use different entities — do not repeat the same one.
- **Always use an entity component — never raw shapes.** Read `components/index.md` for which entity component applies to the context. Applying a Realish fill style to a raw rectangle or ellipse is not an acceptable substitute — the component itself must be used. There is no fallback path that involves raw shapes.
- When placing any entity lockup component, always populate it with the matching Realish entity photo — do not leave the default ghost image in place. Entity lockup components default to ghost images but must be replaced with the correct Realish photo based on entity type (Person photo for a person, company logo for a company, etc.).
- Ghost/placeholder images are only appropriate when the **design scenario explicitly requires a missing photo** (e.g. a new member who hasn't uploaded a profile photo, a company with no logo on file). Use the ghost images from the matching entity group in those cases.
- For content with no library equivalent (posts, UGC, article body text, comments): AI-generated text and images are acceptable, but must be contextually consistent with the entities used.

**Related anti-patterns:** `invented-entity`, `repeated-entity-in-list`, `raw-shape-entity`, `ghost-entity`.

#### Flash mode entity defaults

In Flash mode, **skip Realish entirely.** The built-in ghost photos that ship inside Entity SDUI / Entity Lockup SDUI / Entity Grid SDUI are the Flash default — leave them as-is.

Specifically, in Flash mode:
- Do **not** call `search_design_system` for Realish fills.
- Do **not** call `importStyleByKeyAsync` for Realish fill style keys.
- Do **not** override `fillStyleId` on any node inside an entity component.
- The `ghost-entity` anti-pattern does not apply in Flash mode.

The entity component is still required — never use a raw shape (`raw-shape-entity` still applies). The Flash relaxation is only about photo content, not component selection.

Continuity, name matching, and entity-type-by-context rules also do not apply in Flash mode.

See anti-patterns: `search-for-realish-in-flash`, `realish-fillstyleid-override-in-flash`.

---

## Step 4 — Read Reference Files

Before generating anything, identify and read the files relevant to this task. Use the Data Layer section above to navigate.

**For components:**
1. Read `components/index.md` to identify which components the design needs and get their import keys
2. Read `components/<name>.md` for every component you'll place — do not skip this step

> **Flash mode:** Skip step 2. Rely on `components/index.md` keys plus the general rules in Rules 1–5. Per-component variant exploration is the kind of detail Flash mode trades away.

**For foundations (read when you need the actual keys to bind):**
- `foundations/color.md` — when binding color variables to fills and strokes
- `foundations/typography.md` — when applying text styles
- `foundations/dimension.md` — when binding spacing, size, corner radius, or stroke tokens
- `foundations/elevation.md` — when deciding whether to apply elevation and for effect style keys (default is no elevation — read this before adding any shadow)
- `foundations/icons.md` — when placing any icon (standalone or in a component slot); keys are pre-documented, do not search
- `foundations/illustrations.md` — when placing any illustration (Microspot, Spot, or Scene); keys are pre-documented, do not search
- `foundations/motion.md` — if documenting transitions (informational only — no bindable keys)

Read only what the task requires. Do not load files speculatively.

---

## Step 5 — Generate the Design

With rules confirmed, libraries loaded, and foundations read, proceed to generate the design using the Figma MCP tools (`use_figma`, `get_design_context`, etc.).

Reference only the confirmed libraries when searching for components or variables. Preferred workflow:
1. Import known components directly by key — do not run `search_design_system` unless you need to discover a component you don't have the key for
2. Apply variables and text styles from the confirmed libraries
3. Populate entity content from Realish fill styles

> **Flash mode:** Build the entire design in **one batched `use_figma` call**. Inside that call:
> - Load all SF Pro Text + SF Pro Display weights in a single `Promise.all` at the start — see `foundations/typography.md` → Fonts. Do not default to Inter.
> - Import all components, variables, and styles up-front, then place nodes.
> - **Do not import or apply Realish fill styles.** Entity components keep their default ghost photos. Skip any `search_design_system` call for Realish.
> - Skip mid-build screenshots and inspection. Take one screenshot only at the end.
> - If something looks wrong after the screenshot, re-run the generation once with corrections. **One retry max** — if the second attempt is still wrong, hand the result back to the designer for direction rather than continuing to iterate.

### Frame construction order

Always follow this sequence when building auto-layout frames — skipping steps or reordering causes layout collapse that is expensive to recover from:

```
1. Create the frame
2. Set layoutMode (HORIZONTAL / VERTICAL)
3. Set primaryAxisSizingMode and counterAxisSizingMode (FIXED / HUG / FILL)
4. Set explicit width/height if FIXED
5. Set padding — and bind all padding values to spacing variables
6. Set itemSpacing — and bind to a spacing variable (treat identically to padding)
7. Append children — add FIXED-size children before FILL children
```

**Never append children before the parent frame's sizing mode and dimensions are set.** A FILL child in a parent with unresolved sizing will collapse the container to 1px, corrupting all text nodes inside.

### Variable binding — verify every bind

After every `setBoundVariable` call, read back `node.boundVariables` to confirm the binding took. Silent failures happen when the variable isn't fully imported yet or the property doesn't support binding. If a bind doesn't appear in `boundVariables`, the raw value is still in place — retry after confirming the variable import resolved, or stop and report.

```js
node.setBoundVariable('itemSpacing', variable);
// Verify:
const bound = node.boundVariables['itemSpacing'];
if (!bound) { /* retry or report — do not continue with raw value */ }
```

### Text node width and reflow

When placing a text node inside a frame with an explicit width, always force a reflow after setting the width — Figma caches the wrap width on the node itself and will not recalculate from the parent alone:

```js
textNode.textAutoResize = 'NONE';
textNode.resize(targetWidth, 40);       // force geometry change to bust cache
textNode.textAutoResize = 'HEIGHT';     // restore auto height at correct width
```

Apply this pattern any time a text node's containing width changes after initial placement, including during layout corrections.

**Related anti-patterns (procedural):** `children-before-sizing`, `unverified-variable-bind`, `no-text-reflow`.

---

## Step 6 — Validate Before Completing

Before marking the task done, verify:
- [ ] All components pulled from SDUI library with states preserved
- [ ] No imported instances renamed — SDUI components, icons, and illustrations all retain their original library names
- [ ] Icon placeholders replaced with DS Icons Library icons — keys from `foundations/icons.md`, no search used
- [ ] Illustrations (if any) imported from DS Icons Library — keys from `foundations/illustrations.md`, correct size and dark/light variant applied, no search used
- [ ] LinkedIn logo/inbug sourced from navigation component or DS Icons Library — never custom-built
- [ ] No hardcoded pixel values, hex colors, or raw numbers
- [ ] No raw `= 0` assignments on `paddingTop` / `paddingBottom` / `paddingLeft` / `paddingRight` / `itemSpacing` — these default to `0` on a fresh frame and the DS Token Lint hook blocks the literal assignment (see anti-pattern `raw-zero-padding`)
- [ ] All spacing, size, radius, and stroke values use library variables — verify with `get_metadata` that `boundVariables` are set on padding, gap, and radius properties (not just raw numbers)
- [ ] `strokeWeight` bindings verified under per-side keys (`strokeTopWeight` etc.), not under the `strokeWeight` field directly (see anti-pattern `strokeweight-bind-verification`)
- [ ] Imported components match their type — single components via `importComponentByKeyAsync`, component sets via `importComponentSetByKeyAsync` (see anti-pattern `component-set-vs-single`)
- [ ] Text-bearing instances (Entity Lockup, Buttons, etc.) populated via component properties or by matching node names — not by array index over `findAll('TEXT')` (see anti-pattern `text-slot-set-by-index`)
- [ ] All colors use DS Color Library semantic variables — verify `boundVariables` on fill/stroke paints (no unbound hex fills)
- [ ] Typography text styles are applied — verify `textStyleId` is set on text nodes (not raw font properties)
- [ ] Typography uses named text styles only
- [ ] Cards and containers have no elevation effect — separation from same-color backgrounds uses `color-border-faint` stroke instead
- [ ] Elevation effect styles (if used) are from DS Typography 2.0, applied via `effectStyleId` — no hardcoded shadows
- [ ] All entities sourced from Realish Fake Entities library (as fill styles) with correct type matching *(Thinking only — Flash uses ghost defaults; Realish is not imported)*
- [ ] Every entity is built with an entity component (Entity SDUI, Entity Lockup SDUI, or Entity Grid SDUI) — never a raw shape *(applies in both Flash and Thinking — the entity component's built-in ghost photo is the baseline content in both modes)*
- [ ] Entity components populated with the matching Realish photo — no default ghost images unless the scenario requires a missing photo *(Thinking only — in Flash mode, the built-in ghost photo is the expected default and needs no replacement)*
- [ ] Entity continuity maintained across the design *(Thinking only — Flash does not track continuity)*
