---
name: develop-pixel-art-games
description: Design, implement, audit, and test a pixel-art game's rendering pipeline, logical pixel grid, asset scaling, camera composition, effects, UI, and fonts. Use when crisp pixel presentation must survive responsive windows, localization, browsers, native desktop runtimes, and multiple operating systems; do not use for ordinary non-pixel art direction or marketing copy.
---

# Develop Pixel Art Games

Treat pixel art as a rendering contract, not a texture-filter checkbox. Establish
which coordinate system owns a pixel, then keep assets, text, transforms,
effects, screenshots, and runtime verification consistent with that contract.

This skill does not authorize generated art or public marketing work. Preserve
the repository's human-authorship and external-action policies.

## Route the task

- Read [references/rendering-pipeline.md](references/rendering-pipeline.md) when
  designing or debugging the logical canvas, cameras, sprites, shaders,
  particles, UI layout, display scaling, or mixels.
- Read [references/pixel-text.md](references/pixel-text.md) for pixel fonts,
  cross-platform raster differences, font fallback, localization, or an
  accessible high-legibility mode.
- Read [references/verification.md](references/verification.md) when adding
  tests, auditing a build, investigating a platform-only defect, or preparing a
  release.

Read only the references relevant to the current request.

## Core workflow

1. Inventory every visible surface and transform: source asset, atlas, logical
   canvas, camera, intermediate render target, shader, UI layer, screenshot,
   and final display presentation. Do not assume they share a grid.
2. State the intended logical pixel size and which layer owns snapping. Keep
   continuous simulation state separate from snapped presentation state.
3. Trace a representative sprite and label from source bytes to screen. Check
   sampling, scale, origin, transform basis, fallback behavior, and cache
   invalidation at every boundary.
4. Fix the earliest violated invariant. Do not hide a bad transform with blur,
   extra outlines, per-asset nudges, or a global scale that damages other
   surfaces.
5. Add a regression test for the class of failure, then exercise representative
   window sizes, languages, text modes, and native target platforms.

## Non-negotiable distinctions

- Logical game pixels and physical monitor pixels are different domains. A
  game may continuously scale its finished canvas to fill a window while all
  internal art and text remain perfectly snapped to the logical grid. Do not
  impose letterboxing or physical-pixel integer scaling unless the product
  explicitly chooses it.
- “No mixels” means one coherent implied pixel density within a composed visual
  layer. It does not forbid deliberately higher-resolution accessibility text,
  separate UI surfaces, or source art at other resolutions when each boundary
  is explicit and composited intentionally.
- Responsive layout changes geometry, available logical viewport, columns,
  wrapping, or padding. It must not silently fractionally scale pixel text or
  sprites to make content fit.
- Development, tests, and captures should fail loudly when the pixel contract
  is violated. A production game should report a bounded diagnostic and use a
  narrow visual fallback rather than crash or corrupt player state.

## Completion evidence

Report the logical grid and presentation policy, the broken boundary and root
cause, changed files, automated checks, runtime/platform checks, and any
remaining untested target. Do not claim a Windows font defect is fixed from a
macOS browser capture alone.
