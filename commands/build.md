---
description: Build a new Kleap website or web app and follow it until it is ready
argument-hint: <project description>
---

Build a new Kleap project described as: **$ARGUMENTS**

Use the Kleap MCP tools for this workflow:

1. If the description is missing essential information, ask at most two short questions about the audience, required pages or workflow, and visual direction.
2. Call `get_credits` and explain the available balance. `create_app` consumes credits, so always ask for explicit confirmation immediately before calling it.
3. Call `create_app` once with a complete prompt and the requested visibility. Do not retry because the build feels slow. If publishing is a separate action in the returned workflow, ask for explicit confirmation again immediately before publishing.
4. Return the `build_url` immediately so the user can follow progress in the browser.
5. Then call `check_task` with the returned `task_id` about every 30 seconds until `status` is `completed` and `deployment_status` is `deployed` (a build usually takes 5 to 15 minutes). Never start a second `create_app` because the build feels slow. If the task fails with a transient error, call `retry_task` at most once and follow the new `task_id`; otherwise report the error.
6. Once deployment is confirmed, call `get_app` exactly once as the last tool call so the user sees the finished site and its address.

Never claim a site is live from a task status alone. Never purchase a domain; `search_domains` only checks availability.
