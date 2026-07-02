# AtlasSplitter
 
A fast, fully client-side tool for slicing a texture atlas into individual tiles and exporting them. Everything runs locally in your browser — your images are never uploaded anywhere, and there are no external dependencies.
 
Open `atlas-splitter.html` in any modern browser. That's it.
 
## Features
 
- **Any input resolution** — 1K, 2K, 4K, 8K, or anything else (PNG, JPG, WebP).
- **Arbitrary grid** — split into any columns × rows (2×2, 4×4, 8×8, 4×2, …), with quick presets and a live grid overlay preview.
- **Output size control** — keep native tile size, snap to a power-of-two (128–4096), or set a custom size. Smooth or nearest-neighbour resampling.
- **Color space** — passthrough (exact pixels), sRGB ↔ Linear conversion for game-texture workflows, or a custom gamma.
- **Custom naming** — set a base name and choose a naming scheme (`base_r0_c0`, sequential `base_0`, or `base_c0_r0`) with automatic zero-padding.
- **Export** — download tiles individually, or grab them all as a ZIP (built in-page, no library).
- **Flipbook GIF** — render the tiles as an animated GIF at a selectable frame rate (1–60 fps).
## Notes
 
- The ZIP and GIF encoders are written from scratch in vanilla JavaScript, so the tool has zero runtime dependencies and works offline.
- GIF frame timing is quantized to 1/100s, so very high frame rates round down slightly (≈50 fps effective at 60 fps).
- Linear conversion is applied to 8-bit output; for true HDR/linear pipelines use a 16-bit format.
## Tech
 
Single self-contained HTML file — vanilla JS, Canvas API, no build step, no dependencies. Styled with the CommitMono typeface.
