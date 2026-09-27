---
name: animated-explainer
description: Create an editable animated diagram or short visual explainer with carouse.ls. Use for branching ideas, processes, funnels, cycles, layers, charts, style variations and diagram MP4 exports, not generated footage or audio.
---

# Animated Explainer

Use the user's message, relationships and real values as the source. Choose a
semantic recipe before attempting raw vector geometry. Read `diagram_catalog`
for the supported recipe and its limits; do not invent unsupported fields.

## Structure and Visual Direction

- Tree: branching ideas. Two edge levels produce two slides with a continuous
  rightward camera pan. This is not a general transition between arbitrary scenes.
- Process, funnel or cycle: steps, narrowing stages or a recurring loop.
- Layers, hub or zoom: hierarchy, related concepts or a magnified detail.
- Comparison or before-after: alternatives or a transformation.
- Chart: user-supplied quantitative data, never fabricated evidence.

Styles are classic, editorial, playful and blueprint. Preserve explicit user
colors. When comparing styles, keep labels and relationships identical so the
user compares the design, not a different story. Creating three versions means
three saved projects; do this only when the user requested those creations.
Do not promise a side-by-side comparison widget unless the tool provides one.

## Create, Inspect and Refine

`create_diagram` saves a new account project immediately, not an unsaved draft.
Make that consequence clear when the user only asked for ideas or a preview;
obtain creation intent before calling it. Use concise labels and stable IDs.

Inspect the saved result with `inspect_diagram` and render actual keyframes with
`preview_diagram`. Check label fit, connections and the camera boundary when
present. A returned project ID alone does not prove the diagram looks correct.
Open the actual project by projectId through `open_saved_carousel` when an interactive
editor is wanted. Do not claim the widget rendered until it is visible.

Use `edit_diagram` for supported label, structure, palette, style and timing
changes. Supply the latest expectedRevision and server-issued nextOperationId
from inspection. Keep the same operation ID only for an identical retry.
Resolve conflicts against current state rather than forcing a stale overwrite.
Removing a node also removes its subtree. Preserve unrelated manual changes.

speed is an absolute multiplier: 1.2 is 20% faster than base speed; holdMs is
independent. For 20% faster than an already adjusted speed, inspect the current
value and multiply it by 1.2 within the supported bounds.

## Export

When requested, call `start_video_export` with the owned projectId and
mode=combined for one MP4, then poll that job through `get_video_export` at the
recommended interval. Do not start duplicate jobs while the first is pending.
Combined output is up to 60 seconds at 30 fps. Report completion only when the
job succeeds and provides a download. URLs expire and are not permanent links.

The product renders editable vector/text/photo motion. Do not promise generated
footage, audio, arbitrary scene morphs or a compact multi-project story composer.
Public sharing is separate from download; never call `share_carousel` merely
to deliver an export.
