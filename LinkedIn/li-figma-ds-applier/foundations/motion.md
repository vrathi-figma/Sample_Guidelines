# Motion Tokens

> **Plugin API note:** Motion tokens are informational only. The Figma Plugin API does not support binding motion tokens directly — they are defined in the library for design reference and engineering handoff. Do not attempt to call `importVariableByKeyAsync` for motion tokens. Apply motion as prototype transitions in Figma manually, or document the curve/duration pair in a design annotation.

---

## How to read a motion token name

Motion token names are composed of segments in a fixed order. The prefix `motion` is always first.

```
motion - [type] - [variant] - [scale]
```

To interpret any token: decompose by segment order and intersect each segment value's meaning.

---

## Composition rules

- `type` is always required
- `variant` applies to `type: curve` only
- `scale` applies to `type: time` only — value in milliseconds
- Motion always requires a curve + duration pair. Pick a curve token and a time token together

---

## Segment definitions

### type

| Value | Controls |
|---|---|
| `curve` | Easing curve — defines the acceleration pattern of an animation. Pair with a `time` token |
| `time` | Duration — defines how long an animation takes. Pair with a `curve` token |

### variant (curve tokens only)

| Value | Feel |
|---|---|
| `ease-out` | Begins fast, ends slow. Use for elements entering the screen or responding to user action |
| `ease-in` | Begins slow, ends fast. Use for elements leaving the screen |
| `easy-ease` | Gentle ease in and out. Natural, balanced feel for most transitions |
| `dramatic-ease` | Pronounced ease in and out. Emphasized, high-energy feel |
| `linear` | Constant speed, no acceleration. Use sparingly — for looping animations or progress indicators |

### scale (time tokens only)

| Value | Duration | Use for |
|---|---|---|
| `50` | 50ms | Extra fast — micro interactions |
| `100` | 100ms | Fast, immediate feedback |
| `250` | 250ms | Default speed for most transitions |
| `350` | 350ms | Moderate — larger element transitions |
| `500` | 500ms | Slow — complex or full-screen transitions |
| `1000` | 1000ms | Very slow — deliberate or dramatic moments |
| `2000` | 2000ms | Slowest — ambient or looping animations |

---

## Pairing guide

Curve and duration must always be paired. Common combinations:

| Scenario | Curve | Duration |
|---|---|---|
| Element entering (micro interaction) | `motion-curve-ease-out` | `motion-time-100` |
| Element entering (standard transition) | `motion-curve-ease-out` | `motion-time-250` |
| Element exiting | `motion-curve-ease-in` | `motion-time-250` |
| Larger element entering (sheet, modal) | `motion-curve-easy-ease` | `motion-time-350` |
| Full-screen transition | `motion-curve-easy-ease` | `motion-time-500` |
| Dramatic or hero moment | `motion-curve-dramatic-ease` | `motion-time-350` |
| Looping / ambient | `motion-curve-linear` | `motion-time-2000` |
