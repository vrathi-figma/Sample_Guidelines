---
name: icons
description: Icon sourcing rules and full key reference for DS Icons Library — small (189), medium (303), and large (26) system icons
---

# Icons

## Source & Usage

All icons must come from the **DS Icons Library** (`s1GLDCHfC8f6ZV1aYcWmZm`). This applies in two scenarios:

1. **Icon placeholders inside components** — when a component has a generic icon slot, always swap in the correct icon. Do not leave default placeholder icons in place.
2. **Standalone icon usage** — any time the design calls for an icon (close, chevron, search, add, etc.), import it from the DS Icons Library.

**Never use a text character (✕, ×, +, >, — or any glyph) as a substitute for an icon.** There is no fallback that involves text characters.

## Sizes

Icons come from the **Icons System** page in three sizes: Small, Medium, and Large. **Default to Medium** unless the component's icon slot or surrounding context requires otherwise. Not all icons exist in all three sizes — if Medium isn't available, use the closest available size.

## When to Use Icons

**Use icons when:**
- They help clarify actions or content, making it easier to understand or navigate
- Space is limited and an icon conveys information more efficiently than text
- Used in interactive elements like buttons or navigation menus to guide interactions intuitively
- They reinforce a consistent look and feel without conflicting with the brand aesthetic

**Don't use icons when:**
- The icon could be ambiguous or misinterpreted — familiarity matters, don't reinvent system icons
- There are already too many icons in the UI — excess dilutes their impact
- They would replace essential instructional or informative text entirely

**Selecting the right icon:** Stick with system icons users are already familiar with. Changing them so they're unrecognizable introduces unnecessary friction.

---

## Icon Types

Icons operate in two modes:

- **Functional icons** carry out actions and should be placed within interactive components like buttons. Example: an overflow menu button, a save button.
- **Supportive icons** emphasize, clarify, or decorate other elements. They don't live in a button and don't trigger an action — they exist to support their label. Example: a lightbulb icon next to an insight label, a skills icon next to a profile detail.

---

## Outline vs. Fill

The majority of DS icons present in an **outlined style**. Stick to a consistent style within a design — mixing outline and filled icons can confuse users about behaviors and interactions.

**Toggles:** When an icon is used in a toggle button, use outline for the default/inactive state and filled for the selected/active/complete state. Example: Bookmark Outline = unsaved, Bookmark Fill = saved.

**Non-toggle icons:** If an icon is not used in a toggle, default to the **filled variant**.

**Some icons use both fill and stroke** in their visual form (e.g. Services, Printer, Envelope Open, LinkedIn Page) — this is intentional, not a mixing violation.

---

## Color

Icons use solid, monochromatic colors and must meet a 4.5:1 contrast ratio.

- **Match icon color to text color** when pairing an icon with a label. Do not use a different color for the icon than the adjacent text.
- **Accent colors:** Icon accent colors (e.g. `color-icon-accent-2` = warm orange) add visual interest to content areas. Use them to highlight key content and complement media. Do not use accent colors for signal states — for signaling, use Tags or components that use system colors.
- **Don't use system feedback tokens** (positive, negative, caution) as accent colors on an icon unless it's inside a system feedback component.

---

## How to Import

Use `importComponentByKeyAsync(key)` with the pre-documented key below. **Do not use `search_design_system` for icons** — all medium icons are listed here. If an icon truly isn't in this list, use `search_design_system` scoped to the DS Icons Library (`s1GLDCHfC8f6ZV1aYcWmZm`) as a last resort.

```js
const icon = await figma.importComponentByKeyAsync('KEY');
const instance = icon.createInstance();
```

---

## Medium System Icons — Full Key Reference

| Icon | Key |
|---|---|
| Ad | `62a55a0a3a5cb2338bd3550d4b04542ff15b72b9` |
| Ad Account | `37dd9841eb087f5d0f7291eed0cfec81c4a44d99` |
| Add | `4dbd6ff1e1714d9eef7802b51ef70a446d52e49d` |
| Advertise | `228c6a201efc417aade1f1ced9d68ebf497899ea` |
| Airplay | `883d44a78cdd3183f9d3d89d6ba24981d6fbe5b4` |
| Alt Text | `9b7304e1d1486173609cadca741952db975f58e5` |
| Analytics | `6524118173053309d19275f8a310797d037e3f9e` |
| Archive | `58278be983cafa39b6d8ca76b5c579fb844a8f4b` |
| Arrow Down | `5be2177de044b27b1248210063019d9d8fb80c21` |
| Arrow Left | `6b4831c9afd650141c94430d0f27f0ffa15ca093` |
| Arrow Right | `42c9e6faea74f202873ca18181ff12d912ac188f` |
| Arrow Up | `fe05a5a613752e1def9f5c9cbc48e7ff20dd61f5` |
| Arrow Up Down | `262ab2717aad4fbe534c48d3df2f3757bd1a7280` |
| Arrow Up Left | `b53c62c5eb4a63d44225e4d92fe4c3f1c3c30b09` |
| Assets | `9242d53cadf7dd6fd17a29ae7e7a925b8003db72` |
| Attachment | `d33e5fb2d70a0d2e83eb22e76692686a9529a36b` |
| Ball | `598d5770880b214d64077b94e76535f0eb0cdc7a` |
| Bank | `cc169ba31d3532dda8c8f5f7eaea91b2c0724f1c` |
| Bear | `8ad932d7dbef2b10c529e84a2e271cbab2e4b6bc` |
| Bell Fill | `67862bb554f22db1f0c4b769d60eee24e80a542d` |
| Bell Fill Double | `bfa6445f7010eee0e2ea49c7a624fb26860f58c0` |
| Bell Off | `38c715b00f80529e5b0f71e4f152d93b79b87b44` |
| Bell Outline | `bfe4550944add53c2fbc4577532d79fe3806b632` |
| Bell Ring | `af0b6f5ce59ddd3ba431792ac023fd8b3c5baea6` |
| Block | `d0507beca16290c0f091756977e1e7c10fb3dac1` |
| Book Open | `6732565814c9472be1fc2df9c4c792c0b7fbc2b9` |
| Bookmark Fill | `db9ed39d046766fac040a860c3f181300d4b0eed` |
| Bookmark Outline | `4d3f4011c5c8cb76851f42f3c59ad1328d6c8087` |
| Brightness Fill | `a7f76616c43f4290869403d9897767f3b6f1e6cf` |
| Brightness Outline | `4b30248525aba6df4da416544622848f962cd3a0` |
| Bus | `7107bf8e8d2f0fe2a0db8da9453b6701636b9aa3` |
| Calendar | `9cc7fef033d0c8cade47380d3b265fe68a67a2d4` |
| Camera | `ff66e0ea51835e4faef9e316fce24b841a51493b` |
| Camera Flip | `1295920d549c774a9fd29c60fabe67ffbddf8a3f` |
| Campaigns | `847addd467c89552f80e5a8c12209da08a7ddf8d` |
| Car | `7789919b2b3dead8e2ab5a9ffb8f7f92e0a8af73` |
| Caret | `3d6cc8c413b9e729ada2c26faeb9c6028d5be609` |
| Caret Right | `3af3e2838a93d96415da1462bb3d3ef781ff7632` |
| Caret Up | `9c9f70e249d0e9d90b79e66da9a3e7e053400f53` |
| Certificate | `a8b7a224a4e9976917c7cf93dfba9c674037c3b4` |
| Check | `7222b10ef4f55fbab8faa4bba13d3b0a3ba861f6` |
| Checklist | `74dd47432cf96acf200d4b8d97bf5ffb0dcab304` |
| Chevron Down | `2b050c40a51842ddd1d360a24e3401428286d286` |
| Chevron Left | `3bdc321384b1dfc2255cdcc58db827646b064fc5` |
| Chevron Right | `323fff37264f1da68b1eb40ce9ced807e62553f7` |
| Chevron Up | `ced7e6859bc9950efbc2e835f1beeeb611ba02d5` |
| Chromecast | `308077e7a7658fd31419c067755375221e8d1e64` |
| Circle | `d06d6cd6e6afe902c3977ad9e816cd048981c36b` |
| Clear | `e7b6c506501563297e5145a84ab60958286a99b3` |
| Clipboard | `aedac2f7438f282454485a46b9a6c7c75260da74` |
| Clipboard Check | `0956a271eb389f6a04c30b1741707674ed5e2ce9` |
| Clock | `20c854ff200502d8b09f9cdcf5f2e1a128871e4a` |
| Close | `7881b8806a8156b57254796398cbe7cf9580d1c4` |
| Closed Captions Fill | `1c46e0446b9b3850ce9922a05bc38493a1808e2b` |
| Closed Captions Outline | `ffe3cda728fcbe8264b4989d929731c18b19927b` |
| Comment | `7d6145cb33a94480ff3c269852aad9b7f1964454` |
| Comment Off | `5105dfa94c503956bce4f61bbae0835c72b0f469` |
| Company | `9b92d9fe4cc931d7e997eb6cc15025f25094bb04` |
| Company Fill | `f64182b23c4508d6cf61a94af1088b030464cdb0` |
| Compose | `61a68187f4829e28a8a270bb1b34f37e7f69b7c8` |
| Connect | `ae31b44ee6557e6ad12d4ebbb4362ac002479ac0` |
| Content Add | `cd13ff82a099d33edbd175d6385357f99a03069a` |
| Content Align Center | `5bd5fdf9fb6ecf3a8a6d2e9c124167c0bd57f243` |
| Content Align Left | `24ff6877d992c3fbadd90d7148b020ce587888f1` |
| Content Align Right | `0e5186c0aaea2355022cd75e7b83dfd22aef3790` |
| Content Full Bleed | `78b30c15c95e008b45002eae9e9c1badee1f766d` |
| Content Full Width | `d4094ce3399eb2a4751df030022644ee2d165844` |
| Contrast Fill | `97b7a54993d7a96be498df474d6be728e36fc1a8` |
| Contrast Outline | `7f33ada47b98a9c54eb4e5e480dab682faf891c3` |
| Credit Card | `72d4f0f9bbbb57f4a184c335493305c65da9d192` |
| Crop | `8b8d124312a88d7d74a544e5a9f6c34b80e19b1c` |
| Curly Braces | `11761eefde295c0088f2ce3b38f85c7076dcc25a` |
| Cut | `c568e490422c610b8f6cef5c29e333789cdd3604` |
| Dashboard | `d3d105722ef15785e1e3c8c63099ee86b0bfd074` |
| Discover | `15691de20d35c34d27363cca8bf388cb4680da8e` |
| Document | `f7023c2b4a20cb0cf6dbf3eb48596305c0b23393` |
| Document Copy | `6c8558092e7b33f21c36b7a59aa4fc9c1c176725` |
| Download | `d093ba8fab473c4bd8de0023787e082016c9dbeb` |
| Edit | `1ab167066590879fa22f648aa43cfdff48015621` |
| Embed | `a7507bbd9df12a0f889d29fbe983f5701825b72b` |
| Emoji | `a3e87e8954ceac4db9e1ffbf97db93c1ebefc738` |
| Envelope | `ae9b5c5182a97d7e5dcafbba1258ad16394575fb` |
| Envelope Open | `d78fc567ba4eba6777c397e5725da429701fd8c5` |
| Filter | `7080e01ded7920819778190573843d9dcd98862d` |
| Fire | `91b73a7766d59533a21bb27ff5be7413fd22fefc` |
| Flags | `a48c2f4d2cdb84350ef2065975ca8d1b890c2c73` |
| Flash Auto | `404557065a53beadc0e054df66ab51e13a3dde7c` |
| Flash Off | `2c3e18d762ff302eec622093c9d3ec818b667986` |
| Flash On | `731c1b41fd9d6db986819dd6170eba9cd3b55642` |
| Flip Horizontal | `9ad370b2e46395d4ab8158c0b4f6f22412d08779` |
| Flip Vertical | `3dddc5bc2c77f9b2fcdb2ae41a56163cef694544` |
| Folder | `b298a90651fa195e80c2614be562d4cf36cf8bf7` |
| Food | `a3fa794233f108335e17c3a6bdca23ccae51dfe4` |
| Format Font | `352a9a4e23d04c994fa1d47619e20420000baecc` |
| Forward 10 | `6bbc954ab68bdedba95ce6c5874f40f8790c6cca` |
| Fullscreen Enter | `20c63d1be6bb37a6d8433fce9e7501fe40d57130` |
| Fullscreen Exit | `1ded6112ff7edc534646d645ca9d77ef11371932` |
| GIF | `9e25c06ab62a50aa483dd3229a396040c4637b7e` |
| Gallery View | `b351fce73f4e9a75e79ecf4d29139596e5cedec1` |
| Gift | `271b38062c3a4432a14d39be6fa7866e2da8be4b` |
| Globe Americas | `3db812158f9b458e737890af1cf3e507cff01910` |
| Globe Language | `ecef5e5a4bba0f028073685ecf0bd3e07716631c` |
| Grid | `dc5ab3b0048609b37f7c5fe5378311a7983424d3` |
| Group | `af3dc71ba4f93a71fd93c32f409f6a8dd2310b48` |
| HD Fill | `fc0b5874c61b99487fba7d0e934c4f6f7e769312` |
| HD Outline | `2312bcd4c29b86323fc5554a1bd3113caccf69e8` |
| Hand Point | `9b6da5f4307c943c23071d712fa9e26801e15f1a` |
| Hand Raised Fill | `e7c143cddd70cb0c691ecaa75d83290fb6ca71c3` |
| Hand Raised Outline | `cc9b34a9c9c4b3bfe66b04be50e4024182b28c30` |
| Hashtag | `3f2f06b77ff09f3fc0fb8d8ef0e3c5685333190b` |
| Home | `1506c09a054f6cef7ccb71686bb6883af9c3106a` |
| ID Badge | `8474ba284426c82f087523aa3344725435465cea` |
| Image | `d1e6476f37178e25525b10faf9d0d8e8ec22866e` |
| Image Broken | `70fb422b45454575b3a5ab6f301bdf849e82b84b` |
| Image Square | `b8667ba53cea5089eb4f88e61968ba04875fa65d` |
| Image Stack | `dd2d0f3f5e96071d3dffb337ea3555b6d0b0f3f0` |
| Import Export | `2f5a123565cbe0325bfe351c826157226dadc428` |
| In Common | `1a31dfc0601a4c6ddc04811ed37a49601cc96bda` |
| Invoice | `7167f8ab98bcc343f1abf578a116ad5c64bf623d` |
| Invoice Fill | `88385cbf4cf04f3533b348dff34efa0cced3738d` |
| Job | `93df839ce119bcf639f8b2679e75f18c07e11045` |
| Join | `e2160183a290c7a5307d802a458aaccc35fb05ff` |
| Key | `89afca68984d73bc55a9d0c0fb9678022214bacb` |
| Keyboard Down | `b118456e018639845438984d8ebc118d6da24ced` |
| Keyboard Up | `40ae6ab3c47f2cc94f55f9020ce67d9d359bf994` |
| Laptop | `78648e625cd361791be9254624f80f6774757d70` |
| Leave | `53d92d50809c7bf4451fddb2a220749aec960a49` |
| Lightbulb | `4a0c971ce594c5e9dfe050d32e8ae4fdf200a263` |
| Lightbulb Fill | `d337b6690c1b216c5c692a8b3e2d19c0a249a544` |
| Link | `27a981703ada77db17bb218d15c9932711e269db` |
| Link External | `38bc0f17ca3b5913f9e658d44d9a1f64e0854f09` |
| LinkedIn Bug | `2ef1eabf96cfbf838f490bd44d92dd780e6f5e19` |
| LinkedIn Influencer | `25f8f99d9d1ea9bb923efc56e6fef024e846e3e1` |
| LinkedIn Page | `ef50922a30f0d5834d3b64573935f1e46b71dcb6` |
| Location Marker | `7d83c31d7ae20e9d4b14ea66e610af0bb819810b` |
| Locked | `9cc75e19e766ecb7c4bc63921eead7761f76e8e5` |
| Logo Recruiter | `b781e237add5c39c019a1ce853f69be4e104ce77` |
| Logo Sales Navigator | `8f6ebbe73f54c79d0af73acab248671fcd472b0b` |
| Magic Wand | `2e836aa31f554c817ab99b600db1d935be6d5ed3` |
| Map | `3b7bb345909b15531d6e2ef60b715ebd59b3c20f` |
| Marketplace | `c59d9e64efeb8c13347b034b389485b49cdaef81` |
| Maximize | `f5f2339f32be1f22d732d2685480099554f0bfb6` |
| Mention | `6b9cc37ecd15f486e01128b785b22b6bb59d44d9` |
| Mention Off | `9f3feec664eb878fd8cd35cdc08f00ce1f30c36e` |
| Menu | `31564a5f21426fe642b97b77d7bf3a7ee35cb7b4` |
| Messages | `5bbb8019078e07ac9cb2fb0bc1052fcc3c47466e` |
| Microphone Fill | `837364d3e5702266a7c16cbb9ad9d25414e9bddb` |
| Microphone Off | `cd041f3199d7d98e50115c6c0f1aa6ba5460b235` |
| Microphone Outline | `050064e7c494990cf3f4186280bf837515451e1f` |
| Minimize | `954b16cfcc3d37fd6e793c741690068f9a5be338` |
| Monitor | `272d64cf6d2160c975e1980511fa80bcb913ea5d` |
| Newspaper | `2cd0e3e510473f0a8af65f4298f76100e4633c51` |
| Newspaper Fill | `6756ada623677726619961e58a313bc44deb0a49` |
| Notebook | `55fe7366db079d609a1b5e6200bc983dccb6c664` |
| Org Chart | `543171277c307f269ca413002eb783306c5d4e2a` |
| Overflow Android | `3c0f22632c65331853bbb0a1457f8dab2d29cde8` |
| Overflow Web iOS | `df756af08c9284c360ee80667c0c87764207c164` |
| Panel | `2fcd694709ef09672748c5bf342e8572ad807d64` |
| Partner Accounts | `8af1beddee5d4a084746dc48e194013d49326363` |
| Passkey | `6850b4c85d8553132baa08b1af84625ebe4f1834` |
| Pause | `d65bfc5ffca50ba4ed23587c3db6731eaf189a14` |
| People | `bdd60757910335ee9272ca62c4e60c38cee4b522` |
| Percent | `9396a2874dcdc9e9dd3b47bb574c476237ae0038` |
| Person | `ac102fbc0766a09afef51f40bd7edb05ff570f49` |
| Phone | `bf150d0c4be99acbf0ec7b8052467f44842a9abc` |
| Phone End Call | `2ab9586fd78d8c33a2e9655478b41d0a5d5e4e85` |
| Phone Handset | `eadb1236e8a9cbf31c7491c1f4d75d8dfaab2910` |
| Phone Missed Call | `ecd678bf1ef47ffbb4e73806d564ae0fc5e43dde` |
| Photo Filter Fill | `8d1f58b6456978df30ec9b88ecbdb29104c9ba4b` |
| Photo Filter Outline | `c69274aa231d762ebab16517aca45a0501489994` |
| Pin Fill | `6a4599670a0bb76a0be7e9c66215c183fa028885` |
| Pin Outline | `b8c21379376e6d80d2898311e10ebc5bcaa8d8f7` |
| Placeholder | `fc4fde30b32151a6dc5ece71a02e8bd89f1c74e5` |
| Play | `593628d2016579249393d73c099a146957345f06` |
| Playback Speed | `c53bca95cb1cb2b0e831ce77602b11851976a0dc` |
| Popular Content | `6b6c6b812b0f857ebf566b0328bc2b24bf5c2d73` |
| Popular Content Fill | `5b48383c9a2c6c6bfaf1e3951fd46809b99c61a0` |
| Post Fill | `5d157b5474d1af2aa173032d8922e93ff18196a2` |
| Post Outline | `ebe176a176bdc7c2732aadf8c7c666af02274ca0` |
| Printer | `a7267920c62fa8bc9f93e147cd6dc0229b79b8b2` |
| Question | `848dee6843675945718a84a2ce37e8d1be6f1d18` |
| Quote | `ed8fa8f430c4976213b3b3f6e239be3d04d3a380` |
| RSS | `3581f5deee999bd7e059d01dbe52f0f49daa3a09` |
| Radar Dish | `a3f9f52fdaf67feaeddd4b3ab65c64ff4b31f0d1` |
| Radar Screen | `ca28d5c02c4c4617ad87009aad05783a5f19a887` |
| Rate Applicant | `f71496ae7b221fa2574f4bdfb4ae4f44ae1a019a` |
| Rearrange Horizontal | `9aa91208eb389bccd92b1e89b61b2b97d0245c81` |
| Redo | `b727da0c4457b0d8d1f4e250ebbb3db9f1df20b0` |
| Refresh | `f3456c0ba49f5d5599b25984b9d3ee6f872aa29b` |
| Remove Connection | `ee49ae42fb4beeab68e5364c95246c232e4c58dd` |
| Reorder | `7abc2533192e8ea6249e867095bcad0ed3910d2f` |
| Replay | `325b0472a14e7f3dd1d4875e59d8d3aa69f11bea` |
| Reply | `9ff29dcd5de907209042375599f529ea4d7c562d` |
| Report | `b960ef9686cb49e7309c8ecfa11344766dfa86df` |
| Repost | `ccd9bffa22f71a385e9ad34eae646a6dd48b038c` |
| Responsive | `8c6c9de6b544f855ac4c922d09996f41519b0a82` |
| Rewind 10 | `ba46c65e44ec08d5332ee684c78c760285901c76` |
| Rocket | `07db5a5b45acf7337c67f969a018cb98580276cf` |
| Rotate Left | `e9bbbf26f7757ad699b9e8de325259a1919706aa` |
| Rotate Right | `b9927513b1b00844dd2df0703b9a57a3f3670eab` |
| Salary | `435f5c64ece774e57b3253bb550b4a709d055d81` |
| Saturation Fill | `fe33b03577ec13d084b3977d799d4fe3880bc070` |
| Saturation Outline | `84bf284efed210d71059291e3101a947f205af45` |
| Scan Add | `4f8e7a1e7b094772133201d4cb629cb3cd35892f` |
| Scan Person | `101577fb94cd753b585237866415f6027f3ec2c7` |
| Scan QR Code | `8762a4c76be949aeda442dc9427d599d8a9777ba` |
| School | `58ae80df2b8f7c65d0bfd98901f55ef312d3770b` |
| Search | `68909551951f5c92049e8e9e7b6ee29105c1a1b6` |
| Self-ID | `6e4e6d5dfe62612531e5c7c76105cc482653f8a2` |
| Send | `e173c7cb391dd6682fb15773baf5d294f62b0dc2` |
| Send Privately | `4a24694518541253cee4dccd2f467cfae9cb3d25` |
| Server Sync | `d46156bc282e911895db89f768c124a9f1790989` |
| Services | `3f8a6398c1e1a413acc2eb68703f75ef9e4945e7` |
| Settings | `6a07e3a5ec5b07f9b3ebdbe81e5f858966d9a551` |
| Share Android | `49588d359d9bf8db3483e55847eb1bfb3f9335ce` |
| Share LinkedIn | `6b5ff24da663e47a9ea94f3feab84b0420806aec` |
| Share Screen | `d3b73989d1ebc924b235fa3ae175577f419d8598` |
| Share iOS | `e7d9b791db22049195661a1789afccf749ac5b4c` |
| Shield | `1fe825d01bbdb35a9a8b7001599374126296d04c` |
| Shopping Cart | `3a40bdba7b6088bbd16dfe5316cde6dab698caf3` |
| Signal AI | `9c2d7ba4fe99c9f3bbdb9cb4b36e65f5a8dc2b06` |
| Signal AI Outline | `84e9858b96b4acec81c410baaa1a00a0991c192d` |
| Signal Caution | `71b77639e8d31b5c68cd8451c4cba8d167ed0519` |
| Signal Error | `352ea00df455e4434efd275c3e37cb8d050395a2` |
| Signal Notice | `207de213217411bb583562b944e4bf5aace77ef1` |
| Signal Success | `a199216b732dd2e90441a4abf35798b898771953` |
| Signal Success Outline | `052791be5f63fc6eb83e9fffa322e8cad9ace88d` |
| Skills | `a702310a96e772f4c4e1cf163b7bfc312d96104b` |
| Skip Back | `e2d6feda04b1c18f3de0161b973a14d7f281f763` |
| Skip Forward | `75a3e57a728ad0158afec4de3dbde0465cd3c884` |
| Slides | `492da7aa96a174a1b6f2cdca8430a759a34b92c5` |
| Sort | `58f72ba20793e0e86695fb550ad6b6289253940d` |
| Sort Down | `563bb356a968973a2e5e98ac62ce84dbedb507c7` |
| Sort Options | `dae38211ca27522eaf5ee0a96fd9fe932c8c4c82` |
| Sort Up | `91c8172474ec9403f6cec71eced3c87f2bdc9537` |
| Speaker View | `b5e53b3e9da0d74c87f53cc52b926b1ff90072a1` |
| Star Fill | `9d99fa9024ef770ce448153a7afa7eaf9167711b` |
| Star Half | `8d65ac81bc6dd0c7687eb114db08143b266110df` |
| Star Outline | `59143a77079f655a9be98f3ebbe8f137b701e87f` |
| Starburst | `4bfcaa42af98480e799ed36872b624600af1e69c` |
| Sticker | `3b97bd578da8214707141a688a0bf3f7aab3f0ff` |
| Sticky Note | `6161435dfd1f05225324745290b2bd1efd65e664` |
| Stop | `46ecf69a69a60097793486b634d34ac1933e8b16` |
| Stop Sharing Screen | `cbe77c7036b4a9276f79245b26e7e4597a837a97` |
| Style | `e0595e3eb0255b42f5bcb31e34c02e2745c86d78` |
| Subtract | `5c706f73044cead09f20a2c5d963382cab986b5c` |
| Table | `667652868bea4681579a210eff1fff9e54b837ea` |
| Tablet | `84def25ad31c3c07a3abc33d31002aa9a3454aad` |
| Tag | `ed6cdaa6e134f1216af56adcf4d64d035531e74b` |
| Tag Person | `713f953f2e1d0a4dc0be2d46971371456195e9d1` |
| Templates | `f4c8e37bd6cf44af71f26172f82dfd14077fc85b` |
| Test | `13933f54019411020d515c6bff9554a1ea2e7642` |
| Text | `016821188a7f24a7c5f525e8cda5f070b2e50d8a` |
| Text Align Center | `6792dc4f4794a39b38c60be3771376158a68fa59` |
| Text Align Left | `dd2fb57f0494f50236a1ce6f2797100d70ffb0b3` |
| Text Align Right | `ddee4323a06ed93f523120723056d4dbedbdb529` |
| Text Bold | `c767c9524fa6835808d32ea6dafe3f7a59b50773` |
| Text Box | `c62541c9142813f7a411c0469af05d6d534edbfc` |
| Text Bulleted List | `d4f4d30085898a68daf731414e7aced1de9d9627` |
| Text Cube | `dfe3a8bbbac959a915b8796789475f7986e1c01d` |
| Text Indent Decrease | `f95860293a6a79a76381c5bc42ad0e6b42ff882a` |
| Text Indent Increase | `023dcace9b782fee3aee417da6575a0e38360b5b` |
| Text Italic | `5d3272cd0beb2575c0247112dd7bc8d0f197884d` |
| Text Numbered List | `4b74f4af229b513e5cd9e585eba94304a8e6f46f` |
| Text Size | `a3a52a1e9fcc765bab029a301b672e8caa22c951` |
| Text Strikethrough | `f4fa90efd30921195acf5457f820b26471d42223` |
| Text Subscript | `c46d4066dd0ec427db071af1adc2e3b41c3d8464` |
| Text Superscript | `8e26c807f0b64b41c8f8d76e861d3f8f50239c3f` |
| Thumbs Down Fill | `0c6ace8ff052e070f82523f6269f3c17a9e404ea` |
| Thumbs Down Outline | `0a17faa9d16691beecab45c9c5a6ae70afa25c76` |
| Thumbs Up Fill | `6c013d029429c65ea18b0130b733399c066ebe8d` |
| Thumbs Up Outline | `3d7658e85cb9856cc663715f6f43f33e158ce2f2` |
| Ticket | `5797ba9a36992c8d42b14174ecf5533cf0de1d34` |
| Train | `bc6352470d6cee167de5ad4c38cc5f0f84d73ea5` |
| Trash | `7f5ad19ee563d8ce90fe0609ad103838cbf3c01d` |
| Trending | `976685f375c683b7dc9958952c57892ec08fd870` |
| Trophy | `6d271f0c70379316f824586f1174a89ee8082cae` |
| Unarchive | `49afcfc76e560976af54fe9a61d9bb4cf899708f` |
| Unblock | `e39b09000e685e3d01230e7581398224039f3887` |
| Undo | `933bf93c2b12b6887537c12c4bc11519f54c4c1a` |
| Unlocked | `1ff2e2157347822a59fffe2523363d3e258fb6a9` |
| Upload | `5c74bb94a3446a05e378160bf66a8a9b20fa32c3` |
| Verified | `002fc203dbbff6e2a5cb870d513b3645368313bc` |
| Verified Fill | `1b687ce224962d6fa0f2472f3fea08c7d63d8493` |
| Video | `31254f14773ffbb587653c25c92db08a8cd85a78` |
| Video Camera | `caf4bcecb03dca0ce2ad42fef84edb2def06e8f9` |
| Video Camera Off | `691a60d266e1dcf7bb618d97c946b76cd3cd4504` |
| Video Conference | `d298d79de696532f4c41c95b0749186b35de6dfd` |
| Video Inset | `081da7e83b8b1b5aa98b2c1a784eb1a9623b0c6f` |
| Video Square | `622148390748966327208df7fb78152bcff5635c` |
| Vignette Fill | `960b0a06e003f4750546aca447cdb0d01a98097f` |
| Vignette Outline | `3be02726ae26c7e9d811c56cbd27f9d874011e6e` |
| Virtual Chat | `8edcbef4eb245858e072dc5f1e7e408f9bc43063` |
| Virtual Chat Fill | `b3f5e544cbf2bfdc020e2843b815be2192b47470` |
| Visibility | `59703076bbe48f74e73acdae9f7c951e0cef0106` |
| Visibility Off | `a58e9560b6d11f9c819268159226feb44b34b0d4` |
| Volume High | `a46e57c481dd597729dbcc25d4bf83af9aea7e8f` |
| Volume Low | `6e7c37f0e96b695e5ff73dab0dee3001f2733894` |
| Volume Medium | `8aac1e17ac0eb4f94b1e108dbcfd76d24c6c5fdd` |
| Volume Mute | `b4117a17c49b39b79c77bf701846e87aa99015c3` |
| Walk | `4728f0b391d1630df78f03dcb8486c950a0e29f9` |
| Wallet | `042c071ba4fbaf9952421d5390877d81d68480d5` |
| Web Browser | `52f7b36298161e0f2fd4dae0f6c68f7db6a528fa` |

---

## Small System Icons — Full Key Reference

| Icon | Key |
|---|---|
| AMP Small | `4e1c431853c95cf2c32772e6d1474262f6258a29` |
| Add Small | `42467cf4cc721c82dcc6951d068b6befbb28370c` |
| Analytics Small | `36a71b1ee19cef3423ae780776e461d6f0f56ef1` |
| Archive Small | `9db36af8547e517138c98a09a877460600654ec3` |
| Arrow Down Small | `68ebb0e66e2909cf70522a96f94db8f2063aed85` |
| Arrow Left Small | `94db58f2ee6b1b825e1554970702707310358081` |
| Arrow Right Small | `49a0e45971faeb5687cd5da4629c68debe8d80a8` |
| Arrow Up Down Small | `d2edb3e7d12615a3a95be2eb7f4d87fb1239be00` |
| Arrow Up Left Small | `cce5dba6f574b8713d48f3361c575463cef55331` |
| Arrow Up Small | `bda5a3af1477a8e5ff5a3ce48c17561194e191fb` |
| Attachment Small | `dad11b286aea59a46059b8de87335bed522511aa` |
| Bank Small | `985ca23ce7b28ae9616b068aad96b4b1bac50d60` |
| Bell Fill Small | `bca2b2f5252d5ef7b1413aaf2374be71cfb46e55` |
| Bell Off Small | `fa065d38d1f3a745a49b50ae15cc02dd60faba07` |
| Bell Outline Small | `33df505e8c19f60f861411b802771dbef47fceda` |
| Block Small | `01dc9aa52ba07362cd2b6a0d0d58d4f4e6449ace` |
| Book Open Small | `7a79c3f0e16327e663000d924ec02e584502856e` |
| Bookmark Fill Small | `31663306ba720594ba254fad127d6a6344710c88` |
| Bookmark Outline Small | `898e348f81985a2dd0c41c30782d35ba7191240d` |
| Calendar Small | `a08eebbb59a7baca0498bdb9d98b7ec603265bbe` |
| Camera Small | `a4201547c08b49d56fbed9006dd9c009ed07975b` |
| Caret Right Small | `66ca63895c340bd1d6af9ef68077322f328275e7` |
| Caret Small | `a7b12cc49d96948e6c7041bd7c0e063537da05f2` |
| Caret Up Small | `f1d33691a34f394e3f02c1610f909a9d95294a73` |
| Certificate Small | `339d50abca339683e8bf5f4edeb82b2e3fd1b7e3` |
| Check Small | `76c5cb1df0957e0fc35d3a5f58a14aac3120576c` |
| Checklist Small | `ffa03381d2ba73112bcd0c9323ddf57f314b2f34` |
| Chevron Down Small | `89a54808ccd3c24ccca3b861d7b317ae2b0ea5c4` |
| Chevron Left Small | `bf1ed1765db109ee6c09f8db99f38045fcdf04ff` |
| Chevron Right Small | `6c6f1faeebc09eca5aeb3c84182fdc4c5ec19da6` |
| Chevron Up Small | `5fc069ed9f316c870153239387afde482321da22` |
| Circle Small | `9198f620b790759a2f33dd764b28e8b9a4748a91` |
| Clear Small | `3a122ff980373d86c9889b2512e794025a7ad53d` |
| Clipboard Check Small | `768ec2b5ed794c3f147131a6d4abcf3137d56f3e` |
| Clipboard Small | `c1989f85424e5d64a6f792c64b762aa42a644699` |
| Clock Small | `da6a7e8d14303adb71b0c7e211050a85694137d5` |
| Close Small | `5c484fa10ffb6f34f43a332a4b14a9da4d640c4c` |
| Closed Captions Fill Small | `d9484edcc538a36b9dee1e350373599d52012efe` |
| Closed Captions Outline Small | `d1f6df43eb8da4556289b7c56b15a0dcb4e93a92` |
| Comment Off Small | `e6706c8ff43da0a2d7a3d3f1ee1c866ab0573904` |
| Comment Small | `7fc62c5fc4eef282abae1c3232133b25b92c39e9` |
| Company Small | `4df040a991a5e8d867ddb42f26844a33f62cbd49` |
| Compose Small | `d97889aa93710078b2ffb5ff400474852ab79100` |
| Connection Add Small | `fb96c0ca0d5478def7a434c2715728c134fd2cc3` |
| Curly Braces Small | `7c0a48cf3705f2443fe09f4f1ba644ada1389e36` |
| Dashboard Small | `b659bf451b0919c74b0d5412bacd3bc099cf69ea` |
| Document Copy Small | `628717a8ee5e3856d0b0a92fcf2b9c61bc4dacf1` |
| Document Search | `468366abcf043251ac5d76acd4c6199fe0a2edb1` |
| Document Small | `58067b79b9d7eaf0710f484066585ee295380813` |
| Download Small | `a25ee680547d301aa8f689c5df894bd6216fc348` |
| Edit Small | `7582ca73af3f1c60af290889d3efbe423d194616` |
| Embed Small | `bdcce47886dd77b11002333d2202fd78b942c1d5` |
| Emoji Small | `4d484c668cb174212140566303770bc9e5680770` |
| Envelope Open Small | `bfa5fd78e1aef3523b08fead36b80ec19a384a03` |
| Envelope Small | `f80d18d0bb9a52bf38caaf69f2867c6f82a0c263` |
| Fast Forward Small | `d9719dc7a4da4b2482aaa519cf2c674c5103cac6` |
| Filter Small | `346b7f6033334fb5eab2bce674b688d2337d314a` |
| Folder Small | `a7836f98290553138fe1cc92ca6e192c47ffc0b1` |
| Format Font Small | `5ed68d04a21c11524b8c6ab8fc9d512646378fab` |
| Fullscreen Enter Small | `df3762179f1857daa066f375a48e62c59a43afd7` |
| Fullscreen Exit Small | `68bf4e572394b572de6dae2d8869f9a14a49b08c` |
| G2 Small | `e2e34a6ae18c6d09c3404d9d59468ac90eebd014` |
| GIF Small | `5085ea460593863baec5ba02bebe8620b6329685` |
| Gallery View Small | `b78161e3188b304e183cc7651ae0da78a42a6d13` |
| Gift Small | `114177b1c0fbb8119ce5f55f70c61cc3296d4b9f` |
| Globe Americas Small | `5b0dd434f2b4af7e8e4a2925f2fdf6b4dd7dfa12` |
| Globe Language Small | `bbe31cd4adc6b8ba28e46f0ec99819c6485a8e83` |
| Group Small | `b2e8a7f868d97418712ef42a776d7a564236dd74` |
| Hashtag Small | `febc00cf16fd9b25a1a66c02e619cc61b6b3b012` |
| Image Small | `134f95cb312a258b119ca31bb3c90b2f0f856b68` |
| Image Square Small | `2bf149f792ae7d4400c2e79bd7bfa432db1bbde0` |
| Import Export Small | `2655aad721cd65e777f11713ffa41180f6245596` |
| In Common Small | `12a863650356952ecf67a7069689cae64816b15b` |
| Job Small | `8cb2c56b86524a5100d10db5e07fabc729bfefdb` |
| Keyboard Down Small | `4f97669f62c66336e74885b083cfab95172a091a` |
| Keyboard Up Small | `6d3ece62843f6ebf31217fc2b31260a8e0b53248` |
| Lightbulb Fill Small | `60c4338bb5e702613cd5e14904fda49fe150c272` |
| Lightbulb Small | `6727a0b9f4ec895afa86cd11043b7b14b43e19dc` |
| Link External Small | `85beabf28c3bafbe1fad03a9f52fe18144dc5457` |
| Link Small | `6454d60fc7352eb2485820b96876f6e5dfbd9852` |
| LinkedIn Bug Influencer Small | `745c83082f22be4261bbff7b3e1799272295e60a` |
| LinkedIn Bug Small | `0a9a7e730c54278741c799eab34f8158e4224d77` |
| Location Marker Small | `f41404a3cb74c874df5abb80676ceeaec0383926` |
| Locked Small | `70be677b31515c995ca3ef35a7b1024d9e160e64` |
| Magic Wand Small | `02787878e2f4b0890ea50625a3bfd0e84ba8bf83` |
| Marketplace Small | `b6ae65c1b94d37f8d4dec53924f5fb85b24e84fb` |
| Maximize Small | `9e34d1d6be5075e143b8a052de5477688232cb21` |
| Mention Off Small | `639814f91d232f0bc2933afb2f8c3c337343438b` |
| Mention Small | `6ccf366a9da01c8b8fd2804200db932bb9de5746` |
| Messages Small | `c0b51409d25cfc558209457fc78ed00fa4deea9c` |
| Microphone Fill Small | `99b790e04791f3d5ad177bb59439931043dff2f3` |
| Microphone Off Small | `ea2a1327bd09e8be3a858e9cb7e5b3488b0c5694` |
| Minimize Small | `5131fe1811ffcc61e2b4833010b94656bfefddfe` |
| Newspaper Small | `b84e561f7c6a876bd69c49b05ad957bbee3d9ab0` |
| Org Chart Small | `06e0964bc54c4fd347244600b96c6c55a6c36446` |
| Overflow Android Small | `477acea691fb5718342a2afee9cecb38a383b785` |
| Overflow Web iOS Small | `45045846e2419571090eccf01294abeb0baec95e` |
| Pause Small | `9fb23c73bc1a053d5c193b8d8ad6ef13fa6cfe33` |
| People Small | `ff392a62aedd93de41038afff56b3db6e623b02d` |
| Person Small | `3854d3c5c04efc6425519a3c87d2fb6631420d00` |
| Phone Handset Small | `ec5456748808251fc9c4580ccb460b076987d04b` |
| Phone Missed Call Small | `888646979549f17712dab33b4637a3b600368987` |
| Pin Fill Small | `b3ef9ba51c9857799747539ce9108e3f835586ce` |
| Pin Outline Small | `da5888eac33b4eb88c384b8db3a9a8853f5de3cc` |
| Placeholder Small | `58b75ca10538606b77a4913403a4fdde02486ab5` |
| Play Small | `3bcd69ba1dd74ec97ee5958143964af350d8f1e8` |
| Popular Content Small | `7ba3488d2587c8464dbbd2d019a8bd648b43c004` |
| Question Small | `6f09bed3930a23f52ab4bd2ba3d79c2e6eab42d8` |
| Quote Small | `50ba6552bb47f1108f5456b71984d63c3c0c63c6` |
| RSS Small | `e414bc4b1ea3788212f3323db803f07fddcb5142` |
| Radar Dish Small | `e08ea7708f98c5bd5b96c254d75397c25c34fafc` |
| Radar Screen Small | `49a8a50a1ae6346210a23007358bd16132315d8d` |
| Rearrange Horizontal Small | `3dce62dc0d76c3938da0dab200a3efdace137460` |
| Refresh Small | `c7f0c6b770db61df5420ee1554a52457f04ebab8` |
| Remove Connection Small | `e1939178c78973622e79f65e8271b8994524d9a6` |
| Reply Small | `036659682accf071c7b57c7278c977119307ec6b` |
| Report Small | `fc421c06619345e034001669a0ef6207e6a349c2` |
| Repost Small | `3766ada9e60738d4f8bfd189e2727b5acacaf333` |
| Responsive Small | `18e073b04aac609b4d56de69dc380e8241593ca9` |
| Salary Small | `f1af48138e8ef4a654a7e623ae3881b4ee52d26b` |
| Scan QR Code Small | `b921b950f34aefdbae8b51239992b7dc9932e00f` |
| School Small | `e0c1e29dc2c463424bc6032b521e679bc0771c26` |
| Search Small | `9e247da213de42ed47240a38a62f9ddefcd2bd28` |
| Send Privately Small | `ab3cd914cb3da4ddf90a3740ca9813827f45c56c` |
| Send Small | `e782456c2a325899e421274845a0725f7e1c11d6` |
| Server Sync Small | `13cc6b9c0eddbb1d35e0ae509bf2d0d88385c8dd` |
| Services Small | `2d795fd280284e098de77d7446ecdefcb1bccc75` |
| Settings Small | `daf60a9941d6bad279a10186c25ad28639d69beb` |
| Share Android Small | `9f29c1b534f7a4d3923005b0680ef1b08e29f15c` |
| Share LinkedIn Small | `cdeee73376cd0ea960ef7daea314ded82fe3de9d` |
| Share iOS Small | `7844a1b384985b76b4823df5e1dd55ea6eefb4a4` |
| Shield Small | `70e6e72d73e943b393d6a873d47b5fc7044d7ce8` |
| Signal AI Outline Small | `249b754844a47e82f8a6788816c656e4c56940f9` |
| Signal AI Small | `e6822e1d7ee2546c53133fc79e1e89058373478d` |
| Signal Caution Small | `cbd79119a3a4f11579796ad70394ae03505126f3` |
| Signal Error Small | `dbec4a9e79e0188f077949e60e9be21ed2186d70` |
| Signal Notice Small | `90ab51bd9429df93981c5fce3d231fd5ce2d8351` |
| Signal Success Outline Small | `4bf3992b2ea6b1c9accac22053d51296e9002065` |
| Signal Success Small | `d3b4ce8d19a49a0153e903c8e0a28f711c1ed300` |
| Skills Small | `50fdc21b20a2416e8317bb227dc60784e35e6508` |
| Skip Back Small | `926ff77a4acf2ef7d375545255b0260475288d23` |
| Skip Forward Small | `3416ccae34a5ddf49c1214c25df1980b7b47b580` |
| Slides Small | `8755441d88e977f67b14e52bf6bef7b6b8aa1701` |
| Sort Down Small | `233b0a9dd6b8feba2bd67ba9105d102b7d43f6b1` |
| Sort Small | `9993a168d7c3eb6f51ec282eb586235cb6ec2d2e` |
| Sort Up Small | `e1d79d413607aa803322d24429ea82f7465b63ce` |
| Star Fill Small | `b34bc551b50565527cde03fa7f54cc1135b61b47` |
| Star Half Small | `7bb73de91b9b6860e6cdeeb3e5f1cfb8c077f8ec` |
| Star Outline Small | `a2208711d82ac64446957e15e4ef996d0b17a4f6` |
| Starburst Small | `66b09fc07602fc7dd330da0f2e0cea77fa700e7b` |
| Sticky Note Small | `ac642d66121b99d7cf3e84f2c936d224d0df3b2a` |
| Stop Small | `0ee671a0e26a4280f5169dd0c94e9b40546033da` |
| Subtract Small | `ef82fc0b78dbb2490ac2760ea37e948603103c6b` |
| Tag Small | `98d3f2d208d133fabeb244877238a4deba64318f` |
| Templates Small | `c28b1904309e14a2aa7ea91fdd7be61c15636209` |
| Test Small | `f9e4e6c5d152c15119f9bc1d7ba3f1d6229acfea` |
| Text Align Left Small | `0c1de3588cbe78f5c144a9651d744ba491f26a89` |
| Text Bold Small | `dc29c97905c8eb8e8532cee61c3769665e4ea7a5` |
| Text Bulleted List Small | `9cea981fa159144931b9d38c1cb226019be5dd67` |
| Text Italic Small | `e7fda51fb01ec4cc25f0e70634b57c1fe25bdd36` |
| Text Numbered List Small | `efe4d42651cdb9c11d4d3bdaf192d8bd7288719c` |
| Text Underline Small | `293275cc65d179c1a565d67a169b92c4a9f8a915` |
| Thumbs Down Fill Small | `bba87305b3bd92e9a0940dcdf9cb35e502348c58` |
| Thumbs Down Outline Small | `fa19cea6da2a391ba7422f85dbd47a22e75ccf5a` |
| Thumbs Up Fill Small | `a9abab3496493bc579c03d47599b0612dbc16534` |
| Thumbs Up Outline Small | `884713c385fbebcfb86521b4a264c28c1e6bd101` |
| Trash Small | `8b545a92f0494f2fd3d391b6deea7ea072d6ae9a` |
| Trending Small | `96b5244e9d483cc29c584a0808bd15e90f05fad4` |
| Trophy Small | `13a10e95778ad7e30b8687c82e4c546f58f96ba7` |
| Unarchive Small | `9700338e00cda80381d7fc4d45b7f4d14693c9ad` |
| Unblock Small | `279e9fa40abb46961b187666586646e42d79ffea` |
| Undo Small | `d6530229f71b12a15eece14caf6dc80e8977ed62` |
| Unlocked Small | `d596a8675d88bce4eadafbe047a27d87b1d43aea` |
| Upload Small | `0cb759bc5d9041d3b64a0a3f73d08efc42686f29` |
| Verified Fill Small | `9996dd5ed6ac639ad71478bd6e8e96d6a0d82dde` |
| Verified Small | `fc735f7c74cff9b49eceba5137d9f8b1e6495326` |
| Video Camera Small | `ae9ba6348f8ae9853dc89929d996b819e991abe6` |
| Video Conference Small | `064157148137d3f0cb179dcdc6324d5362d72b4a` |
| Video Inset Small | `10d942cb2bb344dfa72068859d47d6fd5c5dc563` |
| Video Square Small | `6ba5473aac51c29efb1c627f2a78a0fcc692c5ad` |
| Virtual Chat Fill Small | `2f77395107023e2e72f347734709aaa01e5a7394` |
| Virtual Chat Small | `0ee3c0ca5f34c89847c4d009dd2cb8b39100f7ae` |
| Visibility Off Small | `c7f7db184c8f07c33726ceaa4b04fb0028972f8c` |
| Visibility Small | `53aafbaa2cfe1ab57b6f0919e16e5c72df2e61b2` |
| Volume High Small | `a9db8f5d3163ad35ab573028f304c5a28979c304` |
| Volume Low Small | `c79d0d4547b58aa9be0d1b81e5667c64eaa9413d` |
| Volume Medium Small | `e896c5010d434b38fae664b576f5e9fe7f7fd96e` |
| Volume Mute Small | `e1f7f96a838913c5750877e7016bda8e5aaeb5c9` |
| WhatsApp Small | `195976eb100018d6a3b6016a476d8123fbc73954` |

---

## Large System Icons — Full Key Reference

| Icon | Key |
|---|---|
| Bookmark Large | `a7f30a201abddf5a9a5919b8e1ff9c01203ea6b5` |
| Bookmark Outline Large | `6a02bc1724708a0bfe42839d9d2f22f50d7a95da` |
| Comment Large | `de5a2418756763be0a4f18402db7c1ead219a053` |
| Fire Large | `b6a3527d4aaf2e4f31eb5d8bf5abb0527d2b698d` |
| Gift Large | `350b11b49a56f275907dd460c11f590965d71b06` |
| Hand Point Large | `3a9cf329e1b4bfcc7d8a2e120fc511aa86faf26e` |
| Passkey Large | `09b8bdd2441bd6294607a672d8a76f17658b7af8` |
| Phone End Call Large | `3e46b37b681874d2be1b0c6bd01b287d1ba36142` |
| Phone Handset Large | `3f6c57c473095f419be4d5e289cdb4b373634401` |
| Play Large | `6545584a9135909350db7c5d16288b25dad5de0b` |
| Repost Large | `d249f3bccc96b67705a9f5fb260bebb3546cfe8b` |
| Send Privately Large | `410c93b2b847271e772443f72253cba4a3bfa616` |
| Send Privately Outline Large | `36c42032589e2965dbb585d3ac86c98ec16fce8a` |
| Share LinkedIn Large | `356ac40f97f37823d58b3970444e158bfc89f5f4` |
| Shield Large | `cd52c2dff54833a56640527ffd1fee5c1726395d` |
| Signal AI Large | `faa34883d3c46adb06f7c188538753c1715167fd` |
| Signal Success Large | `ba89db3e3c882347e1719c182a4508604c754f1a` |
| Signal Success Outline Large | `77a6cd427d892bbdc1ad60b2003041c247051fde` |
| Star Fill Large | `64c08db6d4e632ae33786ec17097a45b81f7b7f0` |
| Star Half Large | `0ece67e66866ae15434afbf74dc5ff24cc01efdd` |
| Star Outline Large | `73eddfb62ee6e16c9da0a0d2ca3e499e83ca1d28` |
| Thumbs Up Outline Large | `d568ac88e5759835cb35f862d18237d6c6c86ce0` |
| Verified Fill Large | `77d943fee5a6cdf5101a81f382f099f2b21e3687` |
| Verified Large | `2a50097b7e678d1a14c224c51597c09696caaa8d` |
| Visibility Large | `c3f99b081fd7ce03523be0420d7730801852aaf6` |

---

## Implementation Guidance

### Sizing

- **Default size is Medium (24px).** Use 16px (Small) or 32px (Large) only when the component slot or surrounding context requires it.
- **Do not resize icons.** Scaling to arbitrary pixel values distorts the icon's visual relationship with typography. Stick to the three system sizes.

### Alignment

- **Center-align icons with adjacent text.** Do not baseline-align or manually pixel-push icons into position — center alignment is always correct.

### Accessibility

- **Screen reader labels:** All meaningful icons must have a descriptive label for screen readers. Icons that are purely decorative (supporting visible text) can be hidden from assistive technology.
- **Tab navigation:** Interactive icons must be reachable by keyboard and show a visible focus state.
- **Color contrast:** Icon colors must meet a 4.5:1 contrast ratio against their background.

### Labels and Icon-Only Usage

- **Provide a text label** when the icon's meaning isn't immediately apparent to all users.
- **Icon-only is acceptable** only for universally understood actions: cut, copy, paste, and text formatting controls (bold, italic, underline, etc.).
- For all other actions, pair the icon with a visible label or a tooltip.

---

## Icon Patterns

### Help vs. Signal Notice (Info)

These two icons are commonly confused — they have distinct behaviors:

| Icon | Behavior | When to use |
|---|---|---|
| **Question / Help** | Interactive — activates a HoverCard that persists until dismissed. Can contain interactive elements (links, buttons) inside the HoverCard. | When users need contextual help that may require action |
| **Signal Notice / Info** | Non-interactive decoration only. Always pair with adjacent visible text. Never use as a standalone trigger. | When supplementing visible text with a clarifying visual |

### Directional Icons

Use the correct directional icon family based on the navigation pattern:

| Icon family | Use for |
|---|---|
| **Arrows** (Arrow Up/Down/Left/Right) | Page-level or section-level navigation. Moving the user to a different page or scrolling large distances. |
| **Carets** (Caret Up/Down/Right) | Opening a menu or dropdown selection list. Always paired with a trigger element. |
| **Chevrons** (Chevron Up/Down/Left/Right) | Expanding or collapsing inline content (accordions, show/hide sections). Never use chevrons for page navigation. |

Do not substitute one directional icon family for another.

### Messaging Icons

Multiple icons cover messaging-related actions — use the correct one per context:

| Icon | Use for |
|---|---|
| **Comment** | Opening a comment input or viewing comments on a post |
| **Messages** | Navigation entry point to the LinkedIn Messages experience |
| **Messages Active** | Navigation selected state when the user is in the Messages tab |
| **Send Privately** | Sending or forwarding something privately to a specific person |
| **Send** | Submitting or sending a form/message |

### Navigation Icons — Selected State

When an icon is used as a navigation item (left rail, bottom nav), use the active/filled variant when the item is in the selected state. Pair with a selection indicator as defined by the Navigation component.

### Platform-Specific Icons

Some icons have platform-specific variants. Always use the variant that matches the platform you're designing for:

| Icon | Variants |
|---|---|
| **Share** | Share Android, Share iOS, Share LinkedIn / Share Web — use the correct platform variant |
| **Overflow menu** | Overflow Android = vertical three-dot (⋮); Overflow Web / iOS = horizontal three-dot (•••) |
| Visibility Off Large | `e7e6db444a09bdb1e866125c5db57a1cb3d91e54` |
