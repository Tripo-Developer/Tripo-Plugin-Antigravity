# Region and authentication

| Region | Connection | Only MCP endpoint |
|---|---|---|
| Tripo international | tripo | https://openapi-mcp.tripo3d.ai/mcp |

This plugin supports only Tripo international and needs a Tripo international account from https://developers.tripo3d.ai/en. Tripo China accounts, credits, tasks, uploads and downloads are not available through it; never switch to another Tripo endpoint or reuse another account's session.

The official Antigravity MCP docs state that serverUrl is Streamable HTTP with OAuth DCR auto-discovery; the config has no headers, token or client secret. Public discovery declares register, S256 and refresh_token, but real host sign-in, callback, refresh and revocation are not tested yet.

The user completes authorization in the host's authentication UI; authorization codes and tokens must never be sent to the agent or written to the repository. Stop if authorization fails. Disabling or uninstalling the plugin does not revoke access; the user revokes it by deleting the authorized key on the API Keys page of the Tripo console. Tasks stay bound to the account that created them.

Official reference: https://antigravity.google/docs/mcp/ . For install and uninstall steps, see the package root README; this skill never changes any host files automatically.
