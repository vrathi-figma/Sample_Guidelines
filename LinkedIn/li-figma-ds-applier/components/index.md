# Component Index

All components available in the DS Components SDUI Library (`eTFJFet7kxp4d8yFtPZfue`).

Use this file to identify which components a task needs and get their import keys. For variant properties and usage rules, read the component's `.md` file.

Components without a pre-documented key: use `search_design_system` with the component name and library file key `eTFJFet7kxp4d8yFtPZfue`.

---

## Before you search

**Icons and illustrations are not in this library.** They live in the **DS Icons Library** — keys are fully pre-documented in `foundations/icons.md` (icons) and `foundations/illustrations.md` (illustrations). Read those files and use `importComponentByKeyAsync(key)` directly. Do not run `search_design_system` for either.

---

## How to import

```js
// Component set (has variants) — use for most components
const set = await figma.importComponentSetByKeyAsync('KEY');
const variant = set.children.find(c => {
  const vp = c.variantProperties;
  return vp.Type === 'Primary' && vp.Size === 'Medium' && vp.State === 'Enabled';
});
const instance = variant.createInstance();

// Single component (no variants)
const component = await figma.importComponentByKeyAsync('KEY');
const instance = component.createInstance();
```

---

## Actions

| Component | Import Key | When to use | File |
|---|---|---|---|
| Button | `aa7f4fd25c187e6e67b407bb02570b151e743cf1` | Primary, secondary, ghost, and destructive actions. Key is for Button SDUI — Ghost Button (`153efc03f7a86f9e753d3739758931f65eb8b176`), Overlay Button (`2a714396108e48ce7ef9e777584dc1cf9678dfe8`), and icon-only variants also in `button.md` | `button.md` |
| Button FAB | `aee5d872aabf0e61e62b1fba1e495cecd21d53ea` | Floating action button — primary contextual action on a screen | `button_fab.md` |
| Split Button | `00e90d3012afde133c829eb680b42682af2e683d` | Button with a primary action and a dropdown for secondary actions | `split_button.md` |
| Toggle Button | `0a869489b0ebc9056c32c74545a6174454b9ef3e` | Button with an active/inactive toggle state | `toggle_button.md` |
| External Application Button | `d700b7a1608996576403874e00e8f5777daae6c6` | CTA linking to an external app or deep link | `external_application_button.md` |
| Media Button | `b205d1a02e2f3c75bd76bc5837d3acbd08ac4672` | Button for initiating media-related actions (attach photo, video, document). Volume: `2025f2a431d9abc1d11f8bae595778b796c6f10d`, Play/Pause: `3d5b6c5c3b8fac71efceff04e3b2c894b12ba431`, Captions: `c81e14e850a4f8e217e0514ddfd28c24b46a1842`, Fullscreen: `fd82a8982c2325a984c0abc8cbaeef747524fbe4`, Playback Speed: `ce5ee3304940931c322bea51b0d3405d1cd48b87` | `media_button.md` |

---

## Form Controls

| Component | Import Key | When to use | File |
|---|---|---|---|
| Text Input / Text Area | `c3a4eabcafd66b3c8731e6f29f240fa4d0a1615f` / `42ce720cefb0a713f7f6afb1e22103952c62b048` | Single-line and multi-line text form inputs | `text_input_and_text_area.md` |
| Search Input | `1f2efccade46b857f7ba075fa087148eb59ebe69` | Search field with optional label and helper text | `search_input.md` |
| Typeahead | `e1f51fc7e0666ba545a8de8d7e8eb4e9e9b85aa3` | Search input with live autocomplete suggestions | `typeahead.md` |
| Checkbox | `8f0cc0ff9259b1acc5dacae313543747f6fcbfa0` | Multi-select form control | `checkbox.md` |
| Radio | `69df6f475c2c2e454ce786ddc444b8c80341b333` | Single-select form control | `radio.md` |
| Switch | `873677229fb308ade5a6d1f94b32f7f5a0fe374f` | Toggle on/off form control | `switch.md` |
| Select | `c99d16e1267e58215b0982611b6472b5d12d3b33` | Dropdown for selecting a single value from a list | `select.md` |
| Slider | `d5a46ed8071ed846081a2262f1ecdb37c69aa3ac` | Range input for selecting a value within a range. Segmented variant: `0465a4d80916747312b8a661deefde5500da7a55` | `slider.md` |
| Stepper | `3e12f077e99f9913c818cb7885beb5d9cccace48` | Numeric increment/decrement input. Vertical variant: `9a7d971103375abb5920a5e8bacb296c2704768e` | `stepper.md` |
| Date Picker | `69284c7e1fefa4c96a614b4696a4fd475fcc6ebb` | Date selection input | `datepicker.md` |
| Time Picker | `5f7d2d65beed294b401052b0641e2645fccd929e` | Time selection input | `timepicker.md` |
| Rich Text Editor | `e9e99d135b5089a38244818066e41a539b5f3563` | Multi-line input with formatting controls | `rich_text_editor.md` |
| Star Rating | `98e79841271b2715c7b21ffc84c53c6b8669691b` | Star-based rating input or display. Group variant: `ccfd39eebc9b41a24a21519b9724ee26a8738eab` | `star_rating.md` |

---

## Entity & Content

**Choosing the right entity component:**
- **Entity SDUI** — standalone photo only (circle or square). Use when the entity image is a visual anchor with text positioned separately (e.g. profile header, top of a card).
- **Entity Lockup SDUI** — photo + title + subtitle + metadata in a horizontal layout. Use in lists, feeds, and any surface where entity details appear beside the image.
- **Entity Stack SDUI** — multiple overlapping entity images (e.g. social proof showing 3 mutual connections).
- **Entity Grid SDUI** — multiple entities in a grid. For entity browsing surfaces.
- Never construct an entity image from a raw shape — always use one of the above.

| Component | Import Key | When to use | File |
|---|---|---|---|
| Entity | `40b12fac15193bb0b5664cbd26c72f603368ba1c` | Standalone entity photo. Circle = person. Square = company, group, school, event, newsletter. | `entity.md` |
| Entity Lockup | `0b807cb5b0dd6d0ddc9683329fc6d63deea643df` | Photo + title + subtitle + metadata in a horizontal row. Use in lists, feeds, and cards. | `entity_lockup.md` |
| Entity Stack | `0d4b272843a5e1efd07c8a01025ffa790c8a43fa` | Overlapping entity images for social proof (mutual connections, shared affiliations) | `entity_stack.md` |
| Entity Grid | `dbdc74e18bf4296df779f413500218320bf1c763` | Multiple entities in a grid layout. For entity browsing surfaces. | `entity_grid.md` |
| Link Preview | `7798b25c7d59c8592a7f92bb1067ce5de25c71e1` | Card-style preview of a URL with title, description, and thumbnail | `link_preview.md` |
| Expandable Text | `69f5adda9a5002122bbcfcb068d28ff908363094` | Truncated text with a "see more" control | `expandable_text.md` |

---

## Navigation & Layout

| Component | Import Key | When to use | File |
|---|---|---|---|
| Navigation (Web) | `0b21776a93ebc3e57427729d58570d8d37132052` | Global navigation bar — web | `navigation.md` |
| Navigation (Mobile/Tablet) | `45d9f851bab823cb7913cb5a3892aeb1de3af7d0` | Top navigation bar — mobile and tablet | `navigation.md` |
| Left Rail | — | Persistent left-side navigation panel (web). Composed of modules: Identity Module (`04c9bfe4c1602e964744238034d6d1afc0f3d9ed`), Growth/Premium Module (`50b5b40366afcb7996fdecdca94a3c72a92d8b9a`), Pages Module (`63eaf7a9acaaee6cc80d9ce068399893c5434b06`) | `left_rail.md` |
| Nav Link | `f727e7f709d152f9034c76cb52bff8efef5f6e41` | Navigation link item in left rail or header | `nav_link.md` |
| Tabs | `c0695d2eba6f7cb1e43092624d4b0b106d770741` | Horizontal navigation between content sections within a page | `tabs.md` |
| Module Header | `219b5ed52ac6dce3c388e0b20f4f9106ef6b4564` | Section header with title and optional CTA | `module_header.md` |
| Footer | `f2b74b3d6c682746524d10f7ecfb6cf83abc2694` | Page footer | `footer.md` |
| Divider | `3b0c67d9c4a881153bc04248e3ef40cecdab2b90` | Visual separator between content sections or list items | `divider.md` |
| Pagination | `20b4657fcfec563272e805aa04246d6c28cc83ca` | Page navigation controls for paginated lists. Dot group variant: `df8d6b5e7cd97026958d475269e131d4baa04bbc` | `pagination.md` |
| Pills | `cfba83f4e844992f7739387430f80192024f5dc3` | Compact filter or selection chips | `pills.md` |
| Horizontal Scrolling Action List | `13d9a4f2808366ac3de7d3b0f6a8b8ee99597afa` | Horizontally scrollable list of action chips | `horizontal_scrolling_action_list.md` |

---

## Feedback & Overlays

| Component | Import Key | When to use | File |
|---|---|---|---|
| Toast | `9190f3d9165ef84daf40d39588172c392b15eed7` | Brief, non-blocking notification confirming an action outcome | `toast.md` |
| Global Alert | — | Full-width alert banner at the top of the page. Current library versions are deprecated — confirm with designer before using. | `global_alert.md` |
| Inline Feedback | `5b5932a7b6048595b309809d7d5fa888da410870` | Validation message below form fields (error, success, warning) | `inline_feedback.md` |
| Badge | `6021f2114d8144d641c77e2e80796713f817366e` | Numeric count indicator on icons or avatars — notifications, unread counts | `badge.md` |
| Presence Badge | `7bf3065c078d6e3644675fd93950fa8d4e886bf2` | Online/offline presence indicator on entity photos | `badge.md` |
| Modal (Web) | `6834e1dd911d44f9dc098935b5d4d5da48555083` | Interrupting overlay requiring user response. Use for confirmations and focused tasks. | `modal_web.md` |
| Confirmation Dialog | `194b5cf58ccf1ebd42c2e5c684f3c04605fddcb6` | Modal for confirming or canceling a destructive or irreversible action. Mobile variant: `8bb78a1f4a7b986765163b2696626170ab7cd917` | `confirmation_dialog.md` |
| Bottom Sheet (Mobile) | `1fccf432779830ba326b1d5b8282bff12c632ed5` | Modal tray that slides up from the bottom. Mobile only. | `bottom_sheet_mobile.md` |
| Popover (Web) | `8d07dfd1f636e01cb76edbc243acfebea90108fa` | Anchored floating panel for contextual information or actions. Use when content is too complex for a tooltip. | `popover_web.md` |
| Tooltip (Web) | `a4e8f811710c71d9007aecafd6a5e55a4caf4b21` | Brief label or description on hover. Use for icon-only buttons and truncated text. | `tooltip_web.md` |
| Bubble Overlay (Web) | `3b1de57cf759e5a6cc031d1108978ee5d2b5c7ab` | Floating overlay bubble anchored to a trigger element. Detail variant: `c9a2c225d0d0d606547712cc126262f58587a1ef` | `bubble_overlay_web.md` |

---

## Loading & Progress

| Component | Import Key | When to use | File |
|---|---|---|---|
| Skeleton Loader | `61553fd02c482f4a2d83aa91866a5a4d096b8a80` | Placeholder blocks for content that is loading. Key is for Skeleton Text SDUI. Additional variants: Button (`8de9c57c4c2d6837c4db60dafd30bf59e2ed7d01`), Icon (`e06cdb146ced6ccb2cb529f8320b1d978f50b305`), Entity (`2aef2cb7b4eca05d78fdce4a3f19859b2ac1c0d7`), Image & Surface (`a1e89083abb70e38799d6bcad768b70170a6edce`) | `skeleton_loader.md` |
| Progress Indicator | `0ac453eb391125cd5584ca9b57de44a902cd4f91` | Shows completion progress — linear or step-based. Circular variant: `d10ce84cab111554c62b305a9013d980cb727e21` | `progress_indicator.md` |

---

## Media

| Component | Import Key | When to use | File |
|---|---|---|---|
| Carousel | `94349cd3e74a0b96fd3f08c0b21626e38af94278` | Horizontally scrollable set of content items. Continuous variant: `a8a162c64a47e97e5745f2b9de7267ce6ebad0b7`, Spotlight variant: `29c9a3257d4016fe5e5d866a808a9fd9679e3b41` | `carousel.md` |
| Media / Document Carousel | `d53cf6216d97965df18139d6f864e7145d519f28` | Carousel for photos, videos, and documents | `media_document_carousel.md` |
| Media Scrubber | `d3eab06cec3cfc651185cbe06e9aea2dbbe3c615` | Video or audio playback scrubber | `media_scrubber.md` |
| Media Toolbar | `cd3b5fdd5404e26496ecd0e306266e98e0c5882d` | Toolbar for media creation and editing actions. Key is for Document Toolbar. | `media_toolbar.md` |
| Emoji / GIF Picker & Reaction Bar | `bc1a532e33ea088a24a313b2794ff52c96d8aea4` | Reaction and emoji/GIF selection UI | `emoji_gif_picker_and_reaction_bar.md` |

---

## Data & Structure

| Component | Import Key | When to use | File |
|---|---|---|---|
| Table (Web) | `9515ace8f8616d7f2009b8f7c8fa7022c6436b6a` | Structured data table. Sub-components: Table Header (`d411732d2c0eb90018ebc76cafcb990394489f89`), Table Cell (`dfb8bcdb4e995f0efa77c3992b737f400a42ec88`) | `table_web.md` |
| Timeline | `8c76db4726e1b9fb886f2cdec67df0fbb08cc6bd` | Vertically structured timeline of events or steps. Timeline Item: `8426885863abfa14decf093c974911eea94aed52` | `timeline.md` |
| Reorder List | `658a1aa81bb43d544686f55a35b543df0d4d1f24` | Drag-to-reorder list | `reorder_list.md` |
| Accordion | `660f901d226b02e9001324ae790a3c874cc01169` | Collapsible content sections. Use for progressive disclosure. | `accordion.md` |

---

## Search & Filtering

| Component | Import Key | When to use | File |
|---|---|---|---|
| Global Search (Mobile) | `e97aeebe70d0aebde3b7d5486429197d3354d2f3` | Search bar and results overlay — mobile | `global_search.md` |
| Filter Panel (Web) | `5e25b2783ef583a730f94ade494c040a835b2eae` | Side panel for applying filters to a list or feed | `filter_panel_web.md` |

---

## Empty & Utility States

| Component | Import Key | When to use | File |
|---|---|---|---|
| Empty State | `a689bab18560e8b8090989dfff080ee4b66588ca` | Placeholder when content is absent — zero-data states | `empty_state.md` |
| Tag | `ca9c959ca7f267eafdc02acd80beba407272c814` | Compact label for categorization or status | `tag.md` |
| Menu | `fa2e97830c0afec9f19594106a096cc02e10c7fe` | Dropdown container with a list of actions | `menu.md` |
| Menu Item | `8c12b93b2f44cd496136229bf4c773337d75bae5` | Individual item within a dropdown menu | `menu_item.md` |
