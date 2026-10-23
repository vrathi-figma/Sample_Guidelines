# Skeleton Loader

**Component:** `Skeleton Loader SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- When loading content causes a noticeable delay (>300ms).
- Complex layouts, multiple elements, or large data volumes where visual structure helps.
- Slow connections — communicates that content is loading.

---

## When NOT to use

- **Long-running processes** — use a Progress Indicator instead.
- **Fast processes (<300ms)** — show data immediately. If 301ms, fade in the skeleton then transition smoothly (no white flash between skeleton and data).
- Toasts, Global Alerts, Popovers, Modals, or Progress Indicators — never apply a Skeleton state to these. Elements inside a Modal CAN have skeleton; the Modal itself cannot.
- **Never use Skeleton Loader and Progress Indicator simultaneously** — they serve as alternatives to each other.
- Ideally only used with container-based components (modals, cards) or data-based components (tables).

---

## Best practices

- Design skeleton to closely match the actual content layout — similar sizes, proportions, and positions. Minimizes visual disruption when content loads.
- Use aspect ratios for images and variable-sized elements so they scale correctly.
- Keep simple — excessive detail causes confusion once loading completes.
- If delay exceeds 10 seconds, provide an estimated time to completion.
- Design responsively — skeleton adapts to different screen sizes and orientations.

---

## Accessibility

- Use `aria-busy="true"` on the loading region during loading; set to `false` when complete.
- If the entire section is non-interactive until fully loaded, mark the whole section as busy.
- If sub-sections complete loading independently and need interaction, selectively mark only those still loading as busy.
- Remove incomplete interactive controls from the tab order using `tabindex="-1"`.

**Color tokens:**
- Base: `color-background-faint`
- Shimmer: `color-skeleton-shimmer` (white-a60) — linear gradient (0% → 100% → 0% opacity) at -30° rotation
