# Awardy campaign research

Use this skill to find award-winning marketing work by topic, industry, brand, competitor, or channel. It also works when you already know the award program, year, or category you want to see.

Connect Awardy first using the [connection guide](https://github.com/emircaglayan/awardy-skills/tree/main/skills/connect-awardy-mcp#readme). If you’re already connected, install the research skill and start with a question.

## Install the skill

- **ChatGPT.** Download the [campaign research ZIP](https://github.com/emircaglayan/awardy-skills/releases/latest/download/awardy-campaign-research.zip). In an eligible workspace, open **Plugins → Skills → Create → Upload from your computer** and select the ZIP. If that workspace lacks skill upload but supports file attachments, extract the ZIP and attach `SKILL.md` and both files in `references/` to the chat. Ask ChatGPT to follow the skill for that chat. [OpenAI’s skills guide](https://help.openai.com/en/articles/20001066-skills-in-chatgpt)
- **Codex.** Send the following message in Codex, then start a chat and mention `$awardy-campaign-research`.

  > Use $skill-installer to install the skill at https://github.com/emircaglayan/awardy-skills/tree/main/skills/awardy-campaign-research

- **Claude Code.** Extract the ZIP into a folder named `awardy-campaign-research` under `~/.claude/skills/` for personal use, or under `.claude/skills/` inside a project. Start a chat and use `/awardy-campaign-research`. [Claude Code skills guide](https://code.claude.com/docs/en/skills)
- **Other assistants.** Install the skill folder if the assistant supports skills. Otherwise, give it `SKILL.md` and both files from `references/` as instructions in a chat with Awardy connected.

## Try a search

In ChatGPT, type **@** and select **Awardy** before the question. In other assistants, start with “Use Awardy to…” Here are a few examples.

- “Find standout creator-led campaigns that drove product trial.”
- “Find me the best AI campaigns.”
- “Show me the latest award-winning campaigns in pet care.”
- “Show me the winners in The One Show 2026’s Branded AI Campaign category.”

For a broad search, expect a list grouped by category, with winner counts and the campaign, brand, and award level for each result. Ask for a closer look to get a short case description, a case page, and a video link where available. You can also ask for those details upfront.

See the [user guide](references/user-guide.md) for more prompts and a worked example. Read [SKILL.md](SKILL.md) for the full workflow.
