# Composition system

Composition principles: one dominant subject, restrained functional HUD, strong pose, and layout variation. Keep Orbitals cel-anime rendering and game UI throughout; do not use pixel art, desktop menus or restricted palettes. The goal is that every image reads as **a captured moment from the game starring the user's subject** — not just a style filter.

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
| 5 | **Functional HUD** | Use compact mission, status, map or button elements only. Do not add detail-window enlargements, portrait insets, or partial-feature cards. |
| 6 | **Typography & HUD** | 2–5 text elements from style-guide §3: exactly one *big type device* (chapter title / onomatopoeia / item title / logo), plus 1–4 small ones (dialogue subtitle, quest HUD, buttons, P1/P2 badges, counter). |
| 7 | **Screen surface** | Grain, chromatic aberration, bloom, vignette; optional letterbox. |

Hierarchy: Hero (L) > big type device (L/M) > enrichment (M/S) > HUD (S). Overlap layers by 5–20%: the big title may cross in front of the hero's body but must never cover the face. Keep **25–35% connected calm space** (sky, starfield, flat red field, letterbox) so the frame breathes.

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

**A. 章节标题卡 Chapter card** — cinematic letterbox; hero in a deep painted environment at 55–65%; giant white Japanese title across the centre band crossing the hero's body (not face); small Chinese subtitle beneath; dialogue subtitle in lower third; compact HUD only. Best moods: ruins, furnace, aurora.

**B. 角色切入 Cut-in** — diagonal split: a giant dramatic reaction face of the hero (cut-in, top-left to centre, cel-shaded in a duotone of the mood) above an action shot of the hero (lower-right) with a neon beam or explosion; localized speed lines; huge vertical onomatopoeia on one side; quest HUD top-left. Best moods: warp neon, furnace.

**C. 道具获得 Item get** — radial white/pale-blue burst behind the hero's signature object or the hero holding it, on a painted orange-flame or golden-swirl field; red katakana item title arched at top with Chinese label; dialogue subtitle bottom-left; compact HUD only. Best moods: furnace, golden vortex.

**D. 双人分屏 Co-op split screen** — vertical seam down the middle; each half shows the hero from a different angle (or, for a pair of subjects, one per side); quest HUD top-left of each half; shared dialogue in the lower third. Best moods: ruins, control room.

**E. 主菜单 Main menu** — crimson flat diagonal panel on the left 35–45% holding 3 menu pills (the selected one blue and glowing); hero on the right in a starfield/aurora or painted scene; slanted logo-style title over the hero's area; P1/P2 badges top-right; button prompts bottom-right. Best moods: red menu, aurora.

**F. 对话特写 Dialogue close-up** — over-the-shoulder: a large out-of-focus back-of-head/shoulder of a supporting character in the foreground (left 30%), hero facing camera mid-ground at 50–60% with a strong expression; control-room panels with LEDs behind; dialogue subtitle centred bottom; compact HUD only. Best moods: control room, red menu.

### Interface depth and background restraint

- Default to 4–5 panels in an asymmetric L, staggered zigzag or counter-corner layout. Use a clear size hierarchy such as 1 large + 1 medium + 3 small, with different aspect ratios and 5–20% overlap at selected edges. Avoid equal tiles, rigid columns and uniformly separated cards.
- Functional panels serve the subject: an action gauge, map, object readout or mission status, not arbitrary decoration. Compact labels and diagrams need not add more narrative text blocks.
- Keep the hero unboxed and dominant, with face and defining action unobscured. Some panel edges can overlap the hero silhouette; a small prop may pass behind an edge. Use scale and occlusion for depth before adding foreground scenery.
- Keep the background low contrast and low detail. Avoid dense stars, detailed planets, crowds, layered machinery, rubble, dust sprays and oversized foreground consoles by default. These may be used selectively if central to the user’s subject, never all together. Fine film grain must not become visible dirt or speckle clutter.
- If the result is busy, simplify the background and FX first while retaining the useful window hierarchy. If flat, improve panel size differences, overlap and feature crops before adding objects.
- Adapt to each image: a pet may use paw/ear details and a route map; an object may use a material detail and a function readout. Do not automatically add a football field, shoe crop or charge gauge to every subject. The space setting is the default backdrop, but the panels and props still come from the subject.

### Inset frame, black surround and controlled fisheye

- Default surround: uniform opaque black (#000000) outside the inner scene frame. No cream mat, coloured wallpaper, stars, noise, gradients or scenery outside it. Only selected foreground overflow elements and a very restrained edge light may interrupt the black. Keep visible black space around those elements.
- **Shared size reference for every frame:** open and attach `assets/frame-size-reference.png` as a geometry-only reference. The following measurements are approximate visual targets from that image, not pixel-perfect tracing. Match the frame footprint, black surround and border weight; adapt panel positions to the subject, and do not copy the reference subject or its story.
- **Main frame:** roughly 86–88% of canvas width and 85–87% of canvas height, centered, leaving about 6–8% pure-black space on each side before foreground overflow. Do not enlarge it into a nearly edge-to-edge frame with only a 1–3% black strip. Use a gently bowed rounded rectangle; corner radius roughly 3–5% of the shorter canvas dimension. The cream/navy double-line border assembly is about 1.2–1.8% of the shorter canvas dimension, with each cream stroke about 0.3–0.5% and narrow navy separation. This is a graphic border, not a thick monitor housing.
- **Functional HUD layout:** use compact mission, status, map or button elements in up to three corners. Keep them subordinate to the hero and never crop or enlarge a body detail inside a separate window.
- **Prompt and final check:** state the main-frame footprint and black margins explicitly in the generation prompt. Compare the final image with the bundled size reference, checking visible unobstructed portions of the frame; foreground overflow must not be mistaken for reduced black margins.
- Make 2–4 meaningful frame breaks across at least two sides, with unequal sizes: one major subject extension plus smaller relevant features such as a hand, fish tail/head, hair tips, leaf branch, prop tip or one panel corner. Choose from the subject rather than adding unrelated objects to fill a quota. For the fish-boy composition, the tail can cross left, the snout/hand right, and a smaller hair or panel edge can cross top.
- Render those extensions in front of the border: hide the border exactly behind their silhouettes, use a subtle rim or contact shadow for depth, and keep them visibly connected to the source object. No extra limbs, duplicated full subjects, detached parts or repeated fish. Let each extension travel visibly into the black margin while leaving about 2–3% outer safety space, avoiding accidental clipping.
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
| inset count | 0 (no detail-window enlargements) |
| small text set | dialogue only / dialogue + quest HUD / HUD + buttons + P1P2 / dialogue + counter |
| frame | inset scene on black with foreground overflow (default); explicit full-bleed / letterbox / split-screen overrides |

## 5. Compatibility rules

- The default inset frame wraps any archetype; its internal letterbox or split seam can coexist with the black surround. The hero is unboxed relative to UI panels and can cross the scene border.
- Archetype fixes some axes: A → letterbox + chapter title; B → onomatopoeia + speed lines/neon beam; C → item title + radial burst; D → split-screen + quest HUD; E → logo + HUD/buttons/P1P2; F → dialogue + reaction close-up or bust.
- Total text elements ≤ 5. Keep the frame uncluttered with functional HUD only.
- Reaction close-up means the hero's main composition crop, never a separate detail window; full-body pairs with A, C, D, E.
- Hero coverage beats decoration: if layers crowd the hero, drop an enrichment element before shrinking the hero.
- A group of subjects stays one hero composition — keep everyone, their left/right order and interaction; never merge or drop a person.

## 6. Preflight checklist

Before compiling the prompt, confirm:
- [ ] one hero, 55–75%, off-centre, unboxed, face uncovered
- [ ] 1–3 subdued world details; functional panels distributed across multiple quadrants
- [ ] one FX family touching the hero
- [ ] no detail-window enlargements or partial-feature inset cards
- [ ] exactly one big type device; total text 2–5; every string short and quoted
- [ ] 25–35% connected calm space; background and FX are visibly quieter than hero/UI
- [ ] 3–6 unequal panels with purposeful overlap, including 1–2 distinct partial crops
- [ ] short natural Japanese bottom dialogue unless user wording/language overrides
- [ ] uniform black surround and main-frame dimensions matching the bundled frame-size reference; 2–4 coherent frame breaks across multiple sides, outer safety margin preserved
- [ ] mild inner fisheye, stable central anatomy, legible text, flat outer canvas
- [ ] space setting with sparse stars and at most one planet or nebula band, unless the user chose another setting
- [ ] 4:3 by default; target aspect ratio respected; aspect edits preserve side content without stretching
- [ ] identity anchors (3–5 per subject) carried over; everything else redrawn in the 80s cel style
