# Kleap for Claude Code

Build, edit, publish, and grow real websites and web apps from Claude Code through Kleap's hosted Model Context Protocol server.

The plugin bundles the remote MCP connection and three focused commands:

- `/kleap:build` creates a new project, exposes live build progress, and verifies deployment before reporting it live.
- `/kleap:iterate` reads the current source before making a narrow edit, publishes once, and shows the finished site.
- `/kleap:grow` reads analytics, Google Search Console performance, and saved form submissions without changing the project.

## MCP endpoint

```text
https://kleap.co/api/mcp
```

Transport: Streamable HTTP. Authentication uses Kleap OAuth in the user's browser; no API key needs to be copied into the plugin.

## Local review

Validate the package:

```sh
claude plugin validate .
```

Load it directly during development:

```sh
claude --plugin-dir /absolute/path/to/kleap-claude-plugin
```

In Claude Code, open `/mcp` and complete the Kleap sign-in flow. Then use one of the commands above or ask Claude naturally to use Kleap.

To install from GitHub:

```text
/plugin marketplace add kleaphq/kleap-claude-plugin
/plugin install kleap@kleap
```

This is the public source package submitted for review in Anthropic's Claude plugin directory.

## Safety model

- Existing files are read before they are edited.
- Small changes use exact replacements rather than whole-file rewrites.
- Credit-consuming AI builds and broad edits require clear user authorization.
- Deletes, domain connections, and unrequested publication require explicit confirmation.
- A project is described as live only after deployment is confirmed.
- Analytics and form submissions are read only when relevant, and personal data is minimized in responses.

## What the MCP server provides

- Create, inspect, and edit websites and web apps
- Write, read, rename, and remove project files
- Publish to Kleap hosting and verify deployment
- Connect domains the user already owns
- Capture site screenshots
- Read traffic analytics, Google Search Console data, and form submissions

`search_domains` checks availability only. The connector does not purchase domains or transfer money.

## Documentation and support

- Product and connector guide: https://kleap.co/mcp
- Kleap documentation: https://docs.kleap.co
- Privacy policy: https://kleap.co/privacy-policy
- Help center: https://help.kleap.co/en/
- Support: hello@kleap.co

## License

Apache License 2.0. See [LICENSE](./LICENSE).
