---
name: awardy-campaign-research
description: Find and explain award-winning campaigns with the Awardy ChatGPT app or MCP server. Use for creative inspiration, industry or competitor research, and examples of any marketing topic, channel, practice or goal.
---

# Awardy campaign research

Find campaigns that answer the user's marketing question. Lead with the work and what the user can learn from it. Use award programs and categories to guide the search and record the recognition alongside each case. For prompts and examples, use the [Awardy user guide](references/user-guide.md).

Check for the Awardy winner tools when you are ready to search. In a regular ChatGPT chat, the user can select **@Awardy** in the message box if the app needs to be selected. If Awardy needs to be installed or connected in ChatGPT, send [Open Awardy in ChatGPT](https://chatgpt.com/plugins/plugin_asdk_app_6aca6016a0ac8191b65c654f21dcbe2d?open_in_app). For other clients, use the **Connect Awardy** skill (`connect-awardy-mcp`) if installed. Otherwise, share its [plain-text setup guide](https://raw.githubusercontent.com/emircaglayan/awardy-skills/main/skills/connect-awardy-mcp/README.md). Continue the original search once the connection works.

## Decide whether to ask or search

Read the short question in the context of the conversation and any brand profile the client has provided. Identify what the user wants to see, such as a topic or practice, channel, industry, brand or competitor, campaign goal, or market.

| User asks | What to do |
| --- | --- |
| The user names a topic, channel or practice and asks for standout campaigns. | Search immediately. Find cases that show different approaches to that topic. Offer to narrow the next pass after showing examples. |
| “Find the most recent best winning campaigns in my industry.” | Use the industry already given. If it is missing, ask “Which industry should I look at?” Wait for the answer before selecting cases for that industry. |
| “Show me what my competitors have won” or “Compare my campaigns with my competitors.” | Use competitor names already given. If they are missing, ask “Which competitors should I look at?” If comparison with the user's brand matters and its identity is also missing, ask for the brand in the same message. When the user explicitly asks for help identifying competitors, clarify the relevant brand and market as needed. |
| The user names a program, edition or category. | Search within the scope they specified. |

Ask the smallest question that fills a gap that would change the search. When two missing details are essential, ask for both together. Skip a follow-up for optional preferences such as market, channel or method when a broad search answers the request. Use any award program or category the user specifies. For an open search, choose relevant programs and categories yourself and briefly state the scope with the results.

## Find relevant campaigns

Choose sources by what the user needs:

- **Find cases to browse, explain or compare.** Read [program coverage](references/program-coverage.md). For an open search, start with one or two editions with the case material the user needs that fit the topic and market. For explanations, prefer written cases. When two programs fit, search both before widening within one. Use the shortlist's program IDs to skip a catalog lookup when the program is already known.
- **Find case films.** Search relevant programs and check the individual case for a video link. The shortlist flags films in editions with written cases, and other programs may have films too. A film link alone does not establish the strategy or results.
- **Find who won.** Search the relevant award programs, editions and categories regardless of written or video coverage.
- **Search a named program, category or case.** Use the requested scope even if it has limited case material. Report the results available there and say if a write-up or film is missing.

1. Search the named program directly once its ID is known. For an open search, use the coverage reference where applicable, or use `search_awards` to find plausible programs and IDs. Its region filter describes the program's scope. Use `list_cycles` if you need to resolve a named edition or find recent ones. Honour the requested year. When the year is open, prefer the latest editions with relevant published winners and the case material needed. If the newest accessible edition has none and the brief allows it, check an earlier one and state the edition used. When the user asks for recent campaigns, verify campaign timing in the cases when available. If only the award year is known, describe recency by the award edition.
2. Resolve a named category within its edition using `list_categories` if you need its ID. For a large result, [filter the category list](#filter-a-large-category-list) before reading the matches. If a category name matches multiple programs or sections, search the relevant matches when the request permits. Ask which one the user means when the choice matters. For a topical brief, match both the category **name and description** and use its parent path for context. The winner's category is the first relevance signal. Check case text when the category is broad or the brief requires something specific, such as a market or business outcome. Try dedicated categories before adjacent ones. For a named competitor, search the brand first and use the results to identify relevant categories.
3. Check each shortlisted category with `search_winners` using the program's `award_id`, correct `cycle_id` or year, and the category's `category_id`. A parent category includes its descendants. Use `recognition_type: "winner"` by default. Recognitions in Awardy's winner results can include Merit Awards. Preserve the official award level and honour stricter requests.
4. If a category search returns too few cases, try short phrases for a brand, campaign title, partner or category name within the requested scope. Try adjacent categories or related programs when the brief allows it. The text query matches these fields by phrase. It does not search the case narrative or filter by campaign geography. Use `page_info.next_cursor` with the same arguments when more results are needed. An empty result is a coverage gap for the searched scope. A locked result indicates a workspace access limit. Explain which applies and offer relevant accessible options. This workflow uses read-only tools.
5. Shortlist from the winner search rows before opening full cases. For “best,” use relevance first, then how well the case explains the work and supports the outcome. Use award recognition as another signal. If the user asks for the most recent winners, prioritise recency among relevant cases. For an open search, include work from more than one program when each contributes relevant, well-documented examples. Expand when the first results leave a gap. For a specific program or category lookup, stay within the requested scope and offer broader options if coverage is limited.

### Filter a large category list

If the client saves a large `list_categories` response to a file, parse that JSON where it was saved and filter it before bringing rows into the conversation. Reuse the saved response to refine the filter. For a named category, match its name or code. For a topic, check both names and descriptions. Follow `parent_id` links to recover the parent path. Keep only the relevant IDs, names, descriptions, and parent paths.

If the full response is unavailable, try the exact category name with `search_winners` for that edition. Confirm the category name and path on the returned rows. Once the ID is known, query that category without the text filter to get its winner count and list. If a partial list leaves the category unresolved, state the coverage gap.

## Show a shortlist or open the cases

- **Browse or find examples.** Choose the most relevant categories, then group by program, edition and category. Give the published winner count from `recognition_counts.winner` for that edition and category. If the search applies a text filter, label it as the count of matching winners. List every winning record in each displayed category when the list fits. Use only **campaign · advertiser or brand · exact award level** on each line. Keep distinct wins under their respective categories even when the same campaign appears twice. For a longer or partial list, label it **“Showing X of Y winners”** and offer the rest. If the user asks for all winners, follow the result cursor to include them. Use the Awardy search rows for the list. Save descriptions, links and media for the next step. Skip full-case calls and web searches for browse-only requests. End by asking “Would you like a closer look at any of these cases?”
- **Open selected cases.** Open the cases the user picks. If they say yes without choosing, start with two or three of the strongest matches from the list. If they ask for details upfront, give those details in the first answer. For each case, give a short description of what the team did, a case detail page, and a case video link when available. Use a verified Awardy link to the exact result if the tool provides one, or the organizer’s case page. If the only available link is a results listing, label it as such. Include credits or reported outcomes when they help answer the request. When the user requires written cases or films, confirm each selected case has the required material.

## Verify and explain the cases

- Use the filtered `winner_case_wins` search rows. Call `get_winner_case` with the row's `winner_case_id` and the same `award_id`. Match the search result's recognition ID in `wins`. Use that win's `effective_content`, `source_url` and linked media. Label the case page and case video separately. When a description or link is missing, say what is available.
- Confirm campaign market from campaign evidence. Agency location, advertiser headquarters and the award's scope are separate facts. Confirm the role of the method or channel in the work and label outcomes as case-reported. State when the case gives only credits, a film or a short summary.
- Start each result with the campaign and brand, what the team did, and why it fits the brief. Give the channel or practice and reported results when relevant. Put the award, year, category and recognition next to the source as supporting details.
- Group repeat appearances of the same campaign, retaining the relevant awards. When giving suggestions to adapt, ground them in the user's brand or constraints and label them as suggestions. Use the observed scope when describing what was found.
