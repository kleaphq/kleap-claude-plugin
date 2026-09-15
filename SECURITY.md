# Security Policy

The Kleap plugin connects Claude Code to the hosted MCP endpoint at `https://kleap.co/api/mcp`. Authentication uses Kleap OAuth and the server can read and modify projects within the permissions granted by the connected user.

## Report a vulnerability

Do not include credentials, access tokens, private project source, or personal data in a public issue.

Email `hello@kleap.co` with the subject `[Security] Kleap MCP` and include:

- a concise description and expected impact,
- steps to reproduce,
- affected endpoint or tool names,
- a minimal proof of concept with secrets removed.

Please allow a reasonable remediation window before public disclosure.

## Scope

This package covers the Claude Code plugin configuration and its connection to `https://kleap.co/api/mcp`. Product support is available through https://help.kleap.co/en/.
