---
name: illustrations
description: Illustration types, sourcing rules, sizing, color, surface, spacing, and usage guidance for DS illustrations (Microspot, Spot, Scene)
---

# Illustrations

## Overview

Illustrations play a crucial role in the Mercado Design System, helping to:

- Establish the LinkedIn brand and engage members more directly
- Simplify complex ideas through non-verbal communication
- Maintain our brand personality consistently
- Provide context, enhance information, and add visual interest
- Infuse humanity and warmth

Illustrations should accompany informative text blocks to enhance the user experience, express the brand's visual language, tell a story, clarify complex messages, and guide users in taking action. Consistent imagery usage fosters brand cohesion across all experiences, pages, and external communications.

**Authenticity:** Keep illustrations authentic. The World of Work serves as the foundation of the illustration system — all illustrations are grounded in real, recognizable scenes and objects from professional life. Do not invent conceptual or abstract illustrations.

---

## Illustration Types

| Type | Description | When to use |
|---|---|---|
| **Microspot** | Small, object-based illustrations depicting a single real-life object | Compact spaces, lists, limited-space layouts, supporting UI copy |
| **Spot** | Medium illustrations tied to specific UI states | Empty states, error states, success states, feature/product promos, empty pages |
| **Scene** | Large illustrations depicting people interacting in professional environments | Feature promos, marketing, humanizing data, pacing long-form content, reinforcing ad messaging |

---

## Microspot Illustrations

### What they are

Microspots are compact, object-based illustrations. Every Microspot must depict a real-life object that directly relates to the action or context a user is experiencing. Do not create or use conceptual Microspots that aren't grounded in real objects.

### Sizes

Microspots come in two sizes:
- **Large** — use in spacious contexts where the illustration is a visual anchor
- **Small** — use in lists and when space is limited

**Do:** Use Small Microspots for lists and when space is limited.
**Don't:** Use Large Microspots when space is limited — if your layout has limited space, revisit the design before reaching for a smaller size.

**Do:** Use Microspots at their designated sizes (Large at 100% scale).
**Don't:** Resize, crop, or stretch Microspots. If your page requires a custom-sized image, reach out to the illustration team.

### Color

Microspots use a structured color system to keep illustrations grounded while allowing accent pops:

1. **Cool Gray 70** is used to ground the subject matter — the base neutral that gives the illustration visual weight.
2. **Accent colors** (e.g. Sage 30/50, Warm Red, Amber) are applied selectively as pops of color to add visual interest.
3. **Cool Gray 40** is used in main subject elements to reduce their prominence relative to the accents.
4. **Additional neutral variants** are applied to secondary elements (e.g. doors, background details) to create depth and distinction.

**Do:** Aim to use one to two pop colors at most.
**Don't:** Use two highly saturated accent colors within a single Microspot — this creates visual noise and competes for attention.

Microspots adapt to both **light and dark mode** automatically.

### Surface Placement

**Do:** Use Microspots only over `color-surface` or `color-surface-tint` backgrounds.
**Don't:** Place Microspots on colors that aren't surface or surface tint — this can cause visibility issues. If you need a custom background color, use a Custom illustration designed for appropriate contrast and visibility.

### Spacing

**Do:** Align Microspots consistently to content within container content areas. Provide ample padding — sufficient space around the illustration allows it to stand out and supports the balance of the page.
**Don't:** Align Microspots to the edges of containers.
**Don't:** Overuse or overcrowd Microspots within designs or layouts. Choose the most important areas and direct the user's attention intentionally.

### Usage

**Do:** Use Microspots that illustrate an object based on the action a user is taking.
**Don't:** Use or create conceptual Microspots that are not based on real-life objects.

**Do:** Use diverse Microspots to add visual interest and variety that supports the copy.
**Don't:** Use similar Microspots with subtle variations for consistency. A strong Microspot should convey its meaning independently, even without accompanying text. If two available Microspots are too similar in a given context, consider using a System Icon instead or reevaluating the overall design.

---

## Spot Illustrations

### What they are

Spot illustrations are medium-scale illustrations used to communicate specific UI states and contexts. They are more detailed than Microspots and always tied to a meaningful moment in the user experience.

### Categories

Spots are organized into four categories:
- **General Usage** — supporting content, feature promotions, informational surfaces
- **Error States** — communicating errors or failures
- **Empty States** — indicating zero-data or no-content scenarios
- **Success States** — confirming a completed action or achievement

### Diversity & Inclusivity

The Spot illustration library is intentionally built with diverse human representation. When selecting Spots that include people, consider the range of illustrations available and choose thoughtfully to reflect the breadth of LinkedIn's member base.

### Sizes

Spots come in two sizes: **Large** and **Small**.

**Do:** Use Spots at their designated sizes.
**Don't:** Resize, crop, or stretch Spot illustrations. If your page requires a custom-sized image, reach out to the illustration team.

### Color & Surface Placement

Spots that include people use a more nuanced color system than Microspots, since they need to represent human figures realistically:

1. Certain colors outside the standard ramps can be used for added flexibility — **skin tones and hair colors** are intentional exceptions that ground characters in reality.
2. **Accent colors** are applied to clothing.
3. To enhance depth and differentiation among clustered elements, an additional range of **neutral variations** is applied to secondary elements (e.g. trousers).
4. **Secondary 20–30** is applied to background shapes to reduce their prominence.

**Do:** Place Spots on `color-surface` or `color-surface-tint` backgrounds — these provide the intended contrast and ensure the illustration reads clearly.
**Caution:** Avoid using surface colors for Spots that do not provide adequate contrast with the background tone. If contrast is insufficient, the illustration can visually disappear.

Spots adapt to both **light and dark mode** automatically.

### Usage

Appropriate contexts for Spot illustrations:
- Feature / Product Promos
- Empty Pages (zero-data states, onboarding surfaces)

**Do:** Use Spot illustrations minimally with generous padding. Give them room to breathe.
**Caution:** When using multiple Spot illustrations within a flow, be mindful of the goal or message each illustration is meant to accomplish. If they aren't clearly helping communicate the message, consider using custom illustration — or reducing the number of Spots in the flow.

---

## Scene Illustrations

### What they are

Scene illustrations are large-scale illustrations depicting people interacting with their environments in specific, easily-recognizable professional contexts. They are grounded in the World of Work — LinkedIn's core illustration foundation — and convey a sense of place, collaboration, and belonging.

Scenes have the ability to:
- Help represent multiple human interactions in a professional context
- Drive home a feeling of collaboration and belonging
- Provide additional context and reinforce messaging in ads
- Humanize data and add pacing to long-form content
- Feature products in marketing

### When to use in product

When incorporating Scene illustrations into a product, simplicity is essential for ensuring clarity and visual impact. Appropriate use cases:
- Email Headers
- Feature / Product Promos
- Cards
- Onboarding

Avoid overloading product UI with Scene illustrations — their complexity can compete with functional content.

### Cropping & Masking

Scenes can be masked into shapes for layout flexibility.

**Cropping:**
- **Do:** Create visually pleasing and effective crops. The illustration should read clearly at the intended container size — all key elements visible, scene legible.
- **Caution:** Be mindful of responsive design when cropping. A crop that works at one viewport width may cut off characters or shift the focal point at another size. Test at multiple breakpoints before committing to a crop position.

**Shape Compositions:**
- **Do:** When masking a Scene into a shape, strive to craft visually captivating and impactful crops that elevate both the message and the overall design. For example, a wide bowl/semi-circle crop can reveal a group scene with clear sky above, framing the figures naturally.
- **Caution:** Generally stick to masks like circles, rectangles, and squares. If you want to use a more expressive or non-standard shape, reach out to the Brand Team for guidance.
- Illustrations and shapes can work together to create an enticing, cohesive message when the crop is intentional.

---

## How to Import

All illustrations are individual components sourced from the **DS Icons Library** (`s1GLDCHfC8f6ZV1aYcWmZm`). Import with `importComponentByKeyAsync(key)`. **Do not use `search_design_system` for illustrations** — all variants are pre-documented below.

**Dark mode:** Use the "On Dark" variant when placing on dark surfaces. Light variants are for `color-surface` / `color-surface-tint` backgrounds only.

---

### Microspot Small — 82 components

| Name | Key |
|---|---|
| Address Book Small | `bf8a56408c65c23998042ec048b4248899ee5c70` |
| Article Small | `486b48d88616774e6a30d78ec8db1b0c0d5a3b61` |
| Article Stack Small | `267dc4dc68b3910cc9c7815d7e1d354cd411d8af` |
| Award Small | `559c2bd9a2a4964947171452b1e549b431225816` |
| Bell Small | `19a588ac7943f00acb6417724ca436210472bef1` |
| Binders Small | `89b173a1edecd9fffdeb9af7b2fa5ec1e4647ad4` |
| Birthday Small | `2de9a4e8792aa9a874650dcb97cb38aadda7e536` |
| Briefcase Jobs Small | `1bbe321eedab1054d08ee94055ecf45dc22285e6` |
| CVV Back Small | `24a42abc08b22ac3e38f001aa83e9055ead45ae0` |
| CVV Front Small | `be73b7bd80dff010a552e7179e5c3fe08ed80ee2` |
| Calendar Small | `1be8b2019471133b5aa0485b56ae53e483ea2e07` |
| Camera Small | `8cb4e4c573acc4c1c4f12db07d326f4f7dbd779a` |
| Certificate Small | `e55c96df5bb162fc6b1004dc12f37ba8c85a132b` |
| Certification Small | `4669549ab4e7918eaf26dfb67a11451ef9f2c727` |
| Clipboard Small | `b11d29cf411c16b31f191b2981a75dee9f596adf` |
| Clock Small | `4d0e7ae43fad4c7903b2ef40920b1e9090657f80` |
| Community Small | `c703cd04430f917020afa10afd7e494de3a95758` |
| Company Small | `419caa8cd9a8a35f95d90327a23676a1615b1903` |
| Company Verified Small | `3c181ea01fa17cce420867f18dcba8eec2b063b8` |
| Compass Small | `6b4061c3e66c11bec4602b7920fa2980a12e3b11` |
| Credit Card Small | `c16a4db112e9cc272867939603737938db866938` |
| Dartboard Small | `4b611cd51bc19d10889f739f86bf761f5950ad34` |
| Document Comment Small | `42e45a208d195b8e1b28458a6f0fc6c7359bd9b5` |
| Document Folder Small | `698b07be7da9f2b0ba56a825b939ce9fdc9a6c52` |
| Document Report Small | `7c7b7f5f3767438ae73aa20a9c7a835590f5c9a0` |
| Document Small | `0aac8c2c89f7faf1f710748fd2f832098ddb2954` |
| Flowers Small | `2cadecf157640616970519df36cd3262e8cd91ef` |
| Folder Small | `e7ecfa90f19e88efcd8e6518d32203688f7d77c2` |
| Gift Small | `78dc3365b1f061bee9e53f91feac55311cd7dae5` |
| Glasses Small | `98aeccacdf684be2b5375470c0ee24e9aa7487f4` |
| Globe Small | `d2bed209230a4ae85104b7ae12484dba71d510aa` |
| Handshake Heart Small | `1b777e6287f73427df5773f4b572a4665ca7771f` |
| ID Badge Small | `5929ac8298a427da3d3454e13e8f1c5415a7a6ff` |
| ID Badge Verified Small | `14dbde4183eee426dd589e8c52aae4ae1342f69a` |
| Image Small | `cb9c4b2d4f10a96e59615f0d1fbf5922fdccbf9b` |
| Image Stack Small | `13eeb93b3b0b491e7dbb4a9fc4430f8030733b7c` |
| Industry Small | `1d45bf8fb459a82af9fcb970af740c23f2a94fbd` |
| Lightbulb Small | `fcf8ae0c36ff2aa10da8183b7b2ccf72554bf9aa` |
| Location Marker Small | `37a56de747c5f6a70a08a0902e7ea8c583058cfe` |
| Locked Small | `309a20f9dcf4fe798ba67af64594d878bbb84aed` |
| Magic Wand Small | `e73c5402c1c7e840e071a882dbd39e2a3c4a9763` |
| Magnet Small | `3895cabe10b7b705b5a66102d6e673e83bd57083` |
| Mail Open Small | `539a53a4e59d85e973d49d4cd6e266ab8ac38ba5` |
| Mail Small | `fd8e4d4de5ab6b893caceafc6fd866e7b5eaa445` |
| Mail Verified Small | `a0aba8beca0121b1bf735b18d4d71a2fdf363157` |
| Marketplace Small | `c8a9572dbca396cf9d751278670691a43624d417` |
| Megaphone Small | `677c79216f50ae9ca8e2dab09fda10decd6f3d72` |
| Messages Small | `38d0e2e45d6890e24edc3d7755c72cb9f5770fa0` |
| Microphone Small | `730098339145122ee4989d1432eea8458b33be66` |
| Notebook Small | `f740200159026377254322912128fdf6bd8346ff` |
| Notepad Small | `91ba215eda062394d2af3eba61e3ae35b9651566` |
| Passkey Small | `0765038c587ecde31e6b359008e9140f3532b7b0` |
| Patent Small | `ed546deb0e5484dc0a342d27e6c11bf7f951cacf` |
| Pencil Ruler Small | `4089a2eac4ce14e5473a7181dbca68bd6161a166` |
| Phone Handset Small | `dda2c5fc2f81b62bfd456a4be46e72c3957a1ddb` |
| Phone Small | `f4b7dab93b422ad70840fc317c1af765690e19be` |
| Receipt Small | `446aad4adb02532f834d4071ebb348fd106da274` |
| Rocket Small | `ba58fe15d20f3c14de7748a81c2a3e15f6f03425` |
| Salary Small | `9d1ed4f11950ac2006a388ae804ffbe8a2c448ee` |
| School Small | `f9edd29793b2bdef188bf47b2e81985d0dcd53db` |
| Search Small | `10853e84da4a9605dd40e631e27bace24a62f517` |
| Self-ID Small | `9b063ff0cd8dce824158e79b600231845f88b5bd` |
| Shield Small | `ec2898c621d9a5a2d25f94364cd9bb6877939a55` |
| Signal Caution Small | `0bc7098c65b9d3a75986ce35ba39a9a563816e3c` |
| Signal Error Small | `1d128ece88bea1d6eb296c01b21cf22de4dc1924` |
| Signal Success Small | `ee774c4010deb411e69243a12f0afa4eeeefb9fe` |
| Slides Stack Small | `b5fa6611cbc57e16d0f88f8e2bd4af26e2832b6c` |
| Sparkle Small | `b6c08c6e2276064bc6d05dd8e61d61011d94e3fd` |
| Spotlight Small | `8f5e43cce635161cd5b3746875fa4a55b853830d` |
| Toolbox Small | `cdcf4582ae8dd9eadb1221f1209b935a9527e510` |
| Trophy Small | `d4c90e70040b11580f371c7e6ef6eec04c5ffd63` |
| UI Chart Small | `efcbea614d8cab84fcfbb8c39027ccb861a9e5bf` |
| UI Chart Trend Small | `21742076f4294eca16cc94ae5cf5b0ddf93e31f1` |
| UI Dashboard Small | `670cab8e976aca0b4a39c9e50e46d2872c5001c8` |
| UI Feed Profile Premium Small | `9f7c77e0237981765061e17a09da7064152e42ee` |
| UI Feed Profile Small | `c53b321c565a704c4f73c868756de37c1d26315e` |
| UI Website Small | `8f9658723669a7bceabfee7da4dc432821d9b6e9` |
| Unlocked Small | `c8ba7306326122c47117bec6e5027e8e28271520` |
| Verified Small | `e440fd9bfbe4cd57695e7b301efa0ac52386425e` |
| Video Course Small | `3b6be78618f507b402b06d2a7c4289f5973933fa` |
| Video Meeting Small | `dafc55adf46d7a428d2e38391469fdf505392ae3` |
| Video Small | `d935d901b47709f7268443af6e8fb1684192d59a` |

---

### Microspot Small On Dark — 82 components

| Name | Key |
|---|---|
| Address Book Small On Dark | `6454d810a7f702b3ab5c0a01338bf8512b8f43f4` |
| Article Small On Dark | `f03200a16a13dacfadf935055477ebea51a8ac72` |
| Article Stack Small On Dark | `5e28176d2ade68f8562f7e192ee008ef1c850b2e` |
| Award Small On Dark | `620dbc1222117d17a3b6e8fe65a8edf23b031295` |
| Bell Small On Dark | `8a380aed70a16bb0a4e13e79ff34057b6707e103` |
| Binders Small On Dark | `e1b7f6326f6ad03d46023598a3a76a1335c23c06` |
| Birthday Small On Dark | `a981848c72e623d31cbc64178c7daa081ca19bff` |
| Briefcase Jobs Small On Dark | `96e3c3fb2f6e5c685f175564f7da193750ac2e7b` |
| CVV Back Small On Dark | `71b786d239e92db9efe1cb5914b8aaadd6faace3` |
| CVV Front Small On Dark | `c3cd1b5a39782b72bb247fec6708ce346499d422` |
| Calendar Small On Dark | `638d0594a0956e63892d0b24428b9d6fec508e66` |
| Camera Small On Dark | `47264b62a4573d02bf0e87341893ee66e742104d` |
| Certificate Small On Dark | `90a0b1ca42392dd0aacb1df126334d2d46a2bb8d` |
| Certification Small On Dark | `3cf325b713b0a8f4680740f724ecbe73627b791d` |
| Clipboard Small On Dark | `86e213411d63001e142bc377d9e3f20eebc8884e` |
| Clock Small On Dark | `fbc3720bbe070de045f98a12d3010953573ba556` |
| Community Small On Dark | `b3723e6667dcb454029b40613376ac47af2ec6d5` |
| Company Small On Dark | `1a334c0148c15d2c300d163ad245b3219e007985` |
| Company Verified Small On Dark | `f15a013cf9720d039cf5edfb516cc02130c6b8fa` |
| Compass Small On Dark | `70ac6864161805902ff6f5d33d687624c26e4528` |
| Credit Card Small On Dark | `de6b41f53be1a83c25eb8ca76ef499d4bf9eedeb` |
| Dartboard Small On Dark | `68838f7666d1127d998af23d656609da784f36ee` |
| Document Comment Small On Dark | `73b716d301b041772d80b3d185f6280f090981ea` |
| Document Folder Small On Dark | `a5a06085517606b07fbe728ce31abc17e528255c` |
| Document Report Small On Dark | `0a38246089cf89b1dc417c2578dc34dae27c7675` |
| Document Small On Dark | `0df229a5f7d1ad485ccc7efd925147cc760275a0` |
| Flowers Small On Dark | `c8b8777d6672ccc39a8481fae7a24b7f50fd562b` |
| Folder Small On Dark | `52d9169ec19f18c54497a531d8acdedd18f618d9` |
| Gift Small On Dark | `7b4d7daf883917e21b4757b5c7aa72f79eac9458` |
| Glasses Small On Dark | `5f0c0a67ddd25ce53440e41f7ce38537681b597d` |
| Globe Small On Dark | `f453864f5df0bf08cae325306e860a26ef2fcac4` |
| Handshake Heart Small On Dark | `509adcdf0483bac6a629d58fadd6ce7eb19b0193` |
| ID Badge Small On Dark | `91093fc630adafc4d0127e3a5791af8d0e296f3c` |
| ID Badge Verified Small On Dark | `22486e24bd9dad5437493368fa1b70c5a1706ac1` |
| Image Small On Dark | `c823af2c0f454df2ca2bdd2982740d21e1b96d19` |
| Image Stack Small On Dark | `414d52dcfdcabcc36d778daa23ce28a9b6d46b7d` |
| Industry Small On Dark | `43f24ff063f3cf7ac845fd8ca30b5e6b49b422ab` |
| Lightbulb Small On Dark | `9847e9c45a59c1933830af9105e2ca35900cf990` |
| Location Marker Small On Dark | `514179153ab03963f75fbff44aa5c3bd99e318e2` |
| Locked Small On Dark | `418e970d19b0cdd6837de77052ca4ed4c9d221df` |
| Magic Wand Small On Dark | `32b6cf2eee8fb3ae6ae9298937d81fbabec9c1d9` |
| Magnet Small On Dark | `ec3cede6c6a1a6ba04f6f7b1707f4d6a85aad5c3` |
| Mail Open Small On Dark | `86a4629630f67b326811f9f930d372454402a741` |
| Mail Small On Dark | `6b3ca4b8b211b436ca2ca971bcbccf4c80173479` |
| Mail Verified Small On Dark | `4ecb835fa49355185e15c9448dd512f6a68be805` |
| Marketplace Small On Dark | `b460a0ff3b8d91b7bb5468671556711061b38acc` |
| Megaphone Small On Dark | `7f55d008d8c5ed36ad1f403f89d45dd20a986ba8` |
| Messages Small On Dark | `f0f12f2ffbe687d7f84d8cbaaf54d2c8bdb60b73` |
| Microphone Small On Dark | `1516c4ce2354dadbc7a5b7283921f852acd381e0` |
| Notebook Small On Dark | `3be5b23023d7ed5f46d35a19d9aa113c5a22ea97` |
| Notepad Small On Dark | `23175f670bf42a2d46eb6dd951f65f878ef4ae4f` |
| Passkey Small On Dark | `91812d5d624f85fc1748629993a0451f75cf73f2` |
| Patent Small On Dark | `0f3624bcf36f5e3743a6d99af7ca6cb3fb2ba0b4` |
| Pencil Ruler Small On Dark | `3940c185fc8df3b276c0835d4f9a4e071cba8920` |
| Phone Handset Small On Dark | `3baf771a6c2740f345f9700ae7c58d088e1e3a1b` |
| Phone Small On Dark | `ac4a9824730447e57008265cb641737eeec4b7a3` |
| Receipt Small On Dark | `09ed768bccb1368d50795a51a0ab4de3b448014c` |
| Rocket Small On Dark | `4d9cb6295e124cb8f070fab28fda4a057feb9265` |
| Salary Small On Dark | `3edce3e5ed3c86b4dfca8f804e06c957efcd15b1` |
| School Small On Dark | `253b013ea7b9407727525c883c4ceef859d801d0` |
| Search Small On Dark | `31b1a6ecdfba3953591614c1f4b8b12547e9163f` |
| Self-ID Small On Dark | `7ff74799a1dc6a8edf17b2bc8409a344913340c0` |
| Shield Small On Dark | `c2e82ad472931b65b904e60e23715320d8909a96` |
| Signal Caution Small On Dark | `3b6aed67bc881fb36b6c085fcd22a027101f6024` |
| Signal Error Small On Dark | `3fa93d06e5cc63da3236d12fd764c448e5602ba8` |
| Signal Success Small On Dark | `c31c975f1b9c162f7ee3b52e6c7fedc83a2f1a42` |
| Slides Stack Small On Dark | `df868bf37dea36cf3435874421b977f9b1f5ad34` |
| Sparkle Small On Dark | `f99b147137d2bbc13230040d0caa2741294beb0c` |
| Spotlight Small On Dark | `67a989058c717c39ebd90d7a6c517cf3bea57263` |
| Toolbox Small On Dark | `4723a8715e016a5bccc051dbb3378ac81c8852e0` |
| Trophy Small On Dark | `98e60b5d1129ed473b378207f75449c10a148813` |
| UI Chart Small On Dark | `8af71d692fe8c07b263aed395ac0a219c91a8b48` |
| UI Chart Trend Small On Dark | `204439a7cb39182d2eb4b7bdf07fa888d1564397` |
| UI Dashboard Small On Dark | `ca0eb95ff5c47cd5986f300f918299f015877302` |
| UI Feed Profile Premium Small On Dark | `2275549560272168ec0e1b572a546219c090f3cd` |
| UI Feed Profile Small On Dark | `76e91fbc4f591025ed57bd4f62610103fe237006` |
| UI Website Small On Dark | `121887216b1fb80fb8ac062c5e061b4b05b742c8` |
| Unlocked Small On Dark | `63515e9959b0de9c7c6029542784db2716dd87f1` |
| Verified Small On Dark | `f1e6a98c6e32d08d17f9652ced6b7e79485a7c39` |
| Video Course Small On Dark | `98d748c194483f2ec6e590f2eef7e3613ca8ebe9` |
| Video Meeting Small On Dark | `671dd26ff25b68a7fcf0316200442c75068d2551` |
| Video Small On Dark | `5729133602ba0f76780f0bef5b5f0c9529d48dfd` |

---

### Microspot Large — 82 components

| Name | Key |
|---|---|
| Address Book Large | `4888718695bc23a5cdacb1ef8c308b68b089f203` |
| Article Large | `2c3ea21576c49ade93c2d630da72d4c692b35161` |
| Article Stack Large | `e0c2269fdfe260fc828858af5a4614a2a0266e10` |
| Award Large | `43af82d4b4a05722c6b118266f0071ae885e3459` |
| Bell Large | `99e5f9a2252c731e0025bfd1fda9d8eaedd654b5` |
| Binders Large | `fead9d3dab285c47e85b41e39dd342f4b5d7e2d1` |
| Birthday Large | `32c714b4884e84e6ee817afc1a1771edcf8206ce` |
| Briefcase Jobs Large | `510c53c3545dd523316025bff0d84187b7be1cca` |
| CVV Back Large | `c166990ce68424e4b77998bf5a3721d5286c5cc0` |
| CVV Front Large | `7ca6bc1d6e0272ee1fba2f6a878b6d0b33dc4a56` |
| Calendar Large | `7c2185949adb9f8270b89bf5c7e8c339376f8bc7` |
| Camera Large | `bc38eb8542062cee3cc60782d012c9034a8f1d80` |
| Certificate Large | `065fe575b6fb233ffe0e4e39a49d51b47522ad6e` |
| Certification Large | `ded05e8450aa5a2daa80316a02e34794b9bde90b` |
| Clipboard Large | `85313ae56d37dc365eb35a23d6e11ba127dab7c4` |
| Clock Large | `538a047a1e9d0a7d881438b5bbb29cd66a2f4725` |
| Community Large | `b38c47d3d5ab5afbe076169b3bd75c64a6ccc714` |
| Company Large | `81e668dc7734051e5978ef9fd3b975cf2bf72fd5` |
| Company Verified Large | `96792588ccea421613d601cd96b83d3b5419bfeb` |
| Compass Large | `0f898f69bbace1118dbf867068ea184ed6b840af` |
| Credit Card Large | `d24e8610948399130e2f99b4612e7c55553d5fb5` |
| Dartboard Large | `0a70bcab022ce4665db4547264055ec7665afc98` |
| Document Comment Large | `7d2a2bc647556129b9a5588ba59c7aca445ea509` |
| Document Folder Large | `918fcffb965c18d0b1003249098e78c05b217781` |
| Document Large | `c4a15de5d673293f33b63558490ea272e2e76a62` |
| Document Report Large | `db58c6cbb07723721b776c8c149c6dcfffc03dbf` |
| Flowers Large | `4e465718717b223a9f734eba276d1f7d05970072` |
| Folder Large | `343e32fa42c3faa808a5f04a3451c0f80969da34` |
| Gift Large | `0ed9ed45608a73acabf3dc6325c2285677dea100` |
| Glasses Large | `7b8d39634580ca6dcfa39df086c6859d8c0ed8ad` |
| Globe Large | `1468c34e1e97b94beb8eb81b2054607a542bfb21` |
| Handshake Heart Large | `b5695e51293897b162d2264f1efa223b9aac3c8b` |
| ID Badge Large | `2007c2baba7f04cd74ec1f085bbcbbbfb359f931` |
| ID Badge Verified Large | `7fb69fd305e51853d295d6eb52b1bba0582318b0` |
| Image Large | `5968517281625e11c85fc87dd5dd29656b4ae3a2` |
| Image Stack Large | `026c1372889af973bb0645aae7f14e4096f5061c` |
| Industry Large | `40d709cba62ec561d88ad3e6adfd897ec195cf39` |
| Lightbulb Large | `3023728e49f48c4a13fec10038f1098cb8954f2d` |
| Location Marker Large | `24268dc65415d0d06757037d866a15b92f9c2417` |
| Locked Large | `f278351c22b6c23865a408b2953de7d45d0e5a6a` |
| Magic Wand Large | `5efb7a779e4410bd4115416c1302affd842208c3` |
| Magnet Large | `afff78d34ec51bfe41250eb4607fb5de08aa97ce` |
| Mail Large | `c7222e505d9bdb41e29694df4b07386da664243a` |
| Mail Open Large | `d7c0930d4aa7ab6ed68816494a35dad97f6391ac` |
| Mail Verified Large | `31f5c1854e7ec37bb6ac4cc7ca0115d3c3e4f191` |
| Marketplace Large | `052b9371e17d4bac4b2655efae35c06a7c41c859` |
| Megaphone Large | `6aa546b4fc1ea94877860afb410d8979db7930ab` |
| Messages Large | `00b02d1d2dd470e70bd5990f51c5d2da0331e45a` |
| Microphone Large | `7823c0c71621cfca98aa05752f314d0df1661bf1` |
| Notebook Large | `b9bb9e983d43e5ce4ae021ea90e7929338028566` |
| Notepad Large | `c4491951f215e77ca61e2bf166213468de574911` |
| Passkey Large | `491dc9fe95b780f06fc1b1453d6877aa0c77f06b` |
| Patent Large | `19d61912cd8aff1d063d3a129f7348c08effbaf2` |
| Pencil Ruler Large | `abbd6bff50745b61bdb543a6742f7a77793187ea` |
| Phone Handset Large | `fba2a08dfb28e41df354e2b2eb533594a3beba2e` |
| Phone Large | `6aefc9a95e6c19b153e5beb3480b190bef6e2ca8` |
| Receipt Large | `07e0a142e3c663530a1956381e539cc3ee3f5efd` |
| Rocket Large | `40cd9bc8c225e389ccf3472af858a85b89fb40e1` |
| Salary Large | `fa33226d8ad09caead851ef53c388507d49208f8` |
| School Large | `713183972fcfde63e5f4e16a0eda33c3f92ad726` |
| Search Large | `3a62ade69d2dd338bc607e3649a59c634b055cfd` |
| Self-ID Large | `ab0d6aaf72ea093aef04492d5491d90baa362e48` |
| Shield Large | `21fc14c6f41051b1b0ad7dc2d6da195625bce20f` |
| Signal Caution Large | `624a04bb3aa7e3083886cc8fe947efd168898d07` |
| Signal Error Large | `62688c7adb8cc92b9a328d3c2b6bd373a0bb79ab` |
| Signal Success Large | `047825d57e972bfef004a982a422bba9dea89928` |
| Slides Stack Large | `d65523b6b893ab27cb74b60d416635c40274cfd4` |
| Sparkle Large | `ee1fa5a2019fcaf9bc45b94a98fd42a8b6a514e5` |
| Spotlight Large | `e1a986da0513a0b9dbcbbb77df4ab0d666685b3f` |
| Toolbox Large | `a771db7eb82cef8476050c7eda7f70499316257b` |
| Trophy Large | `25a1911b602249d5e1da71ea62ed94d1b673fe74` |
| UI Chart Large | `2e09f078e649aa01a865fef4abfff55aef37fb40` |
| UI Chart Trend Large | `10d481e4b64c5a5473a129c9f3f5147cdfa5d579` |
| UI Dashboard Large | `519550e5bc4cf818bbebe9740872846bc4efb1b4` |
| UI Feed Profile Large | `e4b6309662f9244b4f3c3dd0fb3e6e8fe8737525` |
| UI Feed Profile Premium Large | `84ffd93ebe5977cb545acb5942b1205d8983ecfe` |
| UI Website Large | `35ebe74070c2d35702ccad81673b845d1566233b` |
| Unlocked Large | `3d5d0e059bacdd1f858349b6c4d4dda842c0db05` |
| Verified Large | `af1d4236c7859a21331c9d1282118bf0e84b1e58` |
| Video Course Large | `bc81a73234e922bb68de5e2139966ed4d3e71698` |
| Video Large | `106e0d08cbe0de1fd28241ec1d3f613075b99073` |
| Video Meeting Large | `e5e0b4b54dc73b77a81821a2d0f89f33d961f41d` |

---

### Microspot Large On Dark — 81 components

| Name | Key |
|---|---|
| Address Book Large On Dark | `c83fe2065d0603342e4d77ed301185ebeb475447` |
| Article Large On Dark | `f040dfcc008c49ea6418f71df31d8b3dd0d7f90e` |
| Article Stack Large On Dark | `8e250467ead1d7942515ef928378b2f8bc2187a3` |
| Award Large On Dark | `d3c08f5a2b42b67240f626f612da33b4b4f5be1e` |
| Bell Large On Dark | `1bdb0c2c8ce8c3194696b4af68342afb4c74bf1d` |
| Binders Large On Dark | `41c6a9d35b2a74241bc0b36599c6ac6df851fbaf` |
| Birthday Large On Dark | `21ae76d6e7da9bf447e6abdae478e88cb8c20b18` |
| Briefcase Jobs Large On Dark | `f4947d7b523bf96bd118431ba4ecfa60af16058b` |
| CVV Back Large On Dark | `e73e67b39a93cd1132138ddeb3b2e4c61290f57b` |
| CVV Front Large On Dark | `6626c9f2db4fdbe22a04ea245b70f2740169d185` |
| Calendar Large On Dark | `6f7a05460fda592b370cf4821283ebd606935b13` |
| Camera Large On Dark | `42271e5a7d3d71ae6a1c4e91381be21d0e6b06e5` |
| Certificate Large On Dark | `59a6d76c2c5200a182a83ffeb9dda306f1fb0d68` |
| Certification Large On Dark | `9b5301aa3aae376e5a0125b1aec3e8eab66b19e6` |
| Clipboard Large On Dark | `b17521ef8a598438274166ffb5bb09560bd997c9` |
| Clock Large On Dark | `8ff67dca68c15129cb5af008f17921c12eb67aca` |
| Community Large On Dark | `84d077d53627b679e8cae58a202a16db621987a6` |
| Company Large On Dark | `3d1e07e172bc77fa9a9054bac7b8aef0a39b1594` |
| Company Verified Large On Dark | `26f5b4461e2181908d4ef80f75fea344ede8dab7` |
| Compass Large On Dark | `a0f38095ab3fb0e54b15036bc335fdb9d446ad79` |
| Credit Card Large On Dark | `fa0334d8878ad58b27854d1f10cc098af3078c76` |
| Dartboard Large On Dark | `b31ddc7e5e3ec49fa079405984130ddf5e139bb5` |
| Document Comment Large On Dark | `78e87cbc8054087277f60db6a9cd7083af4aa43c` |
| Document Folder Large On Dark | `9ecb81e1c37a8812e0e780e82dcf9b3bc84c338e` |
| Document Large On Dark | `5c0aaa38cd269d77f30206c0dc3cfa1abbd67ab1` |
| Document Report Large On Dark | `e617086cb558e7ad3cb456c520652c97557edd77` |
| Flowers Large On Dark | `eeb4a24a2f1c7c62cc48f80cf21f2288d213423b` |
| Folder Large On Dark | `3c284cf622c74204daf1aaff7fe47302fd6768bb` |
| Gift Large On Dark | `a0b0b90bf2f2e01fb9ff354f43723bc89bd81f78` |
| Glasses Large On Dark | `ed7fc75e503fa9df66c816fb18a963e3b2fae1ba` |
| Globe Large On Dark | `d56b41ac16977bc0d906f8509d3eea1ede3ff203` |
| Handshake Heart Large On Dark | `d1edd9736e53c14ff96f96c6f2eaff81497131e0` |
| ID Badge Large On Dark | `e79c3455ab9e3cca7cc0599675917e9204866d4b` |
| ID Badge Verified Large On Dark | `fc7ef49110ec034edd9292948fa0a42b87376b37` |
| Image Large On Dark | `b381ef1622cdf7214a64b6e3d734eda8a56c5d7a` |
| Image Stack Large On Dark | `5d6c99aadf552399bd092dec172aad0c76247ffd` |
| Industry Large On Dark | `d73586c7c75255b833c88072295118be7d5cae1a` |
| Lightbulb Large On Dark | `21c6b0d4fba0096620c5c503751090fe6c462b5b` |
| Location Marker Large On Dark | `e8b9406d6ae406b30336bc38c7f4e63644e8e5cd` |
| Locked Large On Dark | `f6a0bbbd60661e4ccf2a49b55719a0e15ea0a763` |
| Magic Wand Large On Dark | `7d1759a784d86ac1bd68e268f7d988fe5483dc50` |
| Magnet Large On Dark | `a9ee252e7b31c2a12da89412e6d0f1d8568f32f6` |
| Mail Large On Dark | `7f2ee00fc851e312caa23c1daf11f8dceb7cd1df` |
| Mail Open Large On Dark | `e8dbad0f5d14d3c835a5889d8a6cc83fb870d0c9` |
| Mail Verified Large On Dark | `d2144a05b2f4e95b3d34cc69493bb0a10945a778` |
| Marketplace Large On Dark | `567c97c55675b291efa88648aeeb2d9c94ab914c` |
| Megaphone Large On Dark | `361bc2dfa4e2f2958d2f1fe99f6a0346b64b15fc` |
| Messages Large On Dark | `426751e5e20533addc5989d3f9836bce8f18749d` |
| Microphone Large On Dark | `a1706ce5c0fb63e36d50a628c74170440008df1d` |
| Notebook Large On Dark | `fb832110d845511f1745be73438e6e090ca829d0` |
| Notepad Large On Dark | `c894984a8d3657ced203cae00b84972aa159f369` |
| Passkey Large On Dark | `7c211a57d7a3e0c7184743c94680e9a3df98506f` |
| Patent Large On Dark | `dd191c2065ca86bdf86889e726467ac293ebc82d` |
| Pencil Ruler Large On Dark | `394e9e85868aabb3a4ccfe31bb429059bed226d5` |
| Phone Handset Large On Dark | `6906b9651a4016a3cd603dcd4f7679f141341c56` |
| Phone Large On Dark | `bd7a879b354d9424e0fdbb11ab87b463317c1f4c` |
| Rocket Large On Dark | `0143c0eb767857a5c6afb679f237a1f9ab859dca` |
| Salary Large On Dark | `c9a1eb823c7549d4e36df6de451549ad0100e223` |
| School Large On Dark | `4fd24e2b03d11b42d1110a683086ba99e81587b2` |
| Search Large On Dark | `f06c601ac3431acfcf474b68877fddb86fddad2b` |
| Self-ID Large On Dark | `43c9b18675f553714ffbd03ba832a613fee0ae83` |
| Shield Large On Dark | `9421017d93c7ad24c6ba1a1d727da1896b96dab7` |
| Signal Caution Large On Dark | `84d269df2dd752433be9e7bf9fc6d941871302d4` |
| Signal Error Large On Dark | `f6c5954a8e5a6ef30b4c428a6db7b2fcec032c81` |
| Signal Success Large On Dark | `2b53671ae903d0e5e693eeebb52bc5749912cc27` |
| Slides Stack Large On Dark | `a7efcba683cdf2cebd5ed5a59787e030ddb0345f` |
| Sparkle Large On Dark | `e87548c55d45d148c9d054ff0b9d6930e2c36b6b` |
| Spotlight Large On Dark | `871711d245fe7f032f7d9efc883301a54b7d12d8` |
| Toolbox Large On Dark | `477329e3e70d899c2eb7faf264c6934e8c019e74` |
| Trophy Large On Dark | `6a5ae88b7881a08c7001d3cbddc9fb5ffe5d61be` |
| UI Chart Large On Dark | `f7d7200735f9acb072b33208968e0094b3b682a1` |
| UI Chart Trend Large On Dark | `2c73f2835c6ba8590447f6a3f5993d97b37a44f5` |
| UI Dashboard Large On Dark | `18cb2a6d230f303e797f107744c88dfef5af0091` |
| UI Feed Profile Large On Dark | `657ca48d79fef89fbca28ddf7275af2b88919ce9` |
| UI Feed Profile Premium Large On Dark | `ec4d4e5ba1f5e94f59612a8bb298057371ab0ef3` |
| UI Website Large On Dark | `225aaa3f88e2b42b25d31d8f01071d9fb5f8ed2e` |
| Unlocked Large On Dark | `80231f86b8c0d7b6ca5428eb65e6778bd3c60801` |
| Verified Large On Dark | `c7e2080c48c8902ae0dbcbde41b047c5cbf624b8` |
| Video Course Large On Dark | `13720ece46bc106364003beeb9d00ae1f879cde2` |
| Video Large On Dark | `8057616ae09120185ddc54d3395eef8185f0a3c0` |
| Video Meeting Large On Dark | `73a330bc29698703a57cd459eac7f60d6cda3e07` |

---

### Scene — 34 components (no dark variant)

| Name | Key |
|---|---|
| Apartment Rooftop Small | `f19a6aa2f7dbaf90441f44f41b8df407bab98257` |
| City Park Small | `938a192b19c225a3180316c4f04fcde8789d58bb` |
| Coffee Shop Small | `614eabab2772ea9ec632ed874ea09e15aa99e103` |
| Construction Site Small | `64c5fb190cabb387a9fdb5da18346d84b11cf622` |
| Customer Service Small | `7050295706c39f1173f3f1b2bd9efbbbe33062c1` |
| Delivery Worker Mask Small | `0ba9eb703e748a43f47a1987539b2c036b4a4a4d` |
| Delivery Worker Small | `60cadfbe22c52edd86948fa9c7b8a24a57ed3097` |
| DJ Live Stream Small | `74d5a02cb8823ca6e488917e5913f799d367cc57` |
| Doctors Office Mask Small | `ac923382d4475c59de9181cd64ef8e205db149f7` |
| Doctors Office Small | `03f0ae9c92a1ba7ea17d946ceca3716811b43f1c` |
| Emergency Room Small | `16572c446d9130d533ddbbad19104855a82fc531` |
| Home Office Certificate Small | `c2a3b42171868250e272c9375c7b2d1df8241894` |
| Home Office Female Small | `9fde8f09852ef78fe3c11efcd94be23b79f798e2` |
| Home Office Male Small | `67ac54290ef17454bb01a11a551bdc265b9c4a1a` |
| Hospital Desk Mask Small | `c038024b5d571d2c1d358a6398f596e67c12412b` |
| Hospital Desk Small | `6ad17af4b06693ebf387513874132679ce6f512c` |
| Job Board Small | `3c9860416695c585554b1f746d550f731a186e73` |
| Job Interview Small | `dc981938db46f807fafe322e1fc692c272a86e66` |
| Kitchen Small | `29a50c3b59e537b75cd785b7fa9a8ea0c16415af` |
| Laboratory Small | `13da01029c9c7a7a08b319cf36ef802e526393b8` |
| Networking Event Small | `74d24006a4be0c89f92e329a80db3dfa599fd80d` |
| Nurses Office 2 Small | `a7812be26e83443e3fd46a501fb2c45d86159c7c` |
| Nurses Office Small | `5a57404036b7a2c73128d6f7301eb1f88c8ef155` |
| Office AI Small | `26b966e500515a7af17a1d73c70a658508b0546c` |
| Order Fulfillment Mask Small | `bea2946a646ca800022f67b6af35c8b5a0ab04ad` |
| Order Fulfillment Small | `b4e685dc4b0305365adc1de2ed3c213474904eba` |
| Packing Orders Small | `5b473e6e6028c4991e69777cfe1b9ecdfd7d6268` |
| Recruiter Call Small | `0e1e692f6adcb474a7eefd31181538d4112e4a62` |
| Secure Browser Small | `03bbb3096f4e194276f5e7c06d58e017d380a6ca` |
| Supermarket Mask Small | `fa882fbeaffc88a086de09afee6b6ae278ab59fe` |
| Supermarket Small | `d7ce01b69cad1544251815a79c1443c77b777c02` |
| Working In Bed Small | `504b3ae84fbf602bfa4978077e179fd0a3d37617` |
| Working With Pets Small | `0d21c6ba037eee43ef97a7a712b195ff1550462e` |
| Yoga Teacher Small | `b4a0d7447e64f89cf849743e2fe65c0b74358f88` |

---

### Spot Large — 49 components

| Name | Key |
|---|---|
| Empty Leaving Large | `66c347c923792c76b026943281ed892b52854b95` |
| Empty No Mail Large | `9047d2e7a22a33bb9fd2ee254197f689692248ae` |
| Empty Room Large | `4e20e8c8cd8d36e9c2109cfc1e129bc72e01a899` |
| Empty Waiting Large | `48d2dba05d150fc40a8d5a7abcf095cdc8439e6f` |
| Error Connection Large | `8d62bf4fa611786189032282956f09bcc1ab8160` |
| Error Construction Large | `babf60d4ff3a3da5b59684f447225debb5017839` |
| Error Crossing Large | `ab255ac49c3c96c0b1782a1f7c314674cc559d57` |
| Error Fail Large | `7c89d98c15249c5f11b0cd9a9e731602ca51d1d8` |
| Error Pit Crew Large | `9911ee81619eec951dca635010a77e63919672fe` |
| Error Server Large | `d2b7652443c567fa3e09ced882af69e9bc57d1f3` |
| Main Bike Shop Large | `eb508c7e04f676a2221b9748ecc7938f9e29e4a4` |
| Main Broadcast Large | `3d5be809c6acd3acec48d421f1b3ce6583eb66db` |
| Main Call Center Large | `0a673f71833f92467b4b2a3f4c99fa4ae9a266b7` |
| Main Collaboration 2 Large | `ed99328ab7448636758a1efc1289bff864453a10` |
| Main Collaboration Large | `714100d7aacc7916e5c1da8bbd14f337d73e4023` |
| Main Commute Large | `3f9657972a01e4718a59f639352514a6899508c9` |
| Main Conversation Large | `a2366453ad987a6203ee58f0e7f609bfa7e72e11` |
| Main Coworkers 2 Large | `571295bb1a1570babf704a66113af3252fa95089` |
| Main Coworkers 3 Large | `a40c5566a4c1e491a647f203bc137aa910e6ddad` |
| Main Coworkers 4 Large | `5a34febf6e31ddfdad37a9b797dc4f6a2ecb9428` |
| Main Coworkers 5 Large | `4685adea2c3616703d59a2ff503670904d2c2000` |
| Main Coworkers Large | `bf80d11c6e6d460dbd66b8363e831f9ae33ad1dd` |
| Main Diplomas Large | `4a05a75b98cfeb042c485720fa4f833faa8e9548` |
| Main Illustrator Large | `8f194f7602a92a5ea7494915ae7ee564a9c3299e` |
| Main Manufacturing Large | `f482bd7b72fefb41aa7923fcb5a4e738985fa315` |
| Main Manufacturing Mask Large | `738944a0e58473a78ebf4ceb3258fe44965e5741` |
| Main Mobile Video Recording Large | `bebf62d3ab9f3f11154c6557adda89758e58509d` |
| Main Musician Large | `12aecec3522ed11cf7c52a0fe87cb587528a92ee` |
| Main Office AI Large | `be12e8a5fe2ac346a6924f5095c3b4997d49741c` |
| Main Paramedic Large | `d13920d54672281d48338e6bdf61e6317a7f5846` |
| Main Paramedic Mask Large | `e6d33f9c815dc5ed59f568b33ebd26210e854789` |
| Main Person 2 Large | `e62e279da3f2fbca40a7a50c44b136e62411c4fd` |
| Main Person 3 Large | `c5e732f8e583733d359a1b177554f98dd4feb613` |
| Main Person Large | `81e7620808457576b0ae25f847908e0de02c97e2` |
| Main Podcaster Large | `144b4f56b0a16c768f5bc9ebc53cc273ea4ba673` |
| Main Presentation Large | `4121df9a84a27dd260b7294455e497ad52cbd6d3` |
| Main Relax Large | `703921704d3fe6d5adc48ede2983f9a424675497` |
| Main Retail Checkout Large | `2427bff44f0d3989f75dc81ea255307bedf35691` |
| Main School Teacher Large | `f9786a246fc3edecf8b9539b872874b6e3603a29` |
| Main Secure Large | `e7cd7c06b1360edc249179fd484189f2226ed5ed` |
| Main Self-ID Large | `48378ae57511c43b0ebba30a0e5c2529ef800239` |
| Main Tailor Large | `ce2a91ca07e7dc2208e79a90afc49a533d7320d0` |
| Main Teacher Large | `58eb95f8b616a5def84c08c3ed2a9e65da545352` |
| Main WFH Large | `e2017e938e12a0956365f3bc0ad51b33e175228b` |
| Main WFH Video Large | `f9c910d1fbb3c692ad57bfbf0fb206912a78eff0` |
| Success Gift Large | `7b6dca850bd9218119ba68634e89dda0b8236c62` |
| Success Individual 2 Large | `f7f251dbc0d9d9d506081ff3163311a670122a39` |
| Success Individual Large | `4eb165f113b24ea291e00cf879cbacd5ab891fec` |
| Success Team Large | `b9d704ae6ad343a1da4cdd9629708ebe2644273c` |

---

### Spot Large On Dark — 49 components

| Name | Key |
|---|---|
| Empty Leaving Large On Dark | `9cea1dd7c6ca43635682b6456ac7c39916f8b5fb` |
| Empty No Mail Large On Dark | `56dba7fe185da0a2a2a2293caf9eb4bfa7846fb1` |
| Empty Room Large On Dark | `97795ce2d9d77df126dd5337423c2c35b4a424a6` |
| Empty Waiting Large On Dark | `1397183bf3f1aa939775867dc464c6269beb1012` |
| Error Connection Large On Dark | `8bb61dfc812ee1d9c7d6be633d8cf25fe4fd8428` |
| Error Construction Large On Dark | `c962feeaeca88ecbb37c5ab2483c1f2b836a64b9` |
| Error Crossing Large On Dark | `51f712ec72cbed54d6ce8a7520d24a27d611d2ef` |
| Error Fail Large On Dark | `806da321888825ac669a15f8188941e5cdd4584a` |
| Error Pit Crew Large On Dark | `605f806c1d59051e6d4bc783d85105995c1642a9` |
| Error Server Large On Dark | `f48326702767861c02f1857fc261d9ea41bdc05e` |
| Main Bike Shop Large On Dark | `4031aa61b02b16b1dd2adf2628876300a17819e4` |
| Main Broadcast Large On Dark | `f6f55e42dff303c8307a118a96ed4632efe7b37a` |
| Main Call Center Large On Dark | `ed10fd8e13603d6715ab81fdac474f21bbe37e89` |
| Main Collaboration 2 Large On Dark | `ddd7b7c6e3486bbe44ee82d2db7a69f0514f0174` |
| Main Collaboration Large On Dark | `e9d1755c623acdd49053b6014184644d8d99efa6` |
| Main Commute Large On Dark | `84e8b00401726fb8a59a2e339e69482a6316f17b` |
| Main Conversation Large On Dark | `06670744bc16010e75d64481df49c964cc2e9e84` |
| Main Coworkers 2 Large On Dark | `52f20b13a57ee9b217fe91f50c984ee9169cd517` |
| Main Coworkers 3 Large On Dark | `e89b533a632e8c3eb3a49b17ae1165694fdcf8b9` |
| Main Coworkers 4 Large On Dark | `104e954a3203de1ea00857c4df31625779a67409` |
| Main Coworkers 5 Large On Dark | `1e19448e7c5e59579fbb4048c8f347e03024b2c5` |
| Main Coworkers Large On Dark | `6b28acf0153f766bb7d6fda3e5aa5ca09e559a15` |
| Main Diplomas Large On Dark | `7221e54b29eb51c97b5d34dc17cf367b5a5b412f` |
| Main Illustrator Large On Dark | `f0e1dd71bfd5fec51d54ea35eba66392ce7ca2b1` |
| Main Manufacturing Large On Dark | `7090e5e863ce61543244be920e9826c195120161` |
| Main Manufacturing Mask Large On Dark | `a13927206d10d6968aa43a3c02b32bf791d7aa02` |
| Main Mobile Video Recording Large On Dark | `c3e53cf13c3cc45ae67efec7ba9df2033b49afeb` |
| Main Musician Large On Dark | `3830506fb4ae89b43fd0197f4383b14e3f73b5f2` |
| Main Office AI Large On Dark | `1d804db3c169a1f47a0e3d814d9eba7ac3e343db` |
| Main Paramedic Large On Dark | `9275cf1606489487ca1f0edb92054457dc9c6d9c` |
| Main Paramedic Mask Large On Dark | `d47375aff6d4e9c4013b826488213b0bdf46b4ec` |
| Main Person 2 Large On Dark | `6cad5d07ed21f0ffc8445e02c5b45b6dd6e36e84` |
| Main Person 3 Large On Dark | `7a360a52a072eadc838e330e1282293ef3898585` |
| Main Person Large On Dark | `47fa8399f49818201f49a7b44a5aeeda5e4c09ad` |
| Main Podcaster Large On Dark | `f2c5d76b0490f2f44256b9ddc4db4f2464173ee7` |
| Main Presentation Large On Dark | `41c3eda75684f2645a81f080568e2a3b9e100a53` |
| Main Relax Large On Dark | `6536de140ee747d80eb490f678db3f85f9e9d393` |
| Main Retail Checkout Large On Dark | `78d7d464b986131e54acd2dea501648ef78998d4` |
| Main School Teacher Large On Dark | `0e5411f49f192c3f064d3369a99740635df8762d` |
| Main Secure Large On Dark | `b85db91daeea837a6bc28379e7529facb4ca038a` |
| Main Self-ID Large On Dark | `fc1ff45deffe13910c96d4169326c73837f51373` |
| Main Tailor Large On Dark | `fd52de7dd30e0ebd7d032045c734e23b9f080c31` |
| Main Teacher Large On Dark | `214fb6b4eed6404d703e4e4fc272900633375033` |
| Main WFH Large On Dark | `af19dbf6461ce401df58ef1290b95acc368f596a` |
| Main WFH Video Large On Dark | `07848a035fcd6aa1a1a3ccfc51f8c5d61bde3d0b` |
| Success Gift Large On Dark | `7112577ee192205888f84ada7a8491f01b08c046` |
| Success Individual 2 Large On Dark | `bbe81d424d0f2d95b1c3d717d5a6425b87912471` |
| Success Individual Large On Dark | `c11c7ffa63fc0645e1670378e8b88727f3a627ee` |
| Success Team Large On Dark | `f0d2c0d1099895cab7845758b29610f03c5b8dba` |

---

### Spot Small — 49 components

| Name | Key |
|---|---|
| Empty Leaving Small | `b78d175184344e90605cbc100b0991d3bbec672b` |
| Empty No Mail Small | `75e162a8e408bd315998ac6a6db50d69f0d32ef8` |
| Empty Room Small | `42f7116ec232b6ae7f51cf92b7e75742a5d86208` |
| Empty Waiting Small | `6485c4f5d87f6ad2b7d4ba57bc10228e013c4062` |
| Error Connection Small | `8e2fa70fdfed6a0ab5b6b964ee8f0ca946fd57ed` |
| Error Construction Small | `f4c33d147e39f2f3514faa6ff362e2428d35326c` |
| Error Crossing Small | `be649f9b7c5f9728f03b2728f15958603b095104` |
| Error Fail Small | `751b13e8644f1a53e1cfd98556da0fbc6649dc13` |
| Error Pit Crew Small | `67f745fc12b3076d07875d72047205fc66238a97` |
| Error Server Small | `da5cb20f7eb061979e38ef0667c13a26f5ebbbe3` |
| Main Bike Shop Small | `7d4b361b0b6837d0c20ecb2ac59cbedc8bd0536f` |
| Main Broadcast Small | `a2a9f98363f46ef5a18f4dbf36fd67e3595b0c37` |
| Main Call Center Small | `21b1f5211c16a1027cb2d54fa62f59857362c577` |
| Main Collaboration 2 Small | `dcaf976b2e6744c6af1ddb2a660c7017d5147470` |
| Main Collaboration Small | `a6dfc4cd928307cd711eb87851271c17710e178e` |
| Main Commute Small | `a71142897359e9e8a8173c2bb79a6a7b2740f026` |
| Main Conversation Small | `be13ac05edf19d063efad1e238e20e0f86a9635d` |
| Main Coworkers 2 Small | `c18e677b299e946d54a879a013e17610a466e73d` |
| Main Coworkers 3 Small | `0d99cfe1eb2c46863a11f9e86cd82e8a3a7d6251` |
| Main Coworkers 4 Small | `0059df6fe02ec32eb12f2aa39e19abed643615b4` |
| Main Coworkers 5 Small | `99404304f7fd7c1c30a33473758177f798360954` |
| Main Coworkers Small | `efa797b1d62d1d20ddf444cf295b76979cdac896` |
| Main Diplomas Small | `3ce76b8482a48160ec5a743cfcc88fc7e13edf50` |
| Main Illustrator Small | `839a3790a64dc6f67a6ddbb320671a0348120660` |
| Main Manufacturing Mask Small | `1fbbf267163ef020edae0c5f5639e4583dd50d68` |
| Main Manufacturing Small | `cd0af918c848b77afb14ac7409d28e215c1e81a9` |
| Main Mobile Video Recording Small | `cfc9c028653ebf5be665fd6b390b729825916ecd` |
| Main Musician Small | `966359ba09bcee0071ef5c25471db0752a85fb39` |
| Main Office AI Small | `73bd0c8ffda5673169b249a14c78ae5d67c30549` |
| Main Paramedic Mask Small | `c85afcc32c17028c1f39f2dbb2339bca555ffc93` |
| Main Paramedic Small | `f6350ccb056cf1df7756a5457be500f2b2ec8603` |
| Main Person 2 Small | `ce22a1fccf3c64734592c72fe47fc9f0dbbc204f` |
| Main Person 3 Small | `e8eb3459fc5c93c6f3ad74b17738423e3129b962` |
| Main Person Small | `6146e19fe74a9b7e83a21cc2675e3c751c2843d6` |
| Main Podcaster Small | `c8c45bfcb06364afc858a5cdaba5f34dbef96c23` |
| Main Presentation Small | `d007ec07d5dabc47296af37b2db5aa85901025a8` |
| Main Relax Small | `65643220602e258c0300839e5b61914caa5884c3` |
| Main Retail Checkout Small | `3248eb6a9ce98465a5a5885f04f37dfb295bfb50` |
| Main School Teacher Small | `da7a5d6148fed355dfde1f0778b9cbdf3ecb9183` |
| Main Secure Small | `8a6c9d786e80a30d386e4c53b16b037a4fe8a3d4` |
| Main Self-ID Small | `2046dacc077c3f17323fca9c96243a266a0d5338` |
| Main Tailor Small | `454e4baf5781d19c1fc4527f63de02b6894b2ef6` |
| Main Teacher Small | `fb308976e1fbabc56967b8280426320e67cd4082` |
| Main WFH Small | `5f00a97cfa0e004715b5daa69af639e861b0e43c` |
| Main WFH Video Small | `9186096d225fa529fbe669f0176fba5c7717c7cb` |
| Success Gift Small | `a4859fd6aab82e430c9b7f0345cf88322db2df79` |
| Success Individual 2 Small | `84375d54f936abac0e7fbf64e62ff9dad6179e10` |
| Success Individual Small | `faf894a1daea521a4eeba29a788d6ea90b7febfd` |
| Success Team Small | `85488a006cada37b1daa53579a3477750e511d09` |

---

### Spot Small On Dark — 49 components

| Name | Key |
|---|---|
| Empty Leaving Small On Dark | `0e67a32bcfa50b8d831237bb809be8e18f822b12` |
| Empty No Mail Small On Dark | `483cfe1ae6061d2b7f59faa3ee6a51e0ba84cc4c` |
| Empty Room Small On Dark | `e7b89a845f303d80ff10aae56f8325d00669cf03` |
| Empty Waiting Small On Dark | `bab3dd6f72fb5beb44940b6683f48e5f099c4f87` |
| Error Connection Small On Dark | `094f790b89d17e10cf207c1b02e8b0b6d5910f40` |
| Error Construction Small On Dark | `313a47754e3d6e650fa0c36270e016072790454f` |
| Error Crossing Small On Dark | `c6ad6460da07c5ed473733492c2d76cf30e04896` |
| Error Fail Small On Dark | `cac03fb63b1694e662603d827baab6d5aaf20e2d` |
| Error Pit Crew Small On Dark | `bc0453ebf88b1a54062a4d6dc7f7b0398c4af156` |
| Error Server Small On Dark | `306bc024d2731a5671f352c9a40e241727543634` |
| Main Bike Shop Small On Dark | `e2bcc4b67a7553c38b320cb8dd8f37651c7c7b7e` |
| Main Broadcast Small On Dark | `ffe8fef7bdae045e323a2f27e3538f629fc81d4d` |
| Main Call Center Small On Dark | `cf38625bbc3e8fc40add5c7e8c4cc5306b991171` |
| Main Collaboration 2 Small On Dark | `1b8cce658b0d514ef0487caa6100da6014a53558` |
| Main Collaboration Small On Dark | `b8de94687827d7a9f8a378017915755ea2e210d7` |
| Main Commute Small On Dark | `02435e1db7d98e47952de1b6c9520f71d7a87098` |
| Main Conversation Small On Dark | `708b45f3337e11fa377a02b2808621a03dbbba1e` |
| Main Coworkers 2 Small On Dark | `38e76c01a04062f075e77def33d48bde9a8e3848` |
| Main Coworkers 3 Small On Dark | `d867902a4aefed816b52b558b1be826c5671b672` |
| Main Coworkers 4 Small On Dark | `a33b1471c5bce91812d6b2c6c5600857370c8c11` |
| Main Coworkers 5 Small On Dark | `122488a2735dadfdc93c3fd5fa3b2e12466e8c61` |
| Main Coworkers Small On Dark | `9056e45c8eb3d368e2eb9577deccf208e61bb1e3` |
| Main Diplomas Small On Dark | `3855186573adc1f24daebd374d642a1f32a6f12c` |
| Main Illustrator Small On Dark | `3a1ab456b656a05b76d676c12a1c2306982df125` |
| Main Manufacturing Mask Small On Dark | `f425f1fd398f20900f875e05eb43956641955f63` |
| Main Manufacturing Small On Dark | `fd57974573072aefeadaeb3f2bc76a086ad9171f` |
| Main Mobile Video Recording Small On Dark | `7f8398acb3e59b968e54de462f9e8cef5dbe6426` |
| Main Musician Small On Dark | `b51aa9272a79af11f145e66cbee4e514ad463ea0` |
| Main Office AI Small On Dark | `2ecfca3494a46181093bb4845cbcdd5bcbba57a3` |
| Main Paramedic Mask Small On Dark | `d9b2b4937a1b8546c7ef23afb33b1fc3d513819c` |
| Main Paramedic Small On Dark | `2b9883335be2b17d7102f57d7b6f9dce199a7aa1` |
| Main Person 2 Small On Dark | `f4c6bdecc59859d493294426c42e34318986ac22` |
| Main Person 3 Small On Dark | `f56653bf7b79fca560e60ea0912887428d8ab32d` |
| Main Person Small On Dark | `4eba2e85aa3ce9a76c38b1282c532b3c36bf8762` |
| Main Podcaster Small On Dark | `34ea4ad1022de19fb98eef355946a81fc421934d` |
| Main Presentation Small On Dark | `25c8dc4a361766145ed8f3c05b0493c1682bf6d4` |
| Main Relax Small On Dark | `ed7db71919b5769eabd34ed344b12e8a2085e028` |
| Main Retail Checkout Small On Dark | `abf5f9d2fd7fef08d1af5bb2abf0569a5921df75` |
| Main School Teacher Small On Dark | `288ec7a6fecd7f130bd66e246034abfdfd46f58a` |
| Main Secure Small On Dark | `17d0def9ab7855057663a84b25fbfe2b32b85453` |
| Main Self-ID Small On Dark | `82d266a0684d6f5cb3f778dfbd8280c0a7fb3f28` |
| Main Tailor Small On Dark | `df11dbc680bb6e0a3f20fcfa918fdbf52ea83cf0` |
| Main Teacher Small On Dark | `39cbbe38237e7c3c7d8531997dc5ca20338314be` |
| Main WFH Small On Dark | `d087c06a912f21d71831092e77bafb4dba09c746` |
| Main WFH Video Small On Dark | `dca49f6871c7f509cce951635d2740a9af14e2c2` |
| Success Gift Small On Dark | `b6eb9ce5e9bc7159f17bb2d7d6aa8e251092f507` |
| Success Individual 2 Small On Dark | `9fd50e3aa435c0675e36bd3d6217b7a284f2d56c` |
| Success Individual Small On Dark | `96ad28e96412e87c6cd49a2895ebc651032a4742` |
| Success Team Small On Dark | `57f33adaffa56c60039b74f286c3c156b99abb70` |
