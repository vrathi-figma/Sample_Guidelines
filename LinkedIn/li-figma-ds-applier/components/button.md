# Button

**Components:** `Button SDUI`, `Ghost Button SDUI`, `Overlay Button SDUI`
**Library:** DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`)

---

## When to use

- Use to let users take an action — connecting, accepting, following, messaging, submitting forms, etc.
- Commonly used in modals, forms, cards, popovers, and toolbars.

---

## Types and when to use each

### Primary
The most important action on the page. Display only one primary button per content area or viewport at a time.

### Secondary Emphasis
For actions less important than primary, but still ones we encourage the user to take.

### Secondary
For neutral, lower-importance actions. Always default to this type — emphasizing secondary or tertiary actions should not be the norm.

### Ghost
For actions that are visible but not critical, like "Learn More" or "View Details."
- Supports no horizontal padding to align easily with surrounding UI. Without padding, the button has no visible background on interactive states.
- Supports XSmall (24px) size, though this is discouraged.

### Overlay
Used when an action sits on top of an element — e.g. previous/next in a carousel or PYMK cards. Use `Overlay Button SDUI`.

---

## How to configure

**Variants:**
| Property | Values |
|---|---|
| `Type` | `Primary` · `Secondary` · `Ghost` · `Overlay` |
| `Size` | `Medium` · `Small` · `XSmall` *(Ghost only)* |
| `Icon` | `None` · `Start` · `End` |
| `Emphasis` | `True` · `False` |
| `State` | `Enabled` · `Hover` · `Active` · `Disabled` · `Loading` |
| `Width` | `Hug` · `Fill` |

**Configuration rules:**
- **Label vs Icon button:** Use a label button whenever possible. Use an icon-only button only when space is limited and the icon clearly conveys intent without text.
- **Sizes:** Small and Medium for all types. Ghost also supports XSmall (24px) — use sparingly.
- **Icon position:** `None`, `Start`, or `End` — choose based on layout needs.
- **Width Hug:** button width adjusts to label width (default).
- **Width Fill:** button expands to fill its parent container, label and icon centered. Use in cards where the button needs high visual weight. If a Fill button's label wraps, text should align left, not center.

---

## Placement rules

**One primary button at a time.** Only one primary button per content area or viewport. Combine with lower-emphasis buttons to create visual hierarchy.

**Do:** One primary button (e.g. Connect) paired with a secondary button (e.g. Message).
**Don't:** Two primary buttons side by side (e.g. Message + Connect both filled).

---

**Right-aligned button groups** (modals, action bars, multi-step flows, forms): most emphasized button on the far right, decreasing importance from right to left.

**Do:** Message (secondary) on left, Connect (primary) on right.
**Don't:** Connect (primary) on left, Message (secondary) on right.

---

**Left-aligned button groups**: most emphasized button on the far left, decreasing from left to right. This aligns visually with content above and below.

**Do:** Connect / Message / More — most emphasized on the far left.
**Don't:** More / Message / Connect — reversed order buries the primary action.

---

**Fixed Widths:** While buttons can have a maximum width, it's crucial to consider how label text impacts the button's visual appearance, especially when it wraps to multiple lines.

**Do:** Allow a long label to wrap to a second line.
**Don't:** Truncate the label with an ellipsis (e.g. "This is a really really...").
**Don't:** Cut the label off mid-word.

---

**Fill button groups:**
- Contextual (integrated with content): most emphasized on the far left
  - **Do:** Invite (primary, left) + More (secondary, right)
  - **Don't:** Share (secondary, left) + Invite (primary, right)
- Bottom-of-screen (full-screen modals, multi-step flows): most emphasized on the far right
  - **Do:** Cancel (left) + Submit (primary, right)
  - **Don't:** Submit (primary, left) + Cancel (right)

---

**Focus order:** Regardless of visual emphasis, always maintain left-to-right, top-to-bottom tab order for LTR locales. Focus order must not follow visual emphasis — it must follow reading order.

**Button group overflow:** Limit button groups to three surface buttons. When more than three are needed, overflow the rest into a Menu.

---

## Label rules

- Keep labels short and concise. Do: "Connect" — Don't: "Connect with Henry"
- Sentence case, no period. Do: "Download the course" — Don't: "Download the Course"
- Labels describe actions (CTAs), not navigation destinations. Do: "Submit", "Upload", "Connect" — Don't: "Profile", "Form", "Support"
- No ellipsis to imply continuation. Do: "More" — Don't: "More..."
- Never truncate labels. If the label is long, let it wrap. Design flexible layouts to accommodate varying text lengths, especially across languages. Truncating text risks misunderstanding and errors, hinders accessibility and user confidence — use clear icons or rethink button placement instead.
- When a label wraps, corner radius adjusts to half the button's min-height — this is built into the component.

---

## Loading state

Use the loading state for operations that typically take 1–5 seconds. It is a mitigation strategy, not a solution for slow systems.

- Use to provide immediate feedback that the user's action was received.
- Use when the system needs time to process before showing results.
- Return the button to its original state if the action fails or is cancelled.
- Provide alternate label text where possible (e.g. "Saving" for a "Save" button). If none provided, "Loading" is the default.
- For icon-only buttons, no text shows during loading — specify an accessible label.
- For quicker actions, loading state may not be necessary. For longer actions, consider Progress Indicator instead.
- Account for button width changing when it enters the loading state.
- Common use cases: Save, Send, Download, Login.

---

## Interaction

Action triggers on the final confirmation of intent:
- **Mouse/Touch:** on mouse up
- **Keyboard:** on key up while pressing Enter or Space with the button focused
- **Voice:** on voice command

Provide immediate feedback (visual change or loading indicator) so users know their action is processing.

---

## Internationalization

- **RTL:** Icons should mirror their LTR counterparts.
- **Other languages:** Prioritize semantic accuracy over literal translation. Design for text length variation — button labels expand significantly in some languages. Be cautious with abbreviations; they may not translate. Collaborate with the Localization team and test with native speakers.

---

## Accessibility requirements

**Target size:**
- Web: Medium buttons → 48px tap target. Small buttons → 32px tap target. All buttons default to 48px.
- Compact (select cases only): Can reduce to 32px. Use sparingly — smaller targets reduce usability. Only available for buttons with visual size 32px or smaller (excludes Medium).

**Focus indicator:** Must be visible and unobscured when focused via keyboard. Appearance may vary by platform or device — this is expected.

**Keyboard operation** (non-disabled only):
- `Tab` — moves focus to button
- `Enter` — activates focused button

**Name, Role, Value:**
- Role: Button. Buttons never have a value.
- Button names must always include the visible text label. When context is needed to clarify meaning, include it in the a11y name even if it's not in the visible label.
- **Label button:** A11y name must be provided when context is needed to derive meaning.
- **Icon button:** A11y name must always be defined, predictable based on the icon. Include contextual info if needed.
- **Loading state:** Update aria-label to reflect the loading action (e.g. "Saving"). Add aria-busy to indicate the button is performing a task. If content outside the button changes, use aria-polite or aria-assertive. For icon-only buttons, specify a custom aria-label or "Loading" will be used.

**Color & Contrast:**
- All default colors meet or exceed 3:1 minimum contrast for light and dark modes.
- Button text is always bold and at least 14px — must meet 3:1 contrast with the button fill or surrounding container.
- Stroke and fill of primary and secondary buttons must also meet 3:1 contrast with surrounding color.
- For overlay buttons, the fill ensures contrast of button text over unpredictable content — the fill itself does not need to meet 3:1 against what it overlays.
- Color differences between button types do not convey meaning about purpose — do not rely on color alone to communicate button hierarchy.
