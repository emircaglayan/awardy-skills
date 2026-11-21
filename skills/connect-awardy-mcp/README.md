# Connect Awardy

Connect your Awardy account so your AI assistant can look up award programs, winners, and campaign cases. Choose the instructions for the assistant you use.

## ChatGPT

1. Open [ChatGPT Plugins](https://chatgpt.com/plugins) in the workspace where you want to use Awardy.
2. Search for **Awardy**. If you find it, open the listing and select **Install plugin**. If it is already installed, find it under **Settings → Plugins**.
3. Select **Connect** when prompted. Sign in with the Awardy account you want to use and approve the connection.
4. Start a text chat. Type **@**, select **Awardy**, then ask “Which Awardy workspace am I connected to? List three award programs.”

See [OpenAI’s guide to connecting an app account](https://help.openai.com/en/articles/20001494-connecting-and-managing-app-accounts-in-chatgpt).

### If Awardy is missing from the directory

On ChatGPT web, use this route if your workspace allows custom MCP servers. If the option is missing, check with your workspace admin.

1. Open **Plugins → + → Add custom MCP server**.
2. Use the name **Awardy**. Enter `https://mcp.awardy.ai/plugin/mcp` under **Connection**. Select **OAuth** for authentication.
3. Review the setup notice, choose **Create as a plugin**, then review the discovered tools. Install the resulting plugin if prompted.
4. Select **Connect** when prompted, sign in to Awardy, then try the **@Awardy** test above.

See [OpenAI’s custom MCP guide](https://help.openai.com/en/articles/12584461-connecting-custom-mcp-servers-in-chatgpt) for workspace permissions and the older **Apps → Create** screen.

## Codex

In Terminal, run:

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

The connection steps above also work on their own. To have your assistant guide you through them, install the [Connect Awardy ZIP](https://github.com/emircaglayan/awardy-skills/releases/latest/download/connect-awardy-mcp.zip) in ChatGPT under **Plugins → Skills → Create → Upload from your computer**, if your workspace supports skill uploads. In Codex, ask `$skill-installer` to install this folder:

```text
https://github.com/emircaglayan/awardy-skills/tree/main/skills/connect-awardy-mcp
```

In Claude Code, extract the ZIP into `~/.claude/skills/connect-awardy-mcp/` and use `/connect-awardy-mcp`. In other assistants, use the skill installer if there is one, or give the assistant `SKILL.md` and this README.
