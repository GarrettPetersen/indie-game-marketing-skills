# Pixel-art rendering pipeline

Use this reference for logical grids, assets, cameras, effects, UI composition,
display scaling, or mixels.

## Define the pixel contract

Record:

- the base logical resolution or formula for a responsive logical viewport;
- the world-units-to-logical-pixels relationship;
- which surfaces are pixel art and which are intentionally smooth;
- which stage snaps positions and dimensions;
- the allowed sprite scales and rotations; and
- how the finished logical image is presented to the physical window.

Keep one authoritative transform for each boundary. A sprite should not be
rounded in world logic, rounded differently by a camera, and nudged again by a
widget. Preserve continuous physics and interpolation when gameplay needs them;
snap the composed render position at the explicit pixel-art boundary.

## Avoid mixels

A mixel is a pixel or edge whose apparent size conflicts with the pixel density
of the surrounding composed layer. Common causes include:

- importing one sprite at a non-integer scale;
- combining assets authored for different base grids without an offline
  conversion;
- fractional camera translation or zoom;
- rotating a sprite through arbitrary angles with a smooth sampler;
- drawing one-pixel outlines before scaling some objects and after scaling
  others;
- rendering particles, shadows, masks, or post-processing at display
  resolution over a low-resolution scene; and
- scaling UI labels independently to make a panel fit.

Inspect silhouette steps and line widths, not only image dimensions. A large
asset can belong to the same grid if its authored pixels map to the same logical
pixel blocks. An intentionally separate high-resolution layer is not a mixel if
its separation is a product decision and its composition is stable.

Convert mismatched source art once, offline, with nearest-neighbor resampling or
redrawing. Keep the original and generated artifact distinct and make the
conversion reproducible. Do not repeatedly resize a runtime source through
several intermediate canvases.

## Sampling and transforms

- Use nearest-neighbor minification and magnification for pixel-art textures.
- Disable canvas image smoothing at every context that draws pixel surfaces;
  settings do not reliably propagate to new or reset contexts.
- Keep pixel-art transform basis vectors square and whole-numbered. Reflections
  and quarter turns can preserve the grid; shear, non-uniform stretch, and
  fractional scale do not.
- Snap the destination-space origin after applying the camera or parent
  transform. Snapping only the local source position is insufficient.
- Prefer authored or pre-rendered directional frames for arbitrary rotations.
  If runtime rotation is required, rasterize once onto the logical target and
  accept it as a deliberate style choice rather than pretending it preserves
  the source grid.
- Quantize visual motion at the composition boundary, not elapsed time or game
  state. Frame-rate changes must not change travel, turning, or animation speed.

## Effects and particles

Build effects on the logical grid unless they belong to an explicitly smooth
layer. Use integer logical-pixel offsets, low-resolution masks, hard-edged alpha,
and nearest texture filters. CSS blur, display-resolution glow, fractional UV
scrolling, and linear filtering can reintroduce a second pixel density.

When particles represent pieces of a sprite—leaves, blossoms, sparks, chips—
sample their origins from qualifying opaque or feature-coloured source pixels.
Do not spawn uniformly from the sprite's bounding box and then cover the error
with random offsets.

Palette swaps should preserve alpha and source-grid membership. Seasonal or
damage variants derived from an asset should keep the same footprint, pivot,
shadow contract, and atlas metadata unless the visible silhouette intentionally
changes.

## Responsive windows and the physical display

Keep internal pixel integrity separate from final window coverage. The logical
canvas may be continuously scaled to fill the available window, including
fractional CSS scale, when that is the product's chosen presentation. Use the
platform's pixelated/nearest presentation path and center the result; do not
distort the aspect ratio.

Do not “fix” internal text or sprite mixels by forcing the whole application to
an integer physical-monitor scale. That can create unnecessary letterboxing,
waste space on unusual aspect ratios, and confuse CSS pixels with game pixels.

For responsive UI, change the logical viewport or layout: reduce padding,
reflow columns, shorten optional copy, paginate deliberately, or reserve only
the space actually used. Never shrink an individual pixel widget by a
fractional factor to avoid scrolling.

## Screenshots and intermediate surfaces

Exports intended to preserve pixel structure should use one equal positive
integer scale on both axes and nearest-neighbor sampling. Verify the requested
dimensions are an exact multiple of the logical source; do not stretch the last
row or column.

Loading screens, workers, cached layers, minimaps, offscreen canvases, WebGL
framebuffers, and native wrappers are separate renderers. Audit their filtering
and grid contracts rather than assuming the main scene's settings cover them.
