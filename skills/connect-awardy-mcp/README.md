# Connect Awardy

Connect your Awardy account so your AI assistant can look up award programs, winners, and campaign cases. For a quick try, [open ChatGPT Plugins](https://chatgpt.com/plugins), search for **Awardy**, and connect your account. Then open a regular **Chat** and select **@Awardy**.

## Choose the setup for this user

If someone shares only this guide or its GitHub link, help them connect Awardy. Give one route based on what they asked for and the client you can identify. Start with the link or next action and give a short verification prompt.

- **ChatGPT web, desktop, or mobile.** Lead with [Open ChatGPT Plugins](https://chatgpt.com/plugins), then tell the user to search for **Awardy**, connect their account, and select **@Awardy** in a regular Chat.
- **Codex Cloud, a read-only task, or a remote task with no confirmed local Terminal.** For a quick try, lead with the same ChatGPT link. In the app, tell the user to return to **Home** and start a regular **Chat**. A code execution tool by itself cannot establish that the task can configure the user's own Codex installation.
- **Local Codex, Claude Code, or another MCP client.** Use that client’s instructions when the user names it or the current local client is clearly identified. Only run setup commands when they request that action and the session can configure the intended client.

If you cannot identify the client and the user has no stated preference, give the ChatGPT route. Ask “Which app are you setting up Awardy in?” only when they need a different client and its identity is unclear. If the GitHub page fails to load, try this [plain-text guide](https://raw.githubusercontent.com/emircaglayan/awardy-skills/main/skills/connect-awardy-mcp/README.md).

## ChatGPT

If you’re in a Codex Cloud task, return to **Home** and start a regular **Chat** for this setup. The composer in Codex Cloud can say **Work on Cloud**.

1. In your ChatGPT workspace, open **Plugins** from the sidebar. You can also use the [ChatGPT plugin directory](https://chatgpt.com/plugins) in your browser.
2. Search for **Awardy**. If it appears, open the listing and select **Install plugin**. If it is already installed, find it under **Settings → Plugins**.
3. Select **Connect** when prompted. Sign in with the Awardy account you want to use and approve the connection.
4. In a regular text chat, type **@**, select **Awardy**, then ask “Which Awardy workspace am I connected to? List three award programs.”

Your plan and workspace determine which plugins you can install and use. [OpenAI’s plugin guide](https://help.openai.com/en/articles/20001256-plugins-in-chatgpt)

See [OpenAI’s guide to connecting an app account](https://help.openai.com/en/articles/20001494-connecting-and-managing-app-accounts-in-chatgpt).

### If Awardy is missing from the directory

If Awardy doesn’t appear for your account, try **Plugins** in the ChatGPT workspace you intend to use. Where that workspace allows custom MCP servers, use these steps on ChatGPT web. If the custom-server option is missing, check with your workspace admin.

1. Open **Plugins → + → Add custom MCP server**.
2. Use the name **Awardy**. Enter `https://mcp.awardy.ai/plugin/mcp` under **Connection**. Select **OAuth** for authentication.
3. Review the setup notice, choose **Create as a plugin**, then review the discovered tools. Install the resulting plugin if prompted.
4. Select **Connect** when prompted, sign in to Awardy, then try the **@Awardy** test above.

See [OpenAI’s custom MCP guide](https://help.openai.com/en/articles/12584461-connecting-custom-mcp-servers-in-chatgpt) for workspace permissions and the older **Apps → Create** screen.

## Local Codex

Use this path when you want Awardy in Codex on your computer and can run commands in your local Terminal. If you specifically want it inside a Codex Cloud task, check **Sources → Use plugins** if offered, then select Awardy if it’s listed. For a quick try from a Cloud task, use the [ChatGPT steps](#chatgpt). [OpenAI’s plugin guide](https://help.openai.com/en/articles/20001256-plugins-in-chatgpt)

In your local Terminal, run:

```sh
codex mcp add awardy --url https://mcp.awardy.ai/mcp
```

Complete the Awardy sign-in and authorization if prompted. If you already added the server and still need to sign in, run `codex mcp login awardy`. Open a new Codex chat and try “Use Awardy to tell me which workspace I’m connected to and list three award programs.”

See [OpenAI’s Codex MCP guide](https://developers.openai.com/codex/mcp/).

## Claude Code

In Terminal, run:

```sh
claude mcp add --transport http --scope user awardy https://mcp.awardy.ai/mcp
```

Start a new Claude Code session. Open `/mcp`, select **awardy**, and follow the sign-in prompt. Then try “Use Awardy to tell me which workspace I’m connected to and list three award programs.”

See [Claude Code’s MCP guide](https://code.claude.com/docs/en/mcp).

## Another MCP-compatible assistant

Add a remote MCP server named **Awardy**. Use the URL `https://mcp.awardy.ai/mcp`, choose **Streamable HTTP**, and use **OAuth** to sign in. Then run the same award-program test. The assistant must support both the remote connection and OAuth.

## After connecting

If your assistant can show the connected workspace, check that it is the one you want. If it can only list programs, that confirms it can reach Awardy. Winner access still depends on your Awardy workspace.

For winner searches, install [Awardy campaign research](https://github.com/emircaglayan/awardy-skills/tree/main/skills/awardy-campaign-research#readme) and ask for the kind of work you want to see.

## Use this guide as a skill

The connection steps above also work on their own. To have your assistant guide you through them, install the [Connect Awardy ZIP](https://github.com/emircaglayan/awardy-skills/releases/latest/download/connect-awardy-mcp.zip) in ChatGPT under **Plugins → Skills → Create → Upload from your computer**, if your workspace supports skill uploads. In local Codex, ask `$skill-installer` to install this folder:

```text
https://github.com/emircaglayan/awardy-skills/tree/main/skills/connect-awardy-mcp
```

In Claude Code, extract the ZIP into `~/.claude/skills/connect-awardy-mcp/` and use `/connect-awardy-mcp`. In other assistants, use the skill installer if there is one, or give the assistant `SKILL.md` and this README.
