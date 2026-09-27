# carouse.ls for Claude

Create editable carousels, photo stories and animated explainers from a brief.
Compare three distinct story directions, refine a selected passage in the
visual editor, and export images, a PDF, or rendered motion. This plugin adds
four focused skills and connects to the official carouse.ls remote MCP server.
It does not install a local server or run shell hooks.

## Connect

An existing carouse.ls account with MCP access is required. Connect the
carousels connector at `https://api.carouse.ls/api/mcp` and complete OAuth in
your browser. If another carouse.ls account is already signed in, sign out of
that service first and reconnect with the intended account. The current consent
page does not display the account email or offer an account switcher. No API
key or password belongs in this bundle or in a chat message.

## Install for Testing

Clone this repository, then load it with Claude Code:

```sh
git clone https://github.com/shr-place/carousels-claude-plugin.git
claude --plugin-dir ./carousels-claude-plugin
```

Authenticate the remote server when prompted. Alternatively, upload the
plugin-only ZIP in Claude where custom plugin upload is supported. This public
source release is not an approved directory listing. Directory review and
cross-host acceptance testing are still in progress.

## Included Skills

| Skill | Workflow |
| --- | --- |
| `visual-story-directions` | Compare three approaches and compose the chosen design |
| `photo-story` | Build a story from authorized photos and prepare exports |
| `refine-visual-story` | Refine selected text or diagrams while preserving unrelated work |
| `animated-explainer` | Build editable diagrams, preview keyframes and prepare an MP4 |

## Try It

- "Show three approaches for a LinkedIn PDF carousel about clearer meetings."
- "Use my uploaded product photos for a four-slide visual story."
- "Create an animated branching diagram in Blueprint style, then export one MP4."
- "Shorten the selected headline, then show the updated working draft."

Choose a direction before composing a complete carousel. The editor lets you
adjust slides, select text for an agent request, preview, and export. Saving a
working draft creates a separate account project; a public share is a different,
explicit action. Download files and publish them to your social network yourself.

## Limits

Motion exports animate editable text, vectors and photo compositions. They do
not synthesize footage or audio, mix uploaded video clips, or publish social
posts. Combined motion exports are limited to 60 seconds at 30 fps. A still
preview is not proof that an animation played. Some hosts may not display the
interactive editor; use the returned links and supported tools in that case.

File delivery depends on the host and browser. An export job finishing does
not prove the file reached your device. Claude download acceptance is still
being verified; do not treat a declined or blocked download as a success.

## Privacy Policy

The service receives design data, selected text and instructions, and media
you intentionally upload or authorize for the task. It does not need your
full conversation history. Private working drafts expire after seven days of
inactivity; saved projects and source media have separate account retention.
See the [privacy policy](https://carouse.ls/privacy) and
[terms](https://carouse.ls/terms). Temporary download URLs are not permanent links.

## Support

[Access and setup](https://carouse.ls/plugin-access),
[support](https://carouse.ls/support), or support@carouse.ls.
Publisher: Shareplace LLC.

## License and Scope

Copyright 2026 Shareplace LLC. This plugin bundle is licensed under the
[Apache License 2.0](LICENSE).

The repository contains workflow instructions and connection configuration,
not the carouse.ls editor, renderer, server implementation, design templates,
credentials or user designs. This license covers only the files in this
repository. It does not license the separately operated carouse.ls service
or grant an account, subscription, API quota, or rights to user content.
