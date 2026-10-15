# Composition system

Composition principles: one dominant subject, a hierarchy of overlapping interface panels, unequal close-up insets and layout variation. Keep Orbitals cel-anime rendering and game UI throughout; do not use pixel art, desktop menus or restricted palettes. The goal is that every image reads as **a captured moment from the game starring the user's subject** — not just a style filter.

## Contents
1. Layer stack (what every image contains)
2. Scene concept (the mini-story)
3. Layout archetypes
4. Variation axes
5. Compatibility rules
6. Preflight checklist

---

## 1. Layer stack

Build the frame from back to front:

| # | Layer | Rule |
|---|---|---|
| 1 | **Painted world** | Background scene in the chosen mood palette, set in outer space by default (deep space, orbit, station exterior or viewport, a small planet's surface) unless the user names another setting. Use 1–3 subdued, subject-relevant world details. Prefer broad painted colour fields, a simple ground plane and one low-contrast distant silhouette. Keep the setting readable without filling it with texture. |
| 2 | **Hero** | Exactly one hero composition — the user's subject, or the anchored group as one unit. Covers **55–75%** of the frame (never below 45% after overlaps). Placed off-centre. Never contained inside a small UI window. The main scene may use an inset frame, with foreground features breaking across its boundary. |
| 3 | **World enrichment** | 1–3 restrained story details that extend the subject into the game world (see §2). Additional narrative information belongs in functional panels rather than extra floating props. Keep world details smaller and lower-contrast than the hero. |
| 4 | **FX** | One localized FX family connected to the action. Default to a few purposeful trails or one restrained burst; do not combine all-over speed lines, floating debris, dust sprays and sparkles. |
| 5 | **Close-up insets** | 1–2 unequal partial-feature cards within a total of 3–6 interface panels (default 4–5). Use retro game frames with corner tabs, cream/navy edges and blue/salmon accents. Each shows a *partial distinctive element* — a reaction face, the signature accessory, a paw, an eye behind glasses. Never a second full copy of the hero. With two insets, give them different sizes and different crops. |
| 6 | **Typography & HUD** | 2–5 text elements from style-guide §3: exactly one *big type device* (chapter title / onomatopoeia / item title / logo), plus 1–4 small ones (dialogue subtitle, quest HUD, buttons, P1/P2 badges, counter). |
| 7 | **Screen surface** | Grain, chromatic aberration, bloom, vignette; optional letterbox. |

Hierarchy: Hero (L) > big type device (L/M) > insets & enrichment (M/S) > HUD (S). Overlap layers by 5–20%: the big title may cross in front of the hero's body but must never cover the face; insets may overlap the hero's edge. Keep **25–35% connected calm space** (sky, starfield, flat red field, letterbox) so the frame breathes.

## 2. Scene concept (do this before writing the prompt)

Invent a tiny game moment around the subject. Answer in one line each:

- **Chapter**: a 2–5 character Japanese title + Chinese translation that puns on the subject. (cat → 「猫の惑星」/「猫之星」; coffee cup → 「目覚めの炉」/「苏醒熔炉」)
- **Mission**: quest HUD text, e.g. 「找回逃跑的毛线球」/「◇ 已收集毛线 2/5」
- **Line**: one short natural Japanese dialogue line (aim for ≤ 20 characters) with a Japanese speaker label. Match the subject and tone. Preserve exact user wording or a requested language instead; do not reuse a fixed line across subjects.
- **Enrichment**: 1–3 quiet world details plus subject-relevant panel functions that translate the subject's traits into Orbitals objects. These are options, not a checklist to accumulate. Good enrichment is *specific to the subject*:
  - a dog → floating bone-shaped asteroid, scout pod with dog ears, a paw-print on the airlock
  - a person with a camera → camera turned into a chunky retro-future device with glowing lens, film strips drifting like debris, a teal scout pod photobombing
  - a city skyline → buildings as overgrown orbital towers with cables, the three-lamp scout pod flying past
  - generic fillers when needed: the teal three-lamp scout pod, a chibi mechanic mascot in goggles, floating cargo crates, red four-point star flares, glowing orange lamps.

If the user supplied any of these (title, dialogue, mood), use theirs verbatim.

## 3. Layout archetypes

Choose one. Each names a layout that actually appears in the game.

**A. 章节标题卡 Chapter card** — cinematic letterbox; hero in a deep painted environment at 55–65%; giant white Japanese title across the centre band crossing the hero's body (not face); small Chinese subtitle beneath; dialogue subtitle in lower third; one inset bottom-right. Best moods: ruins, furnace, aurora.

**B. 角色切入 Cut-in** — diagonal split: a giant dramatic reaction face of the hero (cut-in, top-left to centre, cel-shaded in a duotone of the mood) above an action shot of the hero (lower-right) with a neon beam or explosion; localized speed lines; huge vertical onomatopoeia on one side; quest HUD top-left. Best moods: warp neon, furnace.

**C. 道具获得 Item get** — radial white/pale-blue burst behind the hero's signature object or the hero holding it, on a painted orange-flame or golden-swirl field; red katakana item title arched at top with Chinese label; dialogue subtitle bottom-left; one inset. Optional duplicated split-screen (two identical halves) like the game's co-op view. Best moods: furnace, golden vortex.

**D. 双人分屏 Co-op split screen** — vertical seam down the middle; each half shows the hero from a different angle (or, for a pair of subjects, one per side); quest HUD top-left of each half; P1 inset with blue frame on the left edge, P2 inset with salmon frame on the right edge; shared dialogue in the lower third. Best moods: ruins, control room.

**E. 主菜单 Main menu** — crimson flat diagonal panel on the left 35–45% holding 3 menu pills (the selected one blue and glowing); hero on the right in a starfield/aurora or painted scene; slanted logo-style title over the hero's area; P1/P2 badges top-right; button prompts bottom-right. Best moods: red menu, aurora.

**F. 对话特写 Dialogue close-up** — over-the-shoulder: a large out-of-focus back-of-head/shoulder of a supporting character in the foreground (left 30%), hero facing camera mid-ground at 50–60% with a strong expression; control-room panels with LEDs behind; dialogue subtitle centred bottom; one small inset. Best moods: control room, red menu.

### Interface depth and background restraint

- Default to 4–5 panels in an asymmetric L, staggered zigzag or counter-corner layout. Use a clear size hierarchy such as 1 large + 1 medium + 3 small, with different aspect ratios and 5–20% overlap at selected edges. Avoid equal tiles, rigid columns and uniformly separated cards.
- Count the 1–2 partial-feature close-ups inside the total panel count. Crop different distinctive details (eyes/accessory/paw/tool), never repeat a full figure. Other panels serve the subject: an action gauge, map, object readout or mission status, not arbitrary decoration. Compact labels and diagrams need not add more narrative text blocks.
- Keep the hero unboxed and dominant, with face and defining action unobscured. Some panel edges can overlap the hero silhouette; a small prop may pass behind an edge. Use scale and occlusion for depth before adding foreground scenery.
- Keep the background low contrast and low detail. Avoid dense stars, detailed planets, crowds, layered machinery, rubble, dust sprays and oversized foreground consoles by default. These may be used selectively if central to the user’s subject, never all together. Fine film grain must not become visible dirt or speckle clutter.
- If the result is busy, simplify the background and FX first while retaining the useful window hierarchy. If flat, improve panel size differences, overlap and feature crops before adding objects.
- Adapt to each image: a pet may use paw/ear details and a route map; an object may use a material detail and a function readout. Do not automatically add a football field, shoe crop or charge gauge to every subject. The space setting is the default backdrop, but the panels and props still come from the subject.

### Inset frame, black surround and controlled fisheye

- Default surround: uniform opaque black (#000000) outside the inner scene frame. No cream mat, coloured wallpaper, stars, noise, gradients or scenery outside it. Only selected foreground overflow elements and a very restrained edge light may interrupt the black. Keep visible black space around those elements.
- **Shared size reference for every frame:** open and attach `assets/frame-size-reference.png` as a geometry-only reference. The following measurements are approximate visual targets from that image, not pixel-perfect tracing. Match the frame footprint, black surround and border weight; adapt panel positions to the subject, and do not copy the reference subject or its story.
- **Main frame and black band — the same at every canvas size:** the frame is centered, and the pure-black band between it and the canvas edge has the same thickness on all four sides: **7–8% of the canvas's shorter side** (never under 6.5%, never over 9%). The frame is whatever is left inside that band, so it always has the canvas's own aspect ratio, slightly narrowed. Derive the band from the shorter side for every ratio, including custom ones; do not let a wide canvas get thin top and bottom bands, or a tall canvas thin side bands.

  | Canvas | Band on each side | Frame |
  |---|---|---|
  | 4:3 — 1536x1152 | ≈ 86 px | ≈ 1364x980 (89% x 85%) |
  | 16:9 — 1536x864 | ≈ 65 px | ≈ 1406x734 (92% x 85%) |
  | 3:4 — 1152x1536 | ≈ 86 px | ≈ 980x1364 (85% x 89%) |
  | 1:1 — 1254x1254 | ≈ 94 px | ≈ 1066x1066 (85% x 85%) |

  The most common failure is a frame drawn at 95%+ of the canvas with only a 1–3% black strip: that is wrong, however good the scene inside is. Think of a picture mounted on a black card with a generous border, not a screen with a thin bezel. Use a gently bowed rounded rectangle; corner radius roughly 3–5% of the shorter canvas dimension. The cream/navy double-line border assembly is about 1.2–1.8% of the shorter canvas dimension, with each cream stroke about 0.3–0.5% and narrow navy separation. This is a graphic border, not a thick monitor housing.
- **Inset-panel sizes:** preserve the reference's unequal hierarchy: one large panel about 27–31% canvas width by 24–29% height; one medium partial-feature panel about 22–26% by 22–27%; one narrow/tall partial-feature panel about 18–22% by 23–28%; one compact status panel about 15–18% by 16–20%. These are approximate bounding boxes before small rotations and overlap; adapt positions or orientations rather than forcing identical tiles. Count close-ups within the existing 3–6 panel limit.
- **Every inset border:** use a crisp cream band with a thin dark-navy outer keyline and inner separator, total edge assembly about 0.7–1.1% of the shorter canvas dimension; cream band about 0.4–0.7%. Prefer square or barely softened corners as in the reference, rather than bulky rounded pills. Scale all stroke widths with canvas size, not panel size, so small panels do not acquire thick borders. Panel sizes may differ; their border weights remain consistent. Colors may follow the chosen palette while the proportions stay matched to the reference.
- **Prompt and final check:** state the main-frame footprint, black margins, inset-panel hierarchy and line weights explicitly in the generation prompt. Compare the final image with the bundled size reference, checking visible unobstructed portions of the frame; foreground overflow must not be mistaken for reduced black margins.
- Make 2–4 meaningful frame breaks across at least two sides, with unequal sizes: one major subject extension plus smaller relevant features such as a hand, fish tail/head, hair tips, leaf branch, prop tip or one panel corner. Choose from the subject rather than adding unrelated objects to fill a quota. For the fish-boy composition, the tail can cross left, the snout/hand right, and a smaller hair or panel edge can cross top.
- **Overflow size — match the reference, where overflow is bold, not a fingertip poking out:**
  - *Major extension (exactly one):* a large part of the hero or its signature object (a whole forearm and hand, a leg from the knee down, the fish tail, a wing) sticks out past the frame across 70–100% of the black band's thickness, stopping just short of the canvas edge. Along the frame edge it spans 20–30% of that side. In the reference this is the fish tail on the left.
  - *Secondary extension (one or two, on other sides):* sticks out across 40–60% of the band and spans 10–15% of that side. In the reference this is the fish snout on the right.
  - *Graphic overflow (at least one):* the big title device and/or one inset-panel corner rises across 25–50% of the band. In the reference the red title crosses the top and right edges and the SONAR panel crosses the top-left corner.
  - Together the overflowing elements cover roughly 15–25% of the black surround. If only a hand or a few hair tips cross the line, the overflow is too small.
  - Plan for it when placing the hero: put the part that will overflow at the frame edge on purpose and scale the hero so that part is genuinely outside. Do not shrink the frame's black margin to fake a bigger overflow, and do not enlarge the frame to contain the hero.
- Render those extensions in front of the border: hide the border exactly behind their silhouettes, use a subtle rim or contact shadow for depth, and keep them visibly connected to the source object. No extra limbs, duplicated full subjects, detached parts or repeated fish. Let each extension travel deep into the black margin. The major extension may run almost to the canvas edge (leave about 0.5–2%), as the fish tail does in the reference, but it must not be cut off by the canvas edge.
- Apply mild fisheye/barrel curvature coherently within the scene: gently bowed horizon/panel lines near edges, modest corner compression and restrained central expansion. Keep central face, hands and anatomy natural; make text readable. The canvas and black surround stay flat, and foreground frame-breaking features should remain coherent rather than excessively warped.
- Preserve the quiet-background rule and unequal interface hierarchy. Achieve depth through occlusion and curvature, not extra debris, machinery or texture. Keep the Japanese subtitle clear of the border and overflow.
- On aspect-ratio edits, extend/recompose the scene and border together; never stretch the whole raster. The default canvas is 4:3. For 16:9 to 4:3 without losing side content, add space above/below. Do not silently apply a one-image ratio change to other subjects.

## 4. Variation axes

Pick one value per axis. If earlier images in this conversation used a value, change at least two of: archetype, hero placement, crop, mood.

| Axis | Options |
|---|---|
| archetype | A chapter-card / B cut-in / C item-get / D split-screen / E main-menu / F dialogue |
| mood | red-menu / aurora-space / overgrown-ruins / furnace / golden-vortex / warp-neon / control-room |
| hero placement | left-third / right-third / low-rise (rising from bottom edge) / diagonal / over-shoulder |
| crop | reaction close-up / bust / waist-up / full-body / object-hero |
| big type device | chapter title / onomatopoeia / item title / logo |
| FX family | speed lines / radial burst / hyperspace streaks / neon beam / sparkle stars / floating debris / cel explosion |
| inset count | 1 / 2 (unequal sizes and crops) |
| small text set | dialogue only / dialogue + quest HUD / HUD + buttons + P1P2 / dialogue + counter |
| frame | inset scene on black with foreground overflow (default); explicit full-bleed / letterbox / split-screen overrides |

## 5. Compatibility rules

- The default inset frame wraps any archetype; its internal letterbox or split seam can coexist with the black surround. The hero is unboxed relative to UI panels and can cross the scene border.
- Archetype fixes some axes: A → letterbox + chapter title; B → onomatopoeia + speed lines/neon beam; C → item title + radial burst; D → split-screen + quest HUD + 2 insets; E → logo + HUD/buttons/P1P2; F → dialogue + reaction close-up or bust.
- Total text elements ≤ 5. With 2 insets use ≤ 4 text elements so the frame does not clutter.
- Reaction close-up crop pairs with B or F only; full-body pairs with A, C, D, E.
- Hero coverage beats decoration: if layers crowd the hero, drop an enrichment element or the second inset before shrinking the hero.
- A group of subjects stays one hero composition — keep everyone, their left/right order and interaction; never merge or drop a person.

## 6. Preflight checklist

Before compiling the prompt, confirm:
- [ ] one hero, 55–75%, off-centre, unboxed, face uncovered
- [ ] 1–3 subdued world details; functional panels distributed across multiple quadrants
- [ ] one FX family touching the hero
- [ ] 1–2 insets showing partial features, unequal if two
- [ ] exactly one big type device; total text 2–5; every string short and quoted
- [ ] 25–35% connected calm space; background and FX are visibly quieter than hero/UI
- [ ] 3–6 unequal panels with purposeful overlap, including 1–2 distinct partial crops
- [ ] short natural Japanese bottom dialogue unless user wording/language overrides
- [ ] uniform black surround and main-frame/panel dimensions matching the bundled frame-size reference; readable inset border; equal black band on all four sides, 7–8% of the canvas's shorter side, at any aspect ratio
- [ ] 2–4 coherent frame breaks across multiple sides: one major (70–100% of the band, 20–30% of the side), one or two secondary (40–60% of the band), plus title or panel overflow; nothing cut off by the canvas edge
- [ ] mild inner fisheye, stable central anatomy, legible text, flat outer canvas
- [ ] space setting with sparse stars and at most one planet or nebula band, unless the user chose another setting
- [ ] 4:3 by default; target aspect ratio respected; aspect edits preserve side content without stretching
- [ ] identity anchors (3–5 per subject) carried over; everything else redrawn in the 80s cel style
