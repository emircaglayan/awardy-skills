---
name: connect-awardy-mcp
description: Connect Awardy and verify access in ChatGPT, Codex, Claude Code, or another MCP-compatible assistant. Use when installing or reconnecting Awardy, or when Awardy tools are missing, disabled, or need sign-in.
---

# Connect Awardy

1. Identify which client the user wants to set up. If they want to try Awardy in the ChatGPT app or only share the setup link, start with [the ChatGPT plugin steps](README.md#chatgpt). If the chat is in Codex Cloud or shows **Work on Cloud**, tell them how to return to Home and start a regular Chat for that path. Use local Terminal commands only when the user wants to configure local Codex and can use a Terminal. For a request specifically about a Codex Cloud task, check its plugin options or explain what is unavailable in that task.
2. Check for Awardy tools. If available, call `get_account_context` when exposed, or try the read-only test in the [connection guide](README.md). If the connection is working, continue with the user's task.
3. If Awardy is missing or needs authorization, use the relevant steps in the [connection guide](README.md). In ChatGPT, use the Awardy plugin if available, or the custom MCP option on the web if the workspace permits it. Use the general Awardy MCP endpoint in local Codex, Claude Code, and other compatible clients. When the client can configure the server and the user asks to connect it, carry out the supported setup steps.
4. Have the user sign in to Awardy and approve access in the authorization window when prompted. Never ask them to paste their password, tokens, or authorization codes into chat.
5. Verify the connection with a read-only call. If the desired award program is locked after connecting, explain that its availability depends on the Awardy account and workspace. If the tools are still unavailable, identify the missing sign-in, client permission, or setup step.
6. For a winner or campaign question, continue with [Awardy campaign research](https://github.com/emircaglayan/awardy-skills/tree/main/skills/awardy-campaign-research#readme) if installed, or offer the research skill if the user wants the full workflow.
