---
description: Review a Kleap site's traffic, search performance, and saved leads without changing it
argument-hint: <site or app> [7d|28d|30d|90d]
---

Review growth signals for this Kleap project: **$ARGUMENTS**

This command is read-only by default:

1. Resolve the project with `find_app` or `list_apps`.
2. Call `get_analytics` for visitors, pageviews, top pages, and referrers. Use the requested period when supported.
3. Call `get_search_console` for Google queries, impressions, clicks, CTR, and position. State that recent Search Console data can lag by about two days.
4. Call `get_form_submissions` only when the user asks to review leads or contact submissions, because these records can contain personal information. Return only the fields needed for the request.
5. Summarize the evidence, separate measured results from recommendations, and identify missing connections plainly.

If Search Console is not connected, explain that `connect_search_console` creates a browser consent link. Ask before starting that connection, and never claim to approve Google's consent for the user. Do not modify, publish, connect a domain, or delete anything from this command.
