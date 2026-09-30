# Pixel text and font rasterization

Use this reference for default pixel text, localized fonts, cross-platform font
defects, fallback detection, or accessible text modes.

## Treat font design size as a contract

Record the native pixel design size for every pixel font family and script.
Render each at that size or an exact positive integer multiple on the logical
canvas. A 12-pixel CJK font and an 8-pixel Latin font can share a UI without
pretending they have the same design grid; adapt line height and layout around
their real metrics.

For default pixel mode:

- snap the final glyph origin to whole destination logical pixels;
- allow only transforms whose basis preserves square whole pixels;
- disable smoothing and linear sampling;
- never stretch or fractionally scale a raster to make copy fit;
- measure and align using the same hardened raster that will be drawn; and
- reserve decorative faces for branding while functional prompts and actions
  use the most readable pixel face available for the script.

Centering the text box is not necessarily centering visible ink. Where visual
alignment matters, retain ink bounds or authored baselines rather than adding
one-off offsets for individual words.

## Font loading is not raster verification

`FontFace.load()`, a successful CSS font promise, or non-empty canvas pixels do
not prove that the requested face rendered. The operating system may reject a
face, substitute a fallback, or rasterize it differently from another platform.

Verify actual output:

1. Bundle and checksum the intended font bytes in the production artifact.
2. Test selection against a deliberately different fallback using metrics and
   pixel output, not only the reported CSS family.
3. Keep one or more diagnostic glyphs with known topology. A useful glyph has
   narrow internal gaps that fail visibly when raster coverage spreads.
4. Exercise every renderer with an independent font environment, including
   loading workers and native desktop wrappers.
5. Recheck newly encountered script coverage in bounded deferred work during
   play. Never send the rendered label, player name, or free text in telemetry.

On a recoverable fallback, retry once with a cache-bypassing source if the
platform supports it. Report a cooldown-protected diagnostic containing the
family, locale, text mode, screen, platform/runtime, build, and grid geometry.
Then choose the narrowest readable fallback; do not crash the voyage.

Any font replacement must invalidate glyph rasters, measured widths, ink
bounds, baselines, and font-metric caches together.

## TrueType hinting can damage a pixel font

An outline font designed on a pixel grid may still contain TrueType grid-fitting
programs or grayscale-rendering flags. DirectWrite, CoreText, FreeType, and
browser canvas implementations need not interpret them identically. At a small
native size, hinting or grayscale coverage can close a deliberate one-pixel
gap. A later binary-alpha hardening pass then turns the spread into a fully
filled shape.

When the font is intended to reproduce exact authored grid geometry and its
license permits modification, make an offline, repeatable fontTools transform
that:

- removes global hinting programs such as `fpgm`, `prep`, and `cvt `;
- removes per-glyph instructions;
- disables grayscale behavior in the `gasp` table when required;
- preserves outlines, units per em, advance widths, names, and licensing; and
- emits deterministic bytes checked into or generated for the build.

Do not strip hinting from ordinary scalable or accessibility fonts. Retain the
original font and document the transformation so an asset update cannot
silently restore the bad tables.

If a platform rasterizer still spreads coverage, render the face at an exact
integer supersample, sample the centre of each logical pixel, and harden the
result to a binary alpha mask. This works only when the outline geometry is
aligned to the corresponding subdivision. Prove it with glyph topology tests;
do not use arbitrary supersampling as a visual guess.

## Accessibility is a separate renderer contract

A high-legibility mode may intentionally use antialiasing, fractional placement,
smooth scaling, natural casing, and script-specific accessible fonts. Keep that
exception explicit and isolated. It must not weaken default pixel-mode tests,
change hit targets or painter order, introduce untranslated text, or prevent
the game canvas from filling the window.

Do not mechanically uppercase accessible prose because it replaces an all-caps
pixel face. Preserve canonical names, localized grammar, brands, acronyms, and
natural sentence casing through a mode-aware presentation policy.

Test accessible and pixel modes separately. A screenshot that looks readable in
accessible mode is not evidence that default pixel text remains snapped.
