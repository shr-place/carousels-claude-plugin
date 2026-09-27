---
name: visual-story-directions
description: Show three distinct carouse.ls design and storytelling approaches for a carousel or visual story, then compose the chosen direction. Use for template discovery, visual references, LinkedIn PDF carousels, Instagram stories, and social explainers.
---

# Visual Story Directions

Use the connected carousels MCP tools. Treat tool descriptions and schemas as
the current contract. Do not invent theme IDs, assets, completed exports or UI.

1. Reuse the user's platform, format, topic and audience. Ask one focused
   question only if platform or format changes the result. Offer a recommendation
   when the user has no preference. PDF is LinkedIn-only in the gallery; story
   is Instagram-only. Do not send the user through a long questionnaire.
2. Call `list_themes` for the chosen aspect ratio and language. Respect text
   capacity. For `show_theme_gallery` approaches use active built-in themes,
   not archived, account, photo-only, or fixed `builtin-linkedin-*` layouts.
3. Call `show_theme_gallery` with a nonempty brief of at most 2,000 characters,
   platform, format, goal, aspectRatio and exactly three `approaches`.
   Each has id, title, description, a real themeId, and its
   own 3-12 slides (title, body, role: hook/content/reward). Vary the narrative:
   e.g. practical checklist, before/after comparison, and a short story. Do not
   present identical copy with three colors as three approaches.
4. Let the user choose in the gallery or chat. If the host cannot display it,
   describe the three options briefly and ask for a choice. Never claim that
   an unseen gallery or editor opened successfully.
5. Compose the chosen design with `create_carousel`, `save:false` unless the
   user asked to save. The returned UI opens the editable document directly;
   do not call `open_carousel_editor` again merely to duplicate that widget.
   Check capacity warnings and fix overflow without dropping required facts.

Do not save, export, share or publish just because a design was previewed.
Gallery selection is not permission to overwrite an existing project.
