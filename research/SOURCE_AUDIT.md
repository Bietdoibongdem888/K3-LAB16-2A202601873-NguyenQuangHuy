# Source Validation Audit — Cursor

Audit date: **14/08/2026**  
Scope: every external URL in every Markdown deliverable in the repository.  
Method: extract URLs repo-wide, open each target, follow redirects, compare publisher/title/date and the exact claim used. Community sources are accepted only as evidence of individual sentiment or observed discussion, never as representative market statistics.

## Final result

- Markdown files scanned: **8** before the two audit reports were added
- URL occurrences checked: **105**
- Unique final URLs checked: **35**
- Accessible and claim-supporting: **35**
- Redirect-only final URLs: **0**
- Broken final URLs: **0**
- Unsupported final claims: **0**

## Audit matrix

| # | Final URL | Used in | Claim checked | Date check | Status |
|---:|---|---|---|---|---|
| 1 | [a16z founder interview](https://a16z.com/podcast/michael-truell-how-cursor-builds-at-the-speed-of-ai/) | `memo.md`, milestone/source research | Michael Truell discusses owning the editor and focusing on power users | Published 10/11/2025 | PASS |
| 2 | [METR study](https://arxiv.org/abs/2507.09089) | user/source research | RCT found early-2025 AI tools, primarily Cursor Pro, increased completion time in this setting | Submitted 12/07/2025 | PASS |
| 3 | [Programming by Chat](https://arxiv.org/abs/2604.00436) | user/source research | 11,579 IDE sessions show progressive specification and active autonomy/context management | Submitted 01/04/2026 | PASS |
| 4 | [Google Jules launch](https://blog.google/innovation-and-ai/models-and-research/google-labs/jules-now-available/) | competitor/source research | Jules is an asynchronous GitHub-integrated coding agent distributed through Google plans | 06/08/2025 | PASS |
| 5 | [Cloud agents with computer use](https://cursor.com/blog/agent-computer-use) | user/prediction/source research | Isolated cloud agents can test software, produce artifacts and point toward self-driving codebases | 24/02/2026 | PASS |
| 6 | [AIUC-1](https://cursor.com/blog/aiuc-1) | user/prediction/source research | Independent audit, adversarial testing and ongoing evaluation of safeguards | 13/08/2026 | PASS |
| 7 | [Automations](https://cursor.com/blog/automations) | `memo.md`, prediction/source research | Agents run from schedules/events with sandbox, integrations and memory | 05/03/2026 | PASS |
| 8 | [Cloud agent Builds](https://cursor.com/blog/builds) | user/prediction/source research | Filesystem snapshots improve startup speed, resilience and observability | 13/08/2026 | PASS |
| 9 | [Cursor Enterprise](https://cursor.com/blog/enterprise) | `memo.md`, user/prediction/source research | Hooks, Team Rules, audit/analytics and sandbox target governed organizations | 31/10/2025 | PASS |
| 10 | [Organizations](https://cursor.com/blog/organizations) | user/prediction/source research | Budget, model and permission administration by organization unit | 03/06/2026 | PASS |
| 11 | [Cursor SDK](https://cursor.com/blog/typescript-sdk) | `memo.md`, user/prediction/source research | Cursor exposes its agent harness/runtime programmatically | 29/04/2026 | PASS |
| 12 | [Cursor changelog index](https://cursor.com/changelog) | README, milestone/prediction/source research, `memo.md` | Cursor Router selects models by task; Cost/Balance/Intelligence and admin controls are documented | 22/07/2026 entry | PASS |
| 13 | [Chat v2](https://cursor.com/changelog/0-2-34) | user/milestone/source research | `@` supplies files, code and docs to chat | 24/06/2023 | PASS |
| 14 | [New inline edits](https://cursor.com/changelog/0-2-39) | user/milestone/source research | Cmd+K is in-editor and can use documentation context | 03/07/2023 | PASS |
| 15 | [Ghost Mode 0.2.4](https://cursor.com/changelog/0-2-4) | milestone research | Users could opt out of server-side data storage via Ghost Mode | 16/04/2023 | PASS |
| 16 | [Codebase-wide chat 0.2.49](https://cursor.com/changelog/0-2-49) | README, `memo.md`, principle/user/milestone/source research | More control over codebase-wide context building and lint-fix flow | 19/07/2023 | PASS |
| 17 | [Cursor 0.2.9](https://cursor.com/changelog/0-2-9) | README, user/competitor/milestone/source research, `memo.md` | One-click VS Code extension import and early whole-repo Q&A | 04/05/2023 | PASS |
| 18 | [Cursor 0.43.x](https://cursor.com/changelog/0-43-x) | `memo.md`, principle/milestone/source research | Early Composer Agent selects context, uses terminal; UI provides inline diffs | 24/11/2024 | PASS |
| 19 | [Cursor 0.45.x](https://cursor.com/changelog/0-45-x) | `memo.md`, milestone/source research | Repository rules and improved codebase-understanding model | 23/01/2025 | PASS |
| 20 | [Cursor 1.0](https://cursor.com/changelog/1-0) | README, `memo.md`, principle/milestone/source research | Background Agent GA and BugBot code review | 04/06/2025 | PASS |
| 21 | [Cursor 1.3](https://cursor.com/changelog/1-3) | milestone/source research | Agent uses the native terminal and shows context usage | 29/07/2025 | PASS |
| 22 | [Cursor 1.4](https://cursor.com/changelog/1-4) | milestone/source research | Improved agent steerability/tools and GitHub PR attachment | 06/08/2025 | PASS |
| 23 | [Cursor 2.0](https://cursor.com/changelog/2-0) | README, `memo.md`, principle/milestone/prediction/source research | Up to eight isolated parallel agents plus first agentic coding model Composer | 29/10/2025 | PASS |
| 24 | [Cursor 3.0](https://cursor.com/changelog/3-0) | README, `memo.md`, milestone/source research | Agents Window spans local, worktree, cloud and remote SSH environments | 02/04/2026 | PASS |
| 25 | [Cloud Agents docs](https://cursor.com/docs/cloud-agent) | source research | Isolated cloud VMs, source-control connection and test/verify capability | Current on 14/08/2026 | PASS |
| 26 | [Models & Pricing docs](https://cursor.com/docs/models-and-pricing) | prediction/source research | Usage pools/on-demand billing; Teams Standard $40/user/month; Enterprise custom | Current on 14/08/2026 | PASS |
| 27 | [Cursor Enterprise page](https://cursor.com/enterprise) | source research | Enterprise privacy, indexing and administrative controls | Current on 14/08/2026 | PASS |
| 28 | [GitHub Copilot coding agent](https://github.blog/changelog/2026-02-13-network-configuration-changes-for-copilot-coding-agent/) | competitor/source research | Asynchronous background agent runs in GitHub Actions and opens a PR | 13/02/2026 | PASS |
| 29 | [HN launch thread](https://news.ycombinator.com/item?id=35285047) | `memo.md`, user/milestone/source research | Public launch and early comparison with existing editor + Copilot | 24/03/2023 | PASS |
| 30 | [OpenAI Codex app](https://openai.com/index/introducing-the-codex-app/) | competitor/source research | Multi-agent command center, scheduled Automations and ChatGPT/CLI/IDE/cloud distribution | 02/02/2026; Windows update 04/03/2026 | PASS |
| 31 | [Anthropic Claude Code for business plans](https://www.anthropic.com/news/claude-code-on-team-and-enterprise) | competitor/source research | Claude Code included in Team/Enterprise with admin/compliance controls | 20/08/2025 | PASS |
| 32 | [Cursor on Product Hunt](https://www.producthunt.com/products/cursor?launch=cursor-1-0) | user/competitor/source research | Individual reviews mention editor integration, multi-file context, VS Code migration and review burden; alternatives include Windsurf | Listing/reviews, no timeline date used | PASS |
| 33 | [Pricing megathread](https://www.reddit.com/r/cursor/comments/1lwjxic/pricing_megathread/) | user/source research | Individual users express uncertainty about limits, usage and pricing | Community evidence only | PASS |
| 34 | [Cursor appreciation post](https://www.reddit.com/r/cursor/comments/1ttxvgk/cursor_appreciation_post/) | user/source research | One user's positive experience emphasizes speed plus guardrails/review | 01/06/2026 | PASS |
| 35 | [Pay-as-you-go discussion](https://www.reddit.com/r/cursor/comments/1uboz5c/cursors_20_plan_is_incredible_but_the_payasyougo/) | user/source research | One user reports latency pull alongside context/cost friction | 21/06/2026 | PASS |

## Repairs made during this audit

| Finding before repair | Resolution | Final status |
|---|---|---|
| Legacy Ghost Mode URL redirected to a new host and then returned 404 | Replaced with canonical `https://cursor.com/changelog/0-2-4` | PASS |
| `docs.cursor.com/account/pricing` redirected only to the docs home, so it no longer supported the pricing claim | Replaced with `https://cursor.com/docs/models-and-pricing`; claim aligned to usage pools/on-demand billing and current Teams/Enterprise wording | PASS |
| `docs.cursor.com/background-agent` redirected only to the docs home | Replaced with `https://cursor.com/docs/cloud-agent`; removed unsupported retention/prompt-injection wording | PASS |
| `www.cursor.com/enterprise` redirected to the canonical host | Normalized to `https://cursor.com/enterprise` | PASS |
| Agent 0.43 source did not state “multi-file edits” | Removed that phrase; retained context selection, terminal and inline diff claims | PASS |
| VS Code fork/dependency claim was not supported by the cited 0.2.9 release | Narrowed to the evidenced extension-import decision and marked strategic reading as **INFERENCE** | PASS |
| Early/current user segments were presented too categorically | Marked both as **INFERENCE** and stated the evidentiary limit | PASS |
| AIUC-1 wording said “periodic” testing | Aligned wording to the page: independent audit, adversarial testing and ongoing evaluation | PASS |
| Codex competitor row mentioned worktrees, which the cited announcement did not state | Removed “worktrees”; retained documented multi-agent, Automations and distribution claims | PASS |

## Claim integrity rules applied

- Official release dates use the date printed on the original changelog/blog page.
- Community posts support only the sentiment of the cited poster/thread, not population-wide conclusions.
- Research abstracts are described within their stated sample and setting.
- Strategic conclusions not directly stated by a source are labeled **INFERENCE**.
- No source is marked PASS merely because it returns HTTP 200; the relevant content must support the claim.

## Conclusion

**SOURCE VALIDATION: PASS**

All 35 final URLs are accessible and all claims retained in the repository are supported at the level stated. Broken links and over-claimed wording found during the audit were corrected before this PASS was issued.
