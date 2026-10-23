# Progress Indicator

**Components:** `Progress Indicator Linear SDUI`, `Progress Indicator Circular SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to communicate the status of an ongoing process — loading, uploading, downloading, processing.
- For loads lasting longer than 10 seconds, include explanatory text alongside the indicator.
- Use only one progress indicator per page. For content loading in a small section, place the indicator directly within that section.

---

## Determinate vs. Indeterminate

| Type | When to use |
|---|---|
| **Determinate** | Progress amount is known. Moves from 0 to 100 (linear) or 0° to 360° (circular). Sets a clear expectation of load time. |
| **Indeterminate** | Duration is unknown, brief, or unspecified. Animates continuously without a fixed endpoint. |

- Can transition: as more information becomes available, switch from indeterminate to determinate mid-process.
- **Be consistent:** if a circular indicator represents "refresh" on one screen, use circular consistently for all refresh actions.

---

## Types

### Linear

- Animates along a straight, visible track.
- Place on the container that's loading — centered or on the edge that grows to show content.
- When spanning the full screen width, inset from the edge by at least 4px.

**Track variants:**
- **Faint Track:** Requires at least one visible label (percentage or current/max value) OR must span the full width of its container.
- **Dark Track:** Optional labels.

**Label positioning:**
- **Below (default):** Works at any viewport size, mobile or web. Preferred for multi-surface designs.
- **Side (left/right):** Web only — do not use on mobile. Side labels reflow to below-positioned on narrower viewports.
- For determinate faint track: at least one label is required (start or end).

### Circular

- Animates from 0 to 360 degrees.
- Can be placed on surfaces, canvases, or within containers (buttons, cards).
- Also used for pull-to-refresh.

**Sizes:**
| Size | Use |
|---|---|
| 16, 20 | Replacing icons or tight spaces |
| 32, 40 | Full-page loading scenarios |
| 48, 64 | Completeness meters (tracking task/profile progress) |

**Muted variant:** Available for sizes 32, 40, 48, 64.

### Spinner (deprecated)
- Used only for 1:1 MVP mapping — do not use for net-new designs.
- Will be replaced entirely by Circular Indeterminate.

---

## Anatomy

| Slot | Description |
|---|---|
| **Indicator (Fill)** | Shows progress achieved. Determinate: fills proportionally. Indeterminate: expands and contracts continuously. |
| **Indicator (Track)** | Full length of the indicator. |
| **Label** | Optional (or required in some linear configurations). Describes the current progress. |

---

## Best practices

- **Completeness meter:** Use determinate indicators (linear or circular) to track profile or task completion. Place prominently at top of page; list remaining next steps alongside.
- **Long load times:** For loads > 10 seconds, add explanatory text. Keep labels under 5 words — they disappear when the indicator closes.
- **Content labels:** Use nouns and adjectives ("Uploading…", "60%"), not verbose explanations. Label text must match the indicator value.
- **Be consistent:** Use the same type of progress indicator consistently across screens. If a circular indicator represents "refresh" on one screen, use circular for all refresh actions — don't mix types for the same pattern.
- **One progress indicator per page:** Don't use more than one Progress Indicator graphic in a single portion of the page. For content loading in a small section, place the indicator directly within that section.

**Long loading time content design:**

**Do:** For scenarios that typically take more than a few seconds, give the user more information about the action before it starts — set expectations upfront.
**Don't:** Show a loading indicator with no context or label when the load is expected to be long.

**Clear and relevant labels:**

**Do:** If you include a label alongside the progress indicator, keep it clear and relevant to the specific action in progress.
**Don't:** Use a vague or irrelevant label — the message appears instantly when the indicator shows.

---

## Internationalization

- **RTL:** Progress indicators and labels mirror their LTR counterparts.
- **Localization:** Prioritize semantic accuracy over literal translation. Design for text length variation; test with native speakers.
- Caution with abbreviations — they may not translate well.

---

## Accessibility

**Name, Role, Value:**
- Role: `progressbar`

**Circular:**
- Indeterminate: do not specify a current value.
- Determinate: use `aria-valuenow`, `aria-valuemin`, `aria-valuemax` for screen reader support. Screen reader announces value automatically (e.g. "10 percent").
- Optional label: if used to display a text equivalent of the value, ensure it matches the indicator.

**Linear:**
- Indeterminate: do not specify a current value. Use label or context to communicate system status.
- Determinate: use `aria-valuenow`, `aria-valuemin` (usually 0), `aria-valuemax` (usually 100).
- Faint track with insufficient contrast: a visible label showing current percentage is required.

**Spinner (deprecated):**
- Since visual is indeterminate, do not specify a current value.
- Use optional label to communicate state (e.g. "Loading…").

**Color & Contrast:**
- Distinguishability is achieved through shape/context rather than color alone:
  - Linear: fill and track have different thicknesses — distinguishable without contrast.
  - Circular: track boundaries are inferred from the circular shape.
  - Full-width: start/end inferred from container boundaries.
- All other default colors meet minimum contrast requirements for light and dark modes.
