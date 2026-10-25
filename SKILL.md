---
name: flami-orbitals-skill
description: Turn a photo or a described subject into a "轨道双子星 / Orbitals" game-screen illustration — late-1980s Japanese cel-anime characters, painted sci-fi backgrounds, faded film grain, plus the game's typography (giant white Japanese chapter titles, manga onomatopoeia, yellow dialogue subtitles, quest HUD, portrait cards) — and generate it with the built-in image tool or the OpenAI Images API. Use this whenever the user mentions 轨道双子星, Orbitals, オービタルズ, or asks for an 80s/昭和 anime, retro cel-anime, 复古赛璐璐, 老动画, or "game screenshot" style image of a person, pet, object or scene, even if they don't name the game. It enriches the composition with story elements, not just a style filter.
---

# flami-orbitals-skill — 轨道双子星 (Orbitals) image skill

All paths below are relative to the directory containing this SKILL.md (call it `SKILL_DIR`).

Make one image that looks like **a captured moment from the game *Orbitals*, starring the user's subject**. Two things must both happen:

1. **Style** — redraw the subject in the game's 80s cel-anime look, with its palette, film surface and typography.
2. **Composition** — don't just restyle the source. Build a layered game frame around the subject: chapter title or onomatopoeia, dialogue, HUD, functional overlays, FX, and new world elements that extend the subject into the game's universe.

Reference files (read both before writing a prompt):
- `references/style-guide.md` — rendering, palettes (scene moods), typography, film surface, and a ready-made English style block.
- `references/composition.md` — layer stack, scene concept, 6 layout archetypes, variation axes, preflight checklist.

## Workflow

### Accepted visual defaults

Use a clean hero composition with restrained game-interface overlays over a quiet background. Depth should come from scale, occlusion and dynamic pose, not detail-window enlargements or dense environmental detail. Keep the Orbitals cel-anime style throughout; do not use pixel art, desktop menus or signatures.

Default to a main scene frame over a uniform opaque black outer field, several purposeful foreground frame breaks, and mild fisheye/barrel curvature within the frame. Use `assets/frame-size-reference.png` as the visual size reference for the main frame border; follow the normalized measurements in `references/composition.md`. Open this image and attach it to generation as a geometry-only reference. Do not copy its boy, fish, text, palette or background into unrelated subjects. Keep the outer black field clean and the central face/anatomy stable. Explicit user framing choices override these defaults.

Default setting: outer space. Unless the user names another setting or mood, stage the subject in a space scene — open deep space, low orbit above a planet, a station exterior or viewport, or a small planet's surface under a starry sky — and translate the subject's own world into it (a kitchen becomes a galley module, a street becomes a station corridor with a window to the stars). Keep it quiet: sparse stars, one soft nebula or aurora band, or one simplified planet, never a dense starfield. Prefer the space-compatible moods (深空极光, 跃迁霓虹, 金色漩涡); other moods still work when space stays visible.

Bottom dialogue and speaker labels default to natural Japanese; keep user-supplied text verbatim and follow an explicitly requested language instead. This default applies to dialogue, not automatically to every HUD or title.

### 1. Read the request

Find:
- **Subject**: an image path / attached image, or a text description. If there is neither, ask once what the image should be about, then stop.
- **Optional user choices**: mood (红幕菜单 / 深空极光 / 遗迹森林 / 熔炉 / 金色漩涡 / 跃迁霓虹 / 控制室), layout (章节标题卡 / 角色切入 / 道具获得 / 双人分屏 / 主菜单 / 对话特写), aspect ratio, any title or dialogue text. Use whatever is given verbatim; pick the rest yourself — don't send the user a questionnaire, choosing is part of the job.

Aspect ratio: default to landscape 4:3 unless specified. Respect exact requested ratios; do not equate 1536x1024 (3:2) with 16:9, or 1024x1536 (2:3) with 3:4 or 9:16. Ask the built-in generator for the target ratio explicitly (for the default: 4:3, ideally 1536x1152). Check actual saved dimensions where available and report any mismatch. The bundled CLI's supported size options are 1536x1024, 1024x1536 and 1024x1024; none is exactly 4:3, so for the default use 1536x1024 (3:2, the closest landscape size) and say so instead of calling it 4:3.

When changing an existing 16:9 image to 4:3 while retaining all content, expand above and below and reflow panels instead of cropping sides or stretching the subject. Retain subject identity, palette and exact text. A ratio the user requests for one image applies to that image only; later images go back to the 4:3 default.

### 2. Anchor the subject

If there is a source image, look at it once and note **3–5 identity anchors per subject**: hair shape and colour, glasses/accessories, signature clothing colour, body type, pose or relationship between subjects. These anchors are what make it recognisable; everything else is redrawn in the 80s cel style (proportions, line, shading, background). For several people, list each one with their anchors and left/right order so nobody gets merged or dropped.

### 3. Build the scene concept and recipe

Follow `composition.md` §2–§5:
- Invent the mini-story: chapter title (JP + CN), mission HUD, one short Japanese dialogue line, and 1–3 restrained subject-specific world details. Functional interface panels may carry additional story details.
- Pick one value per variation axis. Fit the archetype to the subject (a dramatic pet → cut-in; an object → item-get; two people → split-screen; a portrait → main-menu or dialogue). If you already made images in this conversation, change at least two high-impact axes so outputs don't repeat.
- Run the preflight checklist.

For the default composition, use one dominant hero with a small number of functional HUD elements. Specify positions only for functional interface elements and calm background regions using composition.md.

### 4. Choose reference images

**Never open, view or preview the images in `assets/style-refs/` yourself.** Handle them by file path only. (The one bundled image you do open is `assets/frame-size-reference.png`, for frame geometry.) The look is fully described in `style-guide.md`, so you don't need to see them, and viewing them clutters the user's screen with image previews they did not ask for.

Style refs are used only by the bundled script (Option B in step 6), which reads them from disk. It passes images to the API in order: put the **subject photo first** (if any), then 2–3 style refs matching the archetype:

| Archetype | Style refs |
|---|---|
| A chapter card | 05-title-card, 01-characters, 03-space-mecha |
| B cut-in | 06-cut-in, 02-onomatopoeia, 01-characters |
| C item get | 04-item-burst, 01-characters, 03-space-mecha |
| D split screen | 07-hud-splitscreen, 01-characters, 02-onomatopoeia |
| E main menu | 08-red-menu, 01-characters, 05-title-card |
| F dialogue | 01-characters, 02-onomatopoeia, 03-space-mecha |

With the built-in image tool (Option A), skip this step: send no style refs and rely on the style block.

In both options, add `assets/frame-size-reference.png` as the last image and name its role in the prompt ("the last image is a geometry-only reference for the main frame footprint and border; do not copy its subject, text or colours").

Don't tell the user which refs you picked or which files you read — just proceed to the result.

### 5. Write the prompt

Write it in English (image models follow English best), with all on-image text as exact quoted CJK strings. Save it to a file and keep this structure:

```
[Image roles]
Image 1 is the subject to redraw (identity reference only — do not keep its photographic look, lighting or background). Images 2–4 are style references from the game "Orbitals": match their rendering, colour, typography and film texture; do not copy their characters or text.
(Text-only subject: "All images are style references ..." )
(No style refs sent, as with the built-in tool: keep only the sentence about Image 1, or drop this section for a text-only subject.)

[Subject]
<hero: who/what, identity anchors per subject, pose/expression, crop, placement, coverage %>

[Scene & layout]
<archetype layout in concrete positions: what is top-left, centre band, lower third, right edge; frame type (letterbox / split / full-bleed); mood palette with hex colours; calm space>

[Frame & depth]
<uniform opaque black outer field; main frame and border sized to assets/frame-size-reference.png using composition.md measurements; 2–4 subject-relevant features crossing the frame across at least two sides; frame occluded behind them; mild inner-scene fisheye with stable central anatomy and readable text>

[Enrichment & FX]
<1–3 quiet world details; one localized FX family; functional HUD elements only; specify clean negative space and what stays visually subdued>

[Typography]
<each text element: exact string in quotes, position, look from style-guide §3>

[Style]
<paste the style block from style-guide §5>

[Avoid]
photorealism, 3D render look, modern flat vector, glossy digital painting, black outlines everywhere, extra or garbled text beyond the listed strings, watermarks, duplicated hero, merged or missing people, extra fingers.
```

Be concrete about positions and sizes — "giant white title spanning 80% of the width across the middle third, crossing in front of the hero's torso" beats "a big title".

### 6. Generate

Save the prompt and the result under `./orbitals-art/` in the current working directory, with a slug like `cat-cut-in`. Make one image per request unless the user asks for more — generation is slow and costs money.

**Option A — built-in image generation (preferred when available, e.g. Codex).** If the environment gives you an image-generation or image-editing tool, use it directly: send the compiled prompt, plus the user's subject photo if there is one and the tool accepts input images. Also attach `SKILL_DIR/assets/frame-size-reference.png` as the geometry reference. Do not open or attach the style refs — the style block carries the look. Use the tool's closest size to the chosen aspect ratio, then save or copy the result to `./orbitals-art/<slug>.png`.

**Option B — bundled script (when there is no built-in tool).** It calls the OpenAI Images API with only the Python standard library:

```bash
python3 SKILL_DIR/scripts/generate.py --prompt-file ./orbitals-art/<slug>.txt \
  --ref <subject.jpg> --ref SKILL_DIR/assets/style-refs/<a>.jpg --ref SKILL_DIR/assets/style-refs/<b>.jpg \
  --size 1536x1024 --out ./orbitals-art/<slug>.png
```

- Needs `OPENAI_API_KEY`. If it's missing, tell the user how to set it (`export OPENAI_API_KEY=...` in their shell profile), give them the prompt file path, and stop — don't try to work around it.
- `OPENAI_IMAGE_MODEL` overrides the default model (`gpt-image-1`); `OPENAI_BASE_URL` points at a compatible proxy.
- `--dry-run` prints the request without calling the API.

### 7. Check and deliver

Open the result and compare it with the preflight checklist: is the hero recognisable through its anchors, is it clearly 80s cel anime (not a filtered photo), are functional HUD elements readable, is the scene set in space (unless the user chose another setting), is the background calm rather than filled with stars/debris/architecture, is the image 4:3 (unless another ratio was requested), is the text legible, is the bottom dialogue Japanese unless the user requested otherwise, is the outer field uniformly black, do foreground features coherently occlude the main frame border, and is inner fisheye curvature mild with readable text and coherent anatomy?

Then reply briefly (in the user's language) with:
- the image path, and the image itself,
- one line on the scene concept (chapter / mission / layout / mood) so the user knows what was intended,
- any visible flaw worth fixing (e.g. garbled text, a missing element), with an offer to regenerate with a tweak.

Leave out process notes: no mention of the style refs, reference files or steps you went through.

Don't regenerate automatically. Image models often garble CJK text, so if the text came out wrong, suggest shortening it or dropping a text element rather than retrying the same prompt.
