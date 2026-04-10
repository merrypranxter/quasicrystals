# AI Art Prompt Templates for Quasicrystal Tilings

Comprehensive prompt templates for generating quasicrystal-inspired artwork using
Midjourney, Stable Diffusion, DALL-E, and other AI image generation systems.

---

## How to Use These Templates

Each tiling system has a set of modular prompt components. Combine a **Base Prompt**
with one or more **Style Modifiers**, a **Lighting Option**, a **Color Scheme**, and
append **Quality Tags**. Always add the **Negative Prompt** as a negative weight or
negative prompt field.

Format for Midjourney:  `/imagine [base] [style] [lighting] [color] [quality] --ar [ratio] --v 6 --s [stylize]`
Format for Stable Diffusion: Use positive prompt + negative prompt field separately.

---

## 1. Penrose P2 — Golden Rhombus Field

### Base Prompts
- `penrose tiling pattern, golden rhombus quasicrystal, five-fold symmetry, mathematical art, aperiodic tessellation`
- `infinite golden rhombus mosaic, Penrose P2, no repeating pattern, quasiperiodic geometry`
- `photorealistic quasicrystal surface, golden thick and thin rhombi, hierarchical self-similar structure`

### Style Modifiers
- `architectural floor mosaic, Byzantine gold mosaic, ancient temple geometry`
- `glowing neon wireframe, mathematical diagram, blueprint aesthetic`
- `watercolor wash, artistic rendering, painterly brushstrokes over geometric lattice`
- `3D rendered bas-relief, metallic gold tiles, studio lighting, product visualization`
- `Islamic geometric art, Girih tiles, arabesques, intricate ornament`
- `minimal line art, pen and ink, white lines on black, mathematical poster`
- `stained glass window, cathedral light, translucent colored panels`
- `engraved brass plate, antique mathematical instrument, technical illustration`

### Lighting Options
- `dramatic raking light, long shadows, late afternoon sun, golden hour`
- `even soft diffuse light, scientific diagram clarity, flat lighting`
- `backlit translucent tiles, glowing edges, luminescent, bioluminescent`
- `spotlight from above, deep shadows between tiles, chiaroscuro`
- `multiple light sources, color gels, rgb lighting, psychedelic illumination`
- `moonlight silver, cold blue highlights, nocturnal atmosphere`

### Color Scheme Options
- `deep gold #B8860B, bright gold #FFD700, bronze #CD7F32, dark background #1C1008`
- `warm ivory palette, aged parchment #F5F0DC, sepia tones, antique book aesthetic`
- `monochrome silver, platinum highlights, graphite shadows, on jet black`
- `rainbow iridescent, each tile a different hue of spectrum, prismatic`
- `holographic foil effect, shifting colors, metallic luster`

### Aspect Ratios
- `--ar 1:1` — square, ideal for social media, symmetric display
- `--ar 16:9` — widescreen, ideal for wallpaper, panoramic
- `--ar 3:2` — classic photo ratio, prints well
- `--ar 9:16` — portrait/phone wallpaper
- `--ar 2:3` — tall portrait, poster format

### Quality / Detail Settings (Midjourney)
- `--v 6 --q 2 --s 750` — maximum quality, high stylization
- `--v 6 --s 250` — clean, less stylized
- `--v 6 --chaos 10` — slight variation while maintaining geometry
- `--niji 6` — anime/illustrated style if appropriate

### Quality / Detail Settings (Stable Diffusion)
- Sampler: `DPM++ 2M Karras`, Steps: `40`, CFG: `7`
- Model: `SDXL 1.0` with detail refiner
- ControlNet: Use scribble/depth from actual Penrose rendering for structure

### Negative Prompts
- `periodic tiling, square grid, hexagonal grid, regular pattern, repeating unit cell, wallpaper pattern, blurry, low detail, distorted geometry, imperfect symmetry, text, watermark, signature`

### Example Seed Variations
- Seed 42: tends to emphasize star formations
- Seed 137: creates more dart-dominated compositions
- Seed 2024: balanced sun/star distribution
- Seed 31415: golden center with receding hierarchy

---

## 2. Penrose P3 — Kite-Dart Mosaic

### Base Prompts
- `Penrose kite and dart tiling, five-fold quasicrystal pattern, mathematical mosaic`
- `aperiodic kite-dart tessellation, blue kites and red darts, star and sun configurations`
- `infinite non-repeating kite dart pattern, Penrose P3, five-fold symmetry`

### Style Modifiers
- `medieval heraldic pattern, shield decoration, coat of arms background`
- `game board surface texture, strategy game tiles, fantasy map pattern`
- `Japanese kamon-inspired, family crest geometry, circular composition`
- `Art Deco inlay floor, marble mosaic, luxury hotel lobby`
- `deep sea creature scales, fish scale armor, organic biological texture`
- `circuit board trace pattern, PCB design, electronic component aesthetic`
- `origami paper fold marks, crisp paper texture, geometric paper art`

### Lighting Options
- `flat 2D illustration, no shadows, clean vector graphic look`
- `soft ambient occlusion, slight depth between tiles, 3D relief`
- `emissive tiles glowing from within, dark surround, sci-fi aesthetic`
- `photographic overhead shot, slight perspective, real floor texture`

### Color Scheme Options
- `royal blue kites #4169E1, crimson darts #DC143C, white edges, black background`
- `emerald and gold, #50C878 kites, #FFD700 darts, jewel tone luxury`
- `pastels, soft lavender and pale yellow, gentle nursery aesthetic`
- `high contrast black and white, no intermediate greys, stark mathematical`
- `dual tone ombre, each tile type has gradient from center`

### Negative Prompts
- `periodic pattern, square grid, hexagonal tiling, randomly placed shapes, incorrect matching, gaps between tiles, overlapping tiles, blurry, low quality`

---

## 3. Ammann-Beenker — Silver Octagram Grid

### Base Prompts
- `Ammann-Beenker tiling, 8-fold octagonal quasicrystal, squares and rhombi, aperiodic`
- `octagonal quasiperiodic mosaic, 8-pointed star formations, silver metallic geometric`
- `silver mathematical grid, 8-fold symmetry, non-repeating pattern, precision geometry`

### Style Modifiers
- `aerospace engineering blueprint, technical diagram, drafting aesthetic`
- `Islamic octagonal geometric ornament, 8-fold arabesque, marble inlay`
- `anodized aluminum surface, brushed metal texture, machined precision`
- `sci-fi spacecraft hull plating, advanced material, futuristic design`
- `crystallographic diffraction diagram, scientific visualization, x-ray pattern`
- `modernist architecture surface, Zaha Hadid aesthetic, parametric design`
- `holographic security foil, iridescent metallic, anti-counterfeiting pattern`

### Lighting Options
- `studio photography lighting, specular highlights on metal, reflective surfaces`
- `cool blue LED backlighting, technical laboratory aesthetic`
- `dramatic contrast, dark grey shadows, bright metallic highlights`
- `iridescent oil-slick rainbow, angle-dependent color shift`

### Color Scheme Options
- `steel blue #4682B4, silver #E8E8E8, slate grey #708090, deep navy #0A1045`
- `all silver monochrome, varying brightness/contrast, metallic texture only`
- `cobalt and chrome, electric blue highlights on polished steel`
- `thermal map coloring, blue cold to red hot, temperature visualization`

### Negative Prompts
- `warm colors, organic shapes, curved lines, irregular edges, 5-fold symmetry, periodic pattern, blurry`

---

## 4. Stampfli — Dodecagonal Shield

### Base Prompts
- `Stampfli tiling, 12-fold dodecagonal quasicrystal, triangles squares rhombi, mandala-like`
- `dodecagonal quasiperiodic pattern, 12-pointed star rosettes, intricate geometric`
- `12-fold symmetry aperiodic tiling, snowflake-like structure, recursive geometric`

### Style Modifiers
- `Gothic cathedral rose window, stained glass, divine geometric light`
- `Celtic knotwork geometry, interlaced patterns, illuminated manuscript border`
- `mandala meditation art, sacred geometry, spiritual pattern, gold on dark`
- `snowflake crystallography, ice crystal photograph, winter nature`
- `medieval Islamic tilework, Moroccan zellige, intricate ceramic mosaic`
- `psychedelic fractal art, neon colors, trippy geometry, poster art`
- `scientific electron microscopy, black and white TEM image, material science`

### Lighting Options
- `transmitted light, backlit like stained glass, glowing colors`
- `overhead flat illumination, scientific clarity, equal lighting`
- `spotlit center, radial illumination gradient, theatrical`
- `bioluminescent glow, deep ocean dark, living crystal aesthetic`

### Color Scheme Options
- `forest green #228B22, lime #90EE90, chartreuse #ADFF2F, dark green #021002`
- `white and gold on midnight blue, celestial calendar aesthetic`
- `jewel tones, ruby, sapphire, emerald, amethyst, on black`
- `monochrome forest, all greens from dark to light`
- `winter white, ice blue, on deep blue-black, snowflake aesthetic`

### Negative Prompts
- `5-fold symmetry, 8-fold symmetry, periodic grid, square repetition, blurry, warm colors unless specified`

---

## 5. Trilobite-Sphinx — Organic Aperiodic Mosaic

### Base Prompts
- `trilobite sphinx tiling, organic aperiodic mosaic, fossil-like interlocking shapes`
- `biological aperiodic tessellation, trilobite shapes, ancient creature pattern`
- `non-repeating organic shapes, fossil mosaic, paleontological aesthetic`

### Style Modifiers
- `paleontological field guide illustration, technical biological drawing`
- `fossilized coral cross-section, geological thin section, microscopy`
- `ancient temple floor mosaic, archaeological site, ancient civilization`
- `leather texture, embossed reptile scale pattern, luxury material`
- `carved stone relief, ancient bas-relief sculpture, museum artifact`
- `biological tissue cross-section, cellular architecture, microscope slide`
- `ceramic relief tile, handmade pottery decoration, artisanal craft`

### Lighting Options
- `raking sidelight, emphasizing texture and relief, museum display lighting`
- `overhead diffuse, archaeological documentation photograph`
- `golden afternoon sun, warm texture, Mediterranean heat aesthetic`
- `cool blue laboratory light, scientific specimen`

### Color Scheme Options
- `earthy ochre #8B4513, sand #DEB887, tomato accent #FF6347, dark earth #1A0800`
- `fossilized bone, limestone grey, calcite white, on slate black`
- `terracotta and cream, Roman mosaic palette, ancient`
- `verdigris bronze, aged green-blue on brown, patinated metal`

### Negative Prompts
- `regular geometric shapes, crystalline pattern, sharp angles, bright saturated colors, modern aesthetic, blurry`

---

## 6. Pinwheel — Infinite Rotation Field

### Base Prompts
- `pinwheel tiling, infinite rotation right triangles, statistically isotropic aperiodic`
- `Conway-Radin pinwheel, spiraling triangle tessellation, no preferred direction`
- `vortex of right triangles, infinite rotation tiling, mathematical spiral`

### Style Modifiers
- `kinetic art sculpture photograph, motion blur, dynamic rotation`
- `hypnotic optical illusion, op art, Bridget Riley style`
- `particle physics detector visualization, bubble chamber tracks`
- `time-lapse star trail photography, circular rotation, long exposure`
- `DJ turntable record abstract, music visualization, rotating disc`
- `hurricane satellite view, spiral weather system, meteorological`
- `quantum field visualization, Feynman diagram aesthetic, physics art`

### Lighting Options
- `spinning neon lights, long exposure photography, light painting`
- `glowing particle trails, each triangle a different emission spectrum`
- `stroboscopic freeze-frame, multiple exposure, kinetic`
- `computer screen glow, screen recording aesthetic, technical`

### Color Scheme Options
- `hot pink #FF1493, electric cyan #00FFFF, on deep black #0A000F`
- `full rainbow spectrum mapped to rotation angle, continuous color wheel`
- `monochrome with motion-blur gradient, black to white rotation`
- `thermal imaging palette, red hot center, blue cool edges`
- `neon acid colors, rave aesthetic, psychedelic`

### Negative Prompts
- `preferred direction, straight parallel lines, square grid, static pattern, non-rotating, blurry, low energy`

---

## 7. Robinson — Hierarchical Square Nesting

### Base Prompts
- `Robinson tiling, hierarchical nested squares, aperiodic notched tiles`
- `Robinson aperiodic tiling, square fractal hierarchy, mathematical tessellation`
- `notched square tiles, hierarchical aperiodic pattern, mathematical minimalism`

### Style Modifiers
- `mathematical textbook illustration, clean line art, educational diagram`
- `Russian constructivism, Soviet poster art geometry, bold graphic`
- `Mondrian-inspired grid, de Stijl movement, primary colors geometric`
- `laser-engraved wood pattern, CNC router art, maker aesthetic`
- `architectural axonometric diagram, floor plan, technical drawing`
- `retro computer graphics, 8-bit aesthetic, pixel art geometry`
- `Japanese Asanoha or geometric pattern, traditional craft geometric`

### Lighting Options
- `flat diagram style, no lighting, pure 2D line/fill`
- `subtle drop shadow, slight depth, clean infographic aesthetic`
- `etched metal, laser engraved, industrial material texture`
- `chalk on blackboard, educational, academic`

### Color Scheme Options
- `dark charcoal #2F4F4F, medium grey #696969, light #A9A9A9, near-black #050505`
- `Mondrian primary: red, yellow, blue rectangles, black grid lines`
- `aged paper and ink, sepia and dark brown, manuscript aesthetic`
- `neon green on black, terminal/hacker aesthetic, tech`
- `white on black only, maximum contrast, mathematical precision`

### Negative Prompts
- `irregular shapes, curved lines, organic texture, 5-fold symmetry, non-square, blurry, colorful unless specified`

---

## Universal Quality Tags

Append these to any prompt for best results:

### Midjourney Universal Quality Suffix
`ultra detailed, 8k resolution, masterpiece, sharp focus, professional photography, award winning, trending on ArtStation --v 6 --q 2 --s 500`

### Stable Diffusion Universal Quality Tags
Positive: `masterpiece, best quality, ultra detailed, 8k UHD, sharp focus, professional`
Negative: `low quality, bad anatomy, blurry, pixelated, jpeg artifacts, text, watermark, signature, cropped, worst quality, normal quality`

### ControlNet Guidance
For structural accuracy, generate a base Penrose/quasicrystal image programmatically
(using the provided Python renderers), then use it as ControlNet input with:
- Scribble preprocessor: preserves edge geometry
- Depth preprocessor: adds 3D interpretation
- Reference: style transfer from reference image
