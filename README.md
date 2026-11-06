# Tripo 3D for Antigravity

Generate and edit 3D models with [Tripo](https://www.tripo3d.ai) from Antigravity: text, image or multiview to 3D, texturing, segmentation, retopology, rigging, animation and format conversion (GLB, FBX, OBJ, USDZ, STL, 3MF).

The plugin connects to Tripo's hosted MCP server for international accounts (`https://openapi-mcp.tripo3d.ai/mcp`) and bundles the `tripo-3d` skill, which plans each job, shows the credit cost and waits for your confirmation before any paid step. Published and maintained by VAST (Tripo).

## Requirements

- A Tripo international account ([developers.tripo3d.ai](https://developers.tripo3d.ai/en)) with credits. Generation and post-processing spend your own Tripo credits. Tripo China accounts are not supported.
- Antigravity App or Antigravity CLI.

## Sign in

The plugin uses OAuth; it stores no API key.

1. In the Antigravity App, open **Customizations → Installed → Tripo 3D**, click **Go to Accounts** under **Sign in required** and start the sign-in from the **Accounts** tab.
2. In your browser, sign in to the Tripo console, choose the API key to authorize (an account without a key gets `cli-default` created automatically) and approve.
3. If Antigravity asks for an authorization code, paste it in the **Accounts** tab.

Never paste authorization codes or tokens into the chat.

## Try it

- Turn my reference image into a textured 3D model with PBR materials and export it as GLB.
- Build a game-ready 3D character with PBR textures, rig it for animation, and export it as FBX.
- Generate a custom 3D-printable figurine and export it as STL.

## Costs and approvals

Before uploading or creating a task, the skill shows the paid steps and estimated credits, and waits for an explicit yes. A description in words with no image is shown as a concept image first; the 3D model is planned only after you accept that image. Keep Antigravity's default Ask permission for Tripo tools instead of allowing all MCP tools. Ask the agent for your Tripo balance or usage at any time.

- Read-only tools (`tripo_plan`, `tripo_balance`, `tripo_task_status`, `tripo_task_list`, `tripo_task_wait` and `tripo_usage`) never create tasks.
- Generation and post-processing tasks spend credits as listed on the [pricing page](https://developers.tripo3d.ai/en/pricing). Estimates in a plan are not live quotes; the agent reports the actual charge from `tripo_usage`.

## Troubleshooting

- **Tripo tools do not appear**: check that the plugin is enabled under **Customizations → Installed** (in the CLI, `/plugin`) and that sign-in finished.
- **"invalid or revoked grant; re-authorize"**: the authorization expired or was revoked. Sign in again from the plugin's **Accounts** tab.
- **Insufficient balance**: Tripo rejects new tasks until you add credits in the Tripo console.
- **Rate limited (HTTP 429)**: code 2000 means too many tasks of the same kind are already running and no task was created; code 1007 means too many requests. Wait and try again; the error includes Tripo's `request_id` for support.
- **A task is still running**: each wait call returns the latest status after up to about a minute. Ask the agent to keep waiting on the same task instead of starting a new one.

## Data and privacy

Prompts, images and models you choose to send are uploaded to Tripo and processed under the Tripo [Privacy Policy](https://www.tripo3d.ai/privacy). The plugin stores no API key; Antigravity keeps the OAuth tokens. Download links returned by Tripo expire after a short time.

## Uninstall and revoke access

Disabling or uninstalling the plugin does not revoke Tripo's access, and it does not cancel tasks that were already submitted or refund their credits. To revoke access, delete the authorized key on the API Keys page of the Tripo console.

## Privacy, terms and support

- [Privacy Policy](https://www.tripo3d.ai/privacy)
- [Terms of Service](https://developers.tripo3d.ai/en/terms)
- [Support](https://developers.tripo3d.ai/en/support)
