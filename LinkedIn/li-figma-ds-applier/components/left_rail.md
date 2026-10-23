# Left Rail

**Component:** `Left Rail SDUI`
**Library:** App Architecture SDUI Library — Flagship only

---

## When to use

- Home page only.
- Left rail navigation is a series of stacked modules for user-specific navigation and identity.

---

## Module ordering (top to bottom)

1. **Identity** — user profile info
2. **Growth & Premium** — premium/enterprise product links
3. **Pages** — user's affiliated pages
4. **Common** — same for all users

Only the Common module is identical across all users. Identity, Growth & Premium, and Pages vary per user.

---

## Internal ad display

- Ads for LinkedIn products appear in the Growth & Premium and Pages modules.
- Each ad is a link to a Premium or Enterprise product with a single-line value prop.
- **Do:** Show only a single value prop line per module. The ad can appear on either of the eligible menu items.
- **Don't:** Display 2 value prop lines within the same module — only one internal ad can be shown at a time.
- Value prop text must not exceed 1 line.

---

## Behavior

- When the Left Rail fits within the viewport, it remains **fixed**.
- When the Left Rail extends beyond the bottom of the viewport, it **scrolls with the page**.
