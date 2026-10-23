# Loading States

**Reference:** `◾️ Loading`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

Cross-cutting guidance on choosing the right loading pattern.

---

## Two types of loading indicators

| Type | Description |
|---|---|
| **Skeleton Loader** | Placeholder shapes that mimic the layout of content while it loads. |
| **Progress Indicator** | Circular or linear indicator that communicates active loading, downloading, uploading, saving, or submitting. |

---

## Skeleton Loader vs. Progress Indicator

### Use Skeleton Loader when:
- A noticeable delay exists in loading content and the final layout is predictable.
- Complex layouts, multiple elements, or large volumes of data are loading.
- The goal is to communicate structure and reduce perceived wait time.
- **Preferable for complex content** — Skeleton Loaders provide a holistic view of what is expected on the page.

### Use Progress Indicator when:
- Communicating determinate loading times (you know how long it will take).
- Loading is triggered by a single in-line action (e.g., a button submitting a form) — use a small inline loading indicator on the element itself.
- The loading process is the result of a long-running action (downloads, uploads, saves).

**Note:** Never use both simultaneously — they serve as alternatives to each other.

---

## Circular vs. Linear (Progress Indicator)

| Type | When to use |
|---|---|
| **Circular** | Continuous progress indicators — spinning state communicates active loading without implying a specific completion amount. Can be used in different sizes across UI. |
| **Linear** | Shown in the form of a line (progress bar). Typically used to communicate determinate loading in different stages of a process. |

---

## Determinate vs. Indeterminate

| Type | When to use |
|---|---|
| **Determinate** | When the loading time is known — provides exact expectation of load time through visual progress (e.g., 60% complete). |
| **Indeterminate** | When the loading time is not specified or unknown. Used when it is not practical to estimate the time required to complete a task. |

---

## Composability

Skeleton Loaders are composable — designed to combine different loading elements (text, images, shapes) to mirror the actual content layout. Design them to closely match the final layout structure so the transition feels seamless.
