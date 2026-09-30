# Pixel-art verification and release checks

Use this reference when adding tests, auditing an implementation, diagnosing a
platform-only defect, or preparing a build.

## Automated contract tests

Choose tests that fail for the violated rendering contract, not tests that only
match one screenshot. Depending on the stack, cover:

- every pixel-font size is a positive integer multiple of that family's native
  design size;
- final text and sprite origins land on whole logical destination pixels after
  transforms;
- pixel transforms reject shear, non-uniform stretch, and fractional basis
  vectors;
- pixel-art canvas contexts disable smoothing;
- WebGL pixel textures use nearest minification and magnification;
- no presentation-layer blur or linear filter reaches pixel mode;
- sprites and atlases reject non-integer runtime scale;
- pixel-preserving screenshots use one equal integer scale on both axes;
- font packages contain the expected bytes, licenses, glyph coverage, and—for
  intentionally unhinted pixel faces—no hinting programs or grayscale flag;
- an injected fallback is detected even though it draws non-empty glyphs;
- a known diagnostic glyph retains its internal gaps and authored topology;
- switching fonts or languages clears every related raster and metric cache;
- accessibility exceptions cannot make default pixel-mode tests pass; and
- workers, loading screens, cached canvases, screenshots, and native wrappers
  obey the same relevant contract as the main renderer.

Use visual or pixel-buffer goldens for a few diagnostic assets and glyphs, not
for every label. Topology assertions—connected components, protected gaps,
binary alpha, expected opaque coordinates—often survive harmless color or copy
changes better than full screenshots.

## Runtime matrix

Exercise representative combinations rather than one developer browser:

- every shipping native runtime and target operating system;
- the browser build where applicable;
- common wide, narrow, portrait, high-DPI, and unusual aspect ratios;
- default and accessible text modes;
- every supported script family, including representative CJK and Cyrillic;
- loading/startup, ordinary gameplay, modal UI, and exported screenshots; and
- font-load failure, missing glyph, cache invalidation, and device/context reset.

Chrome on macOS cannot certify Electron on Windows. Platform font rasterizers,
GPU texture paths, packaging, and sandbox behavior differ. Cross-building is
useful, but keep at least one target-native smoke or CI job for presentation
defects that have escaped browser tests.

## Diagnose from pixels back to source

For a distorted asset or glyph:

1. Capture the final pixel buffer and relevant transform, not only a phone
   photograph of the physical monitor.
2. Compare source bytes and packaged bytes.
3. Inspect the first intermediate surface where the topology changes.
4. Check sampler state, destination rectangle, transform matrix, font selection,
   and cache age at that boundary.
5. Reproduce with the smallest diagnostic sprite or glyph that contains the
   vulnerable one-pixel feature.

Do not blame a screenshot compression artifact until the game framebuffer is
known good. Conversely, do not change the renderer to compensate for scaling
performed only by a chat client or image viewer.

## Release behavior

Development builds, automated captures, and CI should fail on pixel-grid and
default-font violations. Production should preserve the last valid visual,
clip or omit the narrow failing widget when safe, and emit a bounded diagnostic
instead of terminating the player's session.

Before release, report:

- the logical grid and final display policy;
- validated font families and packaged hashes;
- tested runtimes, operating systems, languages, and window classes;
- tests or diagnostic glyphs that prove the original failure is absent; and
- any target that was only cross-built rather than run natively.
