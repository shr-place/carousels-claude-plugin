---
name: photo-story
description: Compose a carouse.ls visual story from user-authorized photos and export a short rendered motion sequence. Use for product photos, travel recaps, photo carousels, and photo-based social video; not for standalone AI image, footage, or audio generation.
---

# Photo Story

Use carousels tools and current schemas; do not synthesize footage or audio.

1. Establish platform, aspect ratio, short narrative and desired output. Reuse
   information already given. Identify photos the user has intentionally made
   available to carouse.ls. Prefer the widget upload or existing owned media.
   Do not search conversation history, memory or unrelated files for assets.
2. If upload is needed, follow `prepare_carousel_media_upload` and
   `complete_carousel_media_upload` exactly. Never invent successful uploads,
   media IDs, ownership, or MIME types. If this host cannot transfer a file,
   ask the user to upload it in the editor; do not exfiltrate it through a URL.
3. Inspect authorized assets with `inspect_carousel_media`. Use actual owned
   media and stable slide IDs. Compose in an unsaved document unless saving
   was requested. Preserve photo proportions and leave legible text space.
4. Use only supported finite entrances and motion. Preview key frames with
   `preview_motion`; do not call still frames a played video. Keep source media
   and the rendered video distinct. Existing video clips cannot be combined
   by the current Motion V1 export.
5. On an explicit video request, call `start_video_export` with exactly one of
   document or projectId, and the requested mode. Combined video is capped at
   1800 frames (60 seconds at 30 fps). Offer a shorter plan if necessary.
6. Poll `get_video_export` using its jobId, about every 30 seconds. A queued or
   claimed job is not a failure and must not be restarted. Report done/failed
   truthfully; show the completed download only after success.

For images use `render_carousel`; for PDF use `export_pdf`. They create artifacts
and can consume quota but are not permission to save the project or publish it.
Do not promise a download folder: it is chosen by the user's browser or host.
Download URLs expire; the widget can refresh prepared download capabilities.
Never promise that an expired URL means the account's source media was deleted.
