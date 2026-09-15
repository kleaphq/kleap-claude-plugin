---
description: Make a reviewable change to an existing Kleap project and publish it safely
argument-hint: <site or app> — <change request>
---

Update an existing Kleap project. Request: **$ARGUMENTS**

Use the Kleap MCP tools for this workflow:

1. Resolve the project with `find_app` when the user supplied a domain, URL, slug, or name. Use `list_apps` only when the target is still ambiguous.
2. Inspect the current structure with `list_app_files`, then call `read_files` for every existing file that may change. Never rewrite an existing file blind.
3. For a precise copy, color, URL, metadata, or code change, prepare the smallest exact replacements and use `edit_files`. Show the proposed replacements before execution when the request is ambiguous or could remove content.
4. Use `modify_app` only for broad design work or whole sections where Kleap's AI should make the implementation. It consumes credits and may publish automatically, so obtain explicit confirmation immediately before calling it unless this command already clearly authorized those effects.
5. Require explicit confirmation before `delete_files`, connecting a domain, or publishing when publication was not already requested. Never blank a file as a substitute for deletion.
6. For deterministic file edits, call `publish_app` once after the edits. Check `get_publish_status` until it reports the new deployment as live; report audit findings instead of hiding them.
7. Once the requested version is confirmed live, call `get_app` exactly once as the final tool call.

Preserve every unrelated file, section, image, and layout. Do not use `write_files` to replace a large existing file for a small edit.
