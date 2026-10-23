# Dimension Tokens

**Library:** DS Typography 2.0 (`1Dle3oNSHgIg9jewHabgfW`) — collection: `Dimension Tokens`

---

## How to read a dimension token name

Dimension token names are composed of segments in a fixed order. No prefix — the `type` segment identifies the dimension property.

```
[type] - [scale | size] - [element] - [variant]
```

To interpret any token: decompose by segment order and intersect each segment value's meaning.

---

## Composition rules

- Segments always appear in the order defined above
- `type` is always required
- `scale` and `size` are alternatives — a token uses one or the other depending on type
- Not all segments are required — include only those needed for specificity
- Dimensions are base tokens only — no semantic layer. Token choice is scale-based: pick the value that fits the visual density and spatial rhythm of the context

---

## Segment definitions

### type
Identifies the dimension property the token controls.

| Value | Use for |
|---|---|
| `space` | Spacing — margins, padding, gaps between elements |
| `size` | General-purpose fixed dimensions — icon sizes, avatar sizes, fixed element dimensions |
| `corner-radius` | Border radius values |
| `stroke-width` | Border and outline widths |
| `height` | Height values |
| `width` | Width values |
| `breakpoint` | Responsive layout thresholds |

### scale
Numeric multiplier — used with `space`, `size`, `stroke-width`, `corner-radius`. Using a raw pixel value instead of a token is off-system.

| Token | px |
|---|---|
| `*-0_25x` | 2 |
| `*-0_5x` | 4 |
| `*-1x` | 8 |
| `*-1_5x` | 12 |
| `*-2x` | 16 |
| `*-2_5x` | 20 |
| `*-3x` | 24 |
| `*-4x` | 32 |
| `*-5x` | 40 |
| `*-6x` | 48 |
| `*-8x` | 64 |
| `*-10x` | 80 |
| `*-12x` | 96 |
| `*-16x` | 128 |

Stroke widths also include `*-0_125x` = 1px and `*-0_375x` = 3px.

### size
Named size — used for `height`, `width`, `breakpoint` tokens.

`2xsmall` · `xsmall` · `small` · `medium` · `large` · `xlarge` · `2xlarge` · `3xlarge` · `4xlarge` · `5xlarge` · `6xlarge` · `narrow` · `wide`

### variant
| Value | Meaning |
|---|---|
| `full` | Fully rounded corner radius — pill or circle shape |
| `fixed` | Fixed-width panel variant |

---

## Spatial rhythm guide

Dimension tokens are scale-based — use smaller multipliers for tighter/denser contexts and larger multipliers for more spacious ones.

**Corner radius default:** `corner-radius-1x` (8px) — use this unless the context calls for something different.

### Suggested defaults (from DS Spacing Guidance)

These are starting points for layout consistency. Generic dimension tokens can be substituted when needed.

**Padding**
| Token | px | Use for |
|---|---|---|
| `space-1_5x` | 12 | Small / compact padding |
| `space-2x` | 16 | Medium / default padding |
| `space-2_5x` | 20 | Large padding |
| `space-3x` | 24 | XLarge padding |

**Gaps**
| Token | px | Use for |
|---|---|---|
| `space-1x` | 8 | Small gap |
| `space-2x` | 16 | Medium gap |
| `space-3x` | 24 | Large gap |

**Panel widths**
| Token | px |
|---|---|
| `width-narrow` | 256 |
| `width-medium` (panel-medium) | 320 |
| `width-wide` (panel-large) | 384 |

**Text measure (max content width)**
| Token | px |
|---|---|
| `text-width-xsmall` | 448 |
| `text-width-small` | 512 |
| `text-width-medium` | 576 |
| `text-width-large` | 640 |
| `text-width-xlarge` | 720 |
| `text-width-2xlarge` | 800 |

**Breakpoints**
| Token | px |
|---|---|
| `breakpoint-2xsmall` | 576 |
| `breakpoint-xsmall` | 768 |
| `breakpoint-small` | 960 |
| `breakpoint-medium` | 1200 |
| `breakpoint-large` | 1440 |
| `breakpoint-xlarge` | 1600 |
| `breakpoint-2xlarge` | 1920 |

### Corner radius

| Token | px | Use for |
|---|---|---|
| `corner-radius-0_5x` | 4 | Small tight elements |
| `corner-radius-1x` | 8 | **Default** — most components |
| `corner-radius-1_5x` | 12 | Medium containers |
| `corner-radius-2x` | 16 | Larger surfaces |
| `corner-radius-3x` | 24 | Large containers, modals |
| `corner-radius-full` | 999 | Pill / circle shapes |

### Stroke width

| Token | px | Use for |
|---|---|---|
| `stroke-width-0_125x` | 1 | Hairline borders |
| `stroke-width-0_25x` | 2 | Default borders and dividers |
| `stroke-width-0_375x` | 3 | Medium emphasis |
| `stroke-width-0_5x` | 4 | Focused or emphasized outlines |
| `stroke-width-1x` | 8 | Heavy stroke |

---

## Variable keys (DS Typography 2.0 — `1Dle3oNSHgIg9jewHabgfW`)

Use `importVariableByKeyAsync(key)` to bind dimension variables directly — do not use collection discovery or name-string filtering.

```js
const variable = await figma.variables.importVariableByKeyAsync(key);
// For spacing (gap, padding):
node.setBoundVariable('itemSpacing', variable);
node.setBoundVariable('paddingTop', variable);
// For corner radius:
node.setBoundVariable('topLeftRadius', variable);
// For stroke width:
node.setBoundVariable('strokeWeight', variable);
// For width/height:
node.setBoundVariable('width', variable);
node.setBoundVariable('height', variable);
```

### Spacing (`space-*`)
| Token | px | Key |
|---|---|---|
| `space-0_25x` | 2 | `27e46fef89857fe7b601dd3681444ddaa3d0e2c6` |
| `space-0_5x` | 4 | `0895f1a6a061b0174dfbc567b3714a13a4a6206b` |
| `space-1x` | 8 | `fe328f61f0efe8810804c68b914286cea558d1a8` |
| `space-1_5x` | 12 | `0ebfbbdb2aae660f36b8e8ccf41893c69b8586aa` |
| `space-2x` | 16 | `a6e89ba55fad77ae9c2d5d91279d7bb2015c38f0` |
| `space-2_5x` | 20 | `cd804d3e3699b3e4a2fdc983214519bdcfe1bf75` |
| `space-3x` | 24 | `ced0a751031e3dcfd2343f692d7781356fbdddcd` |
| `space-4x` | 32 | `c4e9d28fc352d2f90919036fa0b4862bbf8df50c` |
| `space-5x` | 40 | `1f81cc3d292be9bd7c59970132853392bb623477` |
| `space-6x` | 48 | `b420af41699003d6f93981d8b7a79678330f6a22` |
| `space-8x` | 64 | `142f56a07b5bbcf53c269b2c42ac9f240b234a2f` |
| `space-10x` | 80 | `c480cadd15eea7e3a853ca55abbe697c88b61a6f` |
| `space-12x` | 96 | `2a4f1aba0015608396880808c23af47d395c7bb6` |
| `space-16x` | 128 | `7f83743e75be58cb59afa0b1a4ce12713f671764` |

### Size (`Size/size-*`)
| Token | px | Key |
|---|---|---|
| `Size/size-0_25x` | 2 | `10e3c59bb8b2cef29d2efb11b2302a9fd7a9b423` |
| `Size/size-0_5x` | 4 | `07b6c5b1f81835ef5daf828896fa34ee8e971e2a` |
| `Size/size-1x` | 8 | `b8f21f6e9a5cc14ea0c9552a3f87a3e9ace13a9a` |
| `Size/size-1_5x` | 12 | `bcc0395545d6bd75462f10f5ef26123174b0de6a` |
| `Size/size-2x` | 16 | `94c380eb04e16ad8a8edae5db81a27f24d589033` |
| `Size/size-2_5x` | 20 | `1b7b7d386de8c96a742ceb70e57cec3e98bebbc7` |
| `Size/size-3x` | 24 | `36cad4ef74ec657bcaa8ed1292e57d7eb376abcc` |
| `Size/size-4x` | 32 | `51df6338b9c5b615c97be9d8c36413b078f83e45` |
| `Size/size-5x` | 40 | `24b9edf34708da67cc7fc23bd2b2739a5b6d6654` |
| `Size/size-6x` | 48 | `ffdf9ab4aee277a39bc057cbbe9e6042eff7a101` |
| `Size/size-8x` | 64 | `321d1ed975e1bc69751a6111192ba07699e6ca06` |
| `Size/size-10x` | 80 | `8699c0f669fb052a1526d6986c610da35bbad71a` |
| `Size/size-12x` | 96 | `eb2e67045c3e20e53f8191718abebb71e8315fe9` |
| `Size/size-16x` | 128 | `2ddf0cdbfdfd39d50974e31aad1635a1307cb25a` |
| `Size/size-20x` | 160 | `a8d130bbc3edc33a1c9cdc4e32b54567a3fa0e40` |

### Corner radius (`Corner Radius/corner-radius-*`)
| Token | px | Key |
|---|---|---|
| `Corner Radius/corner-radius-0_5x` | 4 | `8f314971f2ddf7f8468ae51f48c0f2a82eade7ef` |
| `Corner Radius/corner-radius-1x` | 8 | `f4549ef6bac204c4ad1cc94fe14c65a97dbbb329` |
| `Corner Radius/corner-radius-1_5x` | 12 | `42fa8c70d3e806049e843a74c07f0126bfcd9ae0` |
| `Corner Radius/corner-radius-2x` | 16 | `aee411d53a235d40562876150537fe7f0ab82d54` |
| `Corner Radius/corner-radius-3x` | 24 | `714f27125396f4ec633b06fe5567251de981adcc` |
| `Corner Radius/corner-radius-full` | 999 | `83b5f6829e9caa2b62f304e6b7941c09a0da72db` |

### Stroke width (`Stroke Width/stroke-width-*`)
| Token | px | Key |
|---|---|---|
| `Stroke Width/stroke-width-0_125x` | 1 | `a58abc564cab67630ad4c492ae87f52a1769a1b5` |
| `Stroke Width/stroke-width-0_25x` | 2 | `085287e6d71c6f03ba32c187bab41f24f08fb322` |
| `Stroke Width/stroke-width-0_375x` | 3 | `13129f4440187cfaf6f6be0afeedc10526135b5b` |
| `Stroke Width/stroke-width-0_5x` | 4 | `e91b6d968f341234ba7376f7a21f5d19b52a6fbb` |
| `Stroke Width/stroke-width-1x` | 8 | `5b43b956cc55fb265a6af08357fcc4a352562f2a` |
