---
name: connect-awardy-mcp
description: Connect Awardy and verify access in ChatGPT, Codex, Claude Code, or another MCP-compatible assistant. Use when installing or reconnecting Awardy, or when Awardy tools are missing, disabled, or need sign-in.
---

# Connect Awardy

1. Treat a bare link to this repository or guide, or a follow-up like “install it”, as a request for the Awardy ChatGPT plugin by default. Install repository skill files only when the user specifically asks for the skills. Recommend one path, starting with the link or next action. Use the user's stated target first, then a clearly identified current client and available connection tools. For regular ChatGPT or an unspecified target in Codex Cloud, use the ChatGPT setup reply below. Preserve the exact clickable URL with `?open_in_app` even when the session cannot install the plugin on the user’s behalf. From a Cloud task in the app, tell the user to return to **Home** and start a regular **Chat**.
2. A sandbox, cloud terminal, or read-only configuration is insufficient for local Codex setup. Keep Terminal commands to requests targeting a local client. Run commands only when the user asks you to perform the setup and you have access to the intended local environment. For an explicit Codex Cloud setup request, use supported plugin controls if available.
3. If the client is unclear and no other client is requested, use the ChatGPT route. Ask which client only when it would change the instructions. See the [connection guide](README.md) for client-specific details or use the [plain-text setup guide](https://raw.githubusercontent.com/emircaglayan/awardy-skills/main/skills/connect-awardy-mcp/README.md) if the GitHub page cannot be fetched. If Awardy tools are already available, use a read-only check to verify access and continue with the requested task.

4. Have the user sign in to Awardy and approve access in the authorization window when prompted. Never ask them to paste their password, tokens, or authorization codes into chat.
5. Verify the connection with a read-only call. If the desired award program is locked after connecting, explain that its availability depends on the Awardy account and workspace. If the tools are still unavailable, identify the missing sign-in, client permission, or setup step.
6. For a winner or campaign question, continue with [Awardy campaign research](https://github.com/emircaglayan/awardy-skills/tree/main/skills/awardy-campaign-research#readme) if installed, or offer the research skill if the user wants the full workflow.

## ChatGPT setup reply

> [Open Awardy in ChatGPT](https://chatgpt.com/plugins/plugin_asdk_app_6aca6016a0ac8191b65c654f21dcbe2d?open_in_app)
>
> Select **Install plugin**, then **Connect**. Sign in to Awardy, open a regular Chat, and select **@Awardy**.
