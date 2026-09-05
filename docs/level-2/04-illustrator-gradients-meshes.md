# 04 · Illustrator Gradients, Meshes & Effects

Flat fills only go so far. This module covers **gradients** for smooth
multi-color transitions on fills and strokes, the **Gradient Mesh** tool
for shading that follows a curved 3D-like surface rather than a straight
line or radius, and the **Appearance panel**, which stacks multiple
fills/strokes and live effects on a single object non-destructively.

## 1. Gradient fills and strokes

1. Select an object, then open **Window > Gradient** (**⌘/Ctrl+F9**). Click
   the gradient swatch in the panel to apply the default black-to-white
   linear gradient as the object's fill.
2. Double-click a **color stop** beneath the gradient ramp to open a color
   picker and change that stop's color; drag a stop left/right to shift
   where its color falls; click anywhere below the ramp to add a new stop,
   or drag an existing stop away from the ramp to delete it.
3. Drag the diamond-shaped **midpoint marker** above the ramp (between two
   stops) to shift where the 50/50 blend between them falls, biasing the
   transition toward one color or the other.
4. The **Type** dropdown offers **Linear** (a straight-line transition),
   **Radial** (transitions outward from a center point), and **Freeform**
   (place individual color points anywhere on the shape and Illustrator
   blends between them, useful for organic, non-linear color washes).
5. With the **Gradient tool** (**G**) selected, drag directly across the
   object on the canvas to set the gradient's angle and length live — for a
   Radial gradient, this sets the center and radius instead.
6. Gradients apply to a **stroke** the same way — select the stroke swatch
   (not fill) in the Gradient panel first. Three additional stroke-gradient
   options appear next to the stroke weight: gradient **within** the stroke
   line, gradient **along** the stroke's length, or gradient **across** the
   stroke from one side to the other.

## 2. Gradient Mesh

A regular gradient only transitions along a line or from a center point. A
**mesh** lets color vary across a grid of points laid over the object's
surface, which is what makes convincing curved/rounded shading (a sphere, a
folded ribbon, a glossy product render) possible in a vector object.

1. Select a filled object and choose **Object > Create Gradient Mesh** to
   set an initial evenly-spaced grid — specify the number of **Rows** and
   **Columns**, and an **Appearance** option (Flat, To Center, or To Edge)
   for an initial highlight placement.
2. Alternatively, select the **Mesh tool** (**U**) and click directly on
   the shape to add mesh points exactly where you want them, one click at a
   time, building the mesh organically instead of on a fixed grid.
3. Click any mesh point (an intersection of mesh lines) with the Mesh tool
   or Direct Selection tool (**A**), then pick a new fill color from the
   Swatches or Color panel — the color blends smoothly outward from that
   point into its neighbors.
4. Drag a mesh point (or its curve handles, same behavior as an anchor
   point's handles on a regular path) to reshape how the mesh lines curve
   across the surface, changing where highlights and shadows sit.
5. Delete a mesh point with the Mesh tool by Option/Alt-clicking it; add
   one the same way (plain click) at any point later — meshes stay fully
   editable, unlike a rasterized gradient.

!!! warning "Meshes replace a flat fill, and add real complexity"
    Converting to a mesh discards the object's original flat fill/gradient
    and can meaningfully increase file complexity and render time on a
    large or detailed shape. Reach for a mesh specifically when a regular
    linear/radial gradient can't produce the curve you need — not as a
    default choice for every fill.

## 3. The Appearance panel and live effects

The **Appearance panel** (**Window > Appearance**, **Shift+F6**) shows
every fill, stroke, and effect currently applied to a selected object as an
editable, reorderable stack — the same non-destructive logic as Photoshop's
Layers/adjustment layers, applied to a single vector object's look.

1. Select an object and open the Appearance panel — it lists at minimum one
   **Fill** and one **Stroke** row, plus **Opacity** at the bottom.
2. Click **Add New Fill** or **Add New Stroke** (icons at the bottom of the
   panel) to stack a second fill or stroke on the *same* object — e.g. a
   solid fill beneath a semi-transparent gradient fill, or two strokes at
   different weights to fake an outline-within-an-outline.
3. Drag rows to reorder them — like layer order in Photoshop, a fill/stroke
   listed higher in the panel sits visually on top of ones listed below it
   on the same object.
4. **Effect** menu items (**Effect > Stylize > Drop Shadow**, **Effect >
   Distort & Transform > Zig Zag**, etc.) attach to whichever row is
   selected in the Appearance panel — applied to the whole object if
   nothing specific is selected, or to just one fill/stroke row if that row
   is selected first.
5. Every effect appears as its own line in the panel, indented under the
   fill/stroke it applies to. Click an effect's name to reopen its dialog
   and adjust settings, click the eye icon next to it to toggle it off
   temporarily, or drag it to the trash icon to remove it entirely — none of
   this touches the object's underlying path.
6. Click the panel menu (top-right ≡) and choose **Duplicate Item** on a
   whole appearance stack to copy a complex multi-fill/effect look onto
   another object, or drag the **Appearance thumbnail** (top-left of the
   panel) directly onto a different object on the canvas to apply the whole
   stack at once.

## 4. Worked example: a glossy badge icon

1. Draw a circle and apply a **Radial gradient** fill (Section 1) going
   from a light tint at the top-left to the base color at the edges, using
   the Gradient tool to drag the highlight off-center for a more natural
   glossy look.
2. Convert the circle to a **Gradient Mesh** (**Object > Create Gradient
   Mesh**, 2 rows x 2 columns is usually enough) and brighten just the top
   mesh points further for a sharper specular highlight than the flat radial
   gradient alone could produce.
3. Open the **Appearance panel** and add a second stroke at a heavier
   weight, then apply **Effect > Stylize > Drop Shadow** to just that stroke
   row for a subtle rim/depth effect independent of the fill.
4. Add a small icon or outlined wordmark (Module 3) on top, group everything
   (**⌘/Ctrl+G**), and save the result into your Creative Cloud Library
   (Level 1, Module 9) as a reusable badge Graphic.

## Cheat sheet

| Action | Where |
|---|---|
| Gradient panel | Window > Gradient (⌘/Ctrl+F9) |
| Gradient tool (set angle/position on canvas) | G |
| Gradient type: Linear / Radial / Freeform | Gradient panel > Type dropdown |
| Create a Gradient Mesh (grid) | Object > Create Gradient Mesh |
| Mesh tool (add/edit mesh points by hand) | U |
| Appearance panel | Window > Appearance (Shift+F6) |
| Add another fill/stroke to one object | Appearance panel > Add New Fill/Stroke icons |
| Apply a live effect | Effect menu (with a row selected in Appearance) |
| Copy a whole appearance to another object | Drag the Appearance thumbnail onto it |

## How It Actually Works

- **A gradient is interpolated color along a 1D parametric axis mapped onto
  the object.** A linear gradient defines a straight axis (set by the angle
  and length you drag with the Gradient tool) and computes each stop's
  position as a percentage along it; for any point on the object, Illustrator
  projects that point onto the axis, finds which two stops bracket it, and
  linearly interpolates their colors weighted by distance. Radial does the
  same thing but with distance-from-center replacing position-along-axis as
  the parameter. This is exactly why dragging the Gradient tool a shorter
  distance compresses the whole transition into a smaller physical area —
  you're rescaling the axis the percentages are measured against, not
  editing the stops themselves.
- **Gradient Mesh generalizes that same interpolation from one axis to a
  2D grid of independently-colored points.** Each mesh intersection is a
  genuine anchor point (with the same Bézier handle machinery from ordinary
  paths) that additionally carries a color value; Illustrator interpolates
  color continuously across each mesh patch — the quadrilateral bounded by
  four adjacent mesh points — using the same kind of bilinear blending a
  gradient does along a line, just extended across two dimensions at once.
  That's what makes a highlight follow a curved mesh line rather than a
  straight axis: the color's spatial reference is the curved patch geometry
  itself, not a fixed linear ramp.
- **The Appearance panel's fill/stroke/effect stack is evaluated top-to-
  bottom per object, independently of the object's actual path data.**
  The underlying path (its anchor points and curves) is stored once; every
  row in the Appearance panel is a separate rendering instruction applied
  against that same path data, composited in stack order — which is
  mechanically identical to how a Photoshop layer's pixel data can carry
  multiple non-destructive adjustments. This is why duplicating an
  Appearance stack and dragging it onto a different object reproduces the
  exact same layered look on entirely different path geometry: none of the
  fill/stroke/effect definitions reference the original object's specific
  points, only its shape at render time.
- **A live effect (like Drop Shadow or Zig Zag) stores its parameters and
  re-runs its algorithm at render/export time, rather than rewriting the
  path.** Zig Zag, for instance, keeps the original smooth path untouched
  in the object's actual geometry and instead tells the renderer "redraw
  this outline with periodic in/out displacement of a given size and
  segment count" every time it needs to display or export the object —
  identical in spirit to a Photoshop Smart Filter. That's why toggling an
  effect's visibility or deleting it instantly restores the exact original
  path with zero degradation, no matter how many effects were stacked
  before it.
- **Converting to a mesh is a one-way, destructive geometry rewrite,
  unlike a live effect.** `Create Gradient Mesh` replaces the object's fill
  definition and, crucially, its path data itself with new mesh-point
  geometry — the original single flat path and its gradient definition are
  discarded, not hidden underneath. That's the real mechanism behind the
  warning that meshes "replace" a fill rather than layer on top of it, and
  why there's no direct "convert back to gradient" command afterward.

## Exercise

Draw a simple rounded shape and apply a Radial gradient with at least three
color stops. Convert it to a Gradient Mesh and adjust at least two mesh
points' colors and positions to create a directional highlight. In the
Appearance panel, add a second stroke and apply a Drop Shadow effect to just
that stroke. Duplicate the whole appearance stack onto a second shape by
dragging the Appearance thumbnail onto it.
