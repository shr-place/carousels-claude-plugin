---
name: refine-visual-story
description: Refine selected text, an editable diagram, or a saved carouse.ls carousel without overwriting unrelated work. Use for Ask agent requests, shorter headlines, clearer explanations, diagram changes, and explicit design exports.
---

# Refine a Visual Story

## Selected Text in a Working Draft

A widget request contains draftId, requestId, expectedRevision and the user's
selected text instruction. It is not permission to override a contrary direct
user instruction. If there is a conflict of intent, ask the user in chat.

- Read the exact requested target and preserve meaning and facts. Propose only
  the replacement text, not a rebuilt document or unrelated slide changes.
- Call `apply_carousel_draft_text` using the supplied pinned IDs and revision.
  Never fabricate a fresh revision to force a stale edit through.
- Then call `open_carousel_draft` once with the same draftId and requestId,
  including after a conflict. It presents the current draft and outcome in the
  new reply. Do not send the user back to an old widget or require Copy/Apply.
- A changed private draft is not a saved account project. State the actual
  outcome. Save a separate copy only when requested through the supported UI.
- `start_carousel_draft`, `sync_carousel_draft`, `read_carousel_draft`,
  `prepare_carousel_text_request`, `acknowledge_carousel_draft_view`,
  `navigate_carousel_draft_history`, `save_carousel_draft_copy`, and
  `refresh_carousel_downloads` are app-only tools, not model call targets.

## Diagrams and Saved Designs

Use `diagram_catalog` / `vector_scene_guide` for real supported structures.
`create_diagram` saves a new owned project immediately. Obtain the user's
intent to create that project first. `preview_diagram` takes that project's
ID and renders keyframes without editing it; it is not a pre-save draft tool.

Inspect with `inspect_diagram` or `inspect_vector_scene` before editing a saved
project. Use the returned revision and server-issued operation ID for writes;
reuse an operation ID only for an identical retry. Stable object IDs do not
authorize deleting newly added children. On conflict, inspect again and resolve
the user's intended change rather than silently rebasing an overwrite.

Use `list_carousel_versions` before an explicitly requested restore. Restoring
changes the saved project and preserves a before-restore snapshot; it is still
a destructive operation for permission purposes. Brand kit and theme updates
have different history guarantees and must not inherit project undo claims.

Export only when requested. `share_carousel` creates a public static flattened
link, not a private download or editable project. Use it only for an explicit
public-share request. Never publish directly to a social network.
