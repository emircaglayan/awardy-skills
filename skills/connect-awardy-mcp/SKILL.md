---
name: connect-awardy-mcp
description: Connect Awardy and verify access in ChatGPT, Codex, Claude Code, or another MCP-compatible assistant. Use when installing or reconnecting Awardy, or when Awardy tools are missing, disabled, or need sign-in.
---

# Connect Awardy

1. Identify the assistant the user is setting up. Use the current one if clear. Ask which one only when the answer would change the setup.
2. Check for Awardy tools. If available, call `get_account_context` when exposed, or try the read-only test in the [connection guide](README.md). If the connection is working, continue with the user's task.
3. If Awardy is missing or needs authorization, use the relevant steps in the [connection guide](README.md). In ChatGPT, use the Awardy plugin if available, or the custom MCP option if the workspace permits it. Use the general Awardy MCP endpoint in Codex, Claude Code, and other compatible clients. When the client can configure the server and the user asks to connect it, carry out the supported setup steps.
4. Have the user sign in to Awardy and approve access in the authorization window when prompted. Never ask them to paste their password, tokens, or authorization codes into chat.
5. Verify the connection with a read-only call. If the desired award program is locked after connecting, explain that its availability depends on the Awardy account and workspace. If the tools are still unavailable, identify the missing sign-in, client permission, or setup step.
6. For a winner or campaign question, continue with [Awardy campaign research](https://github.com/emircaglayan/awardy-skills/tree/main/skills/awardy-campaign-research#readme) if installed, or offer the research skill if the user wants the full workflow.
