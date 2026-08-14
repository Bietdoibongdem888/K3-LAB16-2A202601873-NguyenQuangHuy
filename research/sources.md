# Source Audit - Cursor

Ngày kiểm tra: **14/08/2026**. Mỗi nguồn dưới đây đã được mở, đối chiếu publisher, ngày và claim sử dụng. `Primary` là nguồn do Cursor/Anysphere hoặc đối thủ liên quan trực tiếp công bố; `Community` là bằng chứng hành vi/cảm nhận, không được dùng để khẳng định số liệu công ty. HTTP audit cuối kiểm tra **57 URL duy nhất**. Lần quét đầu có 44 URL trả `200`, 12 URL Reddit/OpenAI/Product Hunt trả `403` do anti-bot và 1 URL changelog Cursor cũ trả `404`. Link hỏng đã được thay bằng [Cursor 0.2.0](https://cursor.com/changelog/0-2-0), nên trạng thái cuối là **45 URL trả `200`, 12 access-restricted và 0 broken**.

| # | Nguồn | Loại | Claim được hỗ trợ | Kết quả |
|---:|---|---|---|---|
| 1 | [Cursor 0.2.9 - One-click VS Code extension import (04/05/2023)](https://cursor.com/changelog/0-2-9) | Primary | Cursor giảm chi phí chuyển đổi từ VS Code | PASS |
| 2 | [Chat v2 (24/06/2023)](https://cursor.com/changelog/0-2-34) | Primary | Chat cho phép gắn file/code/docs bằng `@` | PASS |
| 3 | [New inline edits (03/07/2023)](https://cursor.com/changelog/0-2-39) | Primary | Cmd+K nằm trong editor và dùng context tài liệu | PASS |
| 4 | [Advanced context for codebase-wide chat (19/07/2023)](https://cursor.com/changelog/0-2-49) | Primary | Kiểm soát context cho chat toàn codebase | PASS |
| 5 | [New Composer UI, Agent, Commit Messages (24/11/2024)](https://cursor.com/changelog/0-43-x) | Primary | Agent trong Composer tự chọn context và dùng terminal | PASS |
| 6 | [.cursor/rules & Better Codebase Understanding (23/01/2025)](https://cursor.com/changelog/0-45-x) | Primary | Rules lưu tri thức repo; model hiểu codebase tốt hơn | PASS |
| 7 | [Cursor 1.0 changelog (04/06/2025)](https://cursor.com/changelog/1-0) | Primary | Background Agent GA, BugBot, memories, MCP, Jupyter | PASS |
| 8 | [Cursor 1.3 (29/07/2025)](https://cursor.com/changelog/1-3) | Primary | Agent dùng terminal native; tăng khả năng quan sát context | PASS |
| 9 | [Cursor 1.4 (06/08/2025)](https://cursor.com/changelog/1-4) | Primary | Agent gắn vào GitHub PR; công cụ context tốt hơn | PASS |
| 10 | [Cursor 2.0 (29/10/2025)](https://cursor.com/changelog/2-0) | Primary | Multi-agent, model Composer, browser và sandbox | PASS |
| 11 | [Introducing Cursor for Enterprise (31/10/2025)](https://cursor.com/blog/enterprise) | Primary | Hooks, Team Rules, analytics, audit, sandbox | PASS |
| 12 | [Cloud agents can control their own computers (24/02/2026)](https://cursor.com/blog/agent-computer-use) | Primary | Cloud agent tự kiểm thử UI, tạo artifacts; hướng tới self-driving codebase | PASS |
| 13 | [Automations (05/03/2026)](https://cursor.com/blog/automations) | Primary | Agent chạy theo lịch/event từ Slack, Linear, GitHub, PagerDuty, webhook | PASS |
| 14 | [Cursor 3.0 - New Interface (02/04/2026)](https://cursor.com/changelog/3-0) | Primary | Agents Window quản lý nhiều agent qua local/worktree/cloud/SSH | PASS |
| 15 | [Cursor SDK (29/04/2026)](https://cursor.com/blog/typescript-sdk) | Primary | Đưa harness/runtime/models thành hạ tầng lập trình được | PASS |
| 16 | [Organizations for Enterprise (03/06/2026)](https://cursor.com/blog/organizations) | Primary | Quản trị budget, model, permission theo đơn vị/cấp tổ chức | PASS |
| 17 | [Cursor Router (22/07/2026)](https://cursor.com/changelog) | Primary | Router chọn model theo task và tối ưu cost/quality; admin controls | PASS |
| 20 | [Cursor pricing](https://cursor.com/pricing) | Primary | Individual từ $20/tháng; Teams $40/user/tháng; on-demand usage; Enterprise custom + pooled usage/controls | PASS |
| 21 | [Cursor Enterprise page](https://www.cursor.com/enterprise) | Primary | Indexing, privacy mặc định và nhu cầu quản trị enterprise | PASS |
| 22 | [Background Agents documentation](https://docs.cursor.com/background-agent) | Primary | Remote VM, quyền GitHub, retention và rủi ro prompt injection | PASS |
| 23 | [Cursor on Product Hunt](https://www.producthunt.com/products/cursor?launch=cursor-1-0) | Community | Người dùng coi tích hợp AI, context đa file và VS Code compatibility là lý do đổi | PASS |
| 24 | [HN launch thread (24/03/2023)](https://news.ycombinator.com/item?id=35285047) | Community | Phản ứng launch sớm và hoài nghi về editor/wrapper | PASS |
| 25 | [Cursor pricing megathread](https://www.reddit.com/r/cursor/comments/1lwjxic/pricing_megathread/) | Community | Anxiety về minh bạch usage và thay đổi pricing | PASS |
| 26 | [Cursor pay-as-you-go discussion (21/06/2026)](https://www.reddit.com/r/cursor/comments/1uboz5c/cursors_20_plan_is_incredible_but_the_payasyougo/) | Community | Context overhead/cost là friction; tốc độ Composer vẫn tạo pull | PASS |
| 27 | [Cursor appreciation post (01/06/2026)](https://www.reddit.com/r/cursor/comments/1ttxvgk/cursor_appreciation_post/) | Community | Tốc độ, guardrail và review phù hợp project nhỏ | PASS |
| 28 | [GitHub Copilot coding agent (13/02/2026)](https://github.blog/changelog/2026-02-13-network-configuration-changes-for-copilot-coding-agent/) | Competitor primary | GitHub có background agent tự mở PR | PASS |
| 29 | [OpenAI Codex app (02/02/2026; Windows 04/03/2026)](https://openai.com/index/introducing-the-codex-app/) | Competitor primary | Multi-agent/worktree/automation và phân phối qua ChatGPT | PASS |
| 30 | [Claude Code for Team & Enterprise (20/08/2025)](https://www.anthropic.com/news/claude-code-on-team-and-enterprise) | Competitor primary | Claude Code đi vào enterprise với admin/compliance | PASS |
| 31 | [Google Jules public launch (06/08/2025)](https://blog.google/innovation-and-ai/models-and-research/google-labs/jules-now-available/) | Competitor primary | Asynchronous agent + GitHub + subscription distribution | PASS |
| 32 | [METR study of experienced OSS developers](https://arxiv.org/abs/2507.09089) | Research | AI coding không mặc định tạo năng suất; trust/measurement vẫn là constraint | PASS |
| 33 | [Programming by Chat study](https://arxiv.org/abs/2604.00436) | Research | IDE chat là progressive specification; người dùng quản lý autonomy/context | PASS |
| 34 | [Michael Truell on owning the editor and focusing on power users (10/11/2025)](https://a16z.com/podcast/michael-truell-how-cursor-builds-at-the-speed-of-ai/) | Founder interview | CEO Cursor giải thích quyết định sở hữu editor và tập trung power users thay vì “democratization” | PASS |
| 35 | [Cursor customer roster](https://cursor.com/customers) | Primary/customer | Deployment ở engineering organizations; outcome gồm onboarding, debugging, migration/refactor và ship | PASS |
| 36 | [Coinbase customer story (23/06/2026)](https://cursor.com/blog/coinbase) | Primary/customer | 2.400+ developers; workflow chuyển từ tự viết sang định nghĩa intent, delegate và validate | PASS |
| 37 | [Money Forward customer story (18/03/2026)](https://cursor.com/blog/money-forward) | Primary/customer | Basic chat/autocomplete không đủ; agent end-to-end tạo bottom-up demand rồi mở rộng sang QA/product/design | PASS |
| 38 | [Cursor Security (updated 24/04/2026)](https://cursor.com/security) | Primary | Privacy Mode, SOC 2, model blocklists, agent security và enterprise controls | PASS |
| 39 | [HN: Stopped using Vim, moving to Cursor (03/10/2024)](https://news.ycombinator.com/item?id=41727350) | Community/switching | User đổi editor vì đọc code, tra API và giữ context ngay trong workflow | PASS |
| 40 | [Cursor vs VS Code + Copilot (02/09/2024)](https://www.reddit.com/r/cursor/comments/1f7cku2/) | Community/review | Context/integration tạo pull; outage là reliability friction | PASS |
| 41 | [Three-month negative review (20/04/2025)](https://www.reddit.com/r/CursorAI/comments/1k3uz9k/my_honest_review_after_3_months_with_cursorai/) | Community/review | Cleanup/maintainability risk ở codebase phức tạp; chỉ delegate task bounded | PASS |
| 42 | [Pricing backlash and switch-away (07/07/2025)](https://www.reddit.com/r/programming/comments/1lu8eyb/cursor_pay_more_get_less_and_dont_ask_how_it_works/) | Community/review | Usage opacity, quality/context complaints và cancellation intent | PASS |
| 43 | [Remote SSH abandonment (30/10/2023)](https://www.reddit.com/r/datascience/comments/17k3svb/has_anyone_tried_cursorsh_ai_editor_for_data/) | Community/review | Editor reliability regression đủ khiến early user bỏ tool | PASS |
| 44 | [Cursor 3 product announcement (02/04/2026)](https://cursor.com/blog/cursor-3) | Primary | Agent-centered multi-repo workspace và local/cloud handoff | PASS |
| 45 | [Amplitude autonomous pipeline (15/04/2026)](https://cursor.com/blog/amplitude) | Primary/customer | Event → agent → risk classification; low-risk PR auto-merge | PASS |
| 46 | [What we learned building cloud agents (02/06/2026)](https://cursor.com/blog/cloud-agent-lessons) | Primary/research | Cloud runtime cần durable execution, checkpoint và enterprise IT controls | PASS |
| 47 | [Auto-review (11/06/2026)](https://cursor.com/blog/agent-autonomy-auto-review) | Primary/research | Contextual risk classifier cân bằng autonomy và approval | PASS |
| 48 | [Agent swarms and model economics (20/07/2026)](https://cursor.com/blog/agent-swarm-model-economics) | Primary/research | Planner-worker mix, coordination và chênh lệch cost lớn | PASS |
| 49 | [Cursor Router announcement (22/07/2026)](https://cursor.com/blog/router) | Primary | Production routing, admin modes, satisfaction/keep rate và cost per commit | PASS |
| 50 | [Cloud-agent environment (30/07/2026)](https://cursor.com/blog/cloud-agent-environment) | Primary/research | Versioned, secure, self-healing environment là product layer | PASS |
| 51 | [Composer 2.5](https://cursor.com/composer) | Primary | Cursor-owned price-efficient model cho long-running agents và SDK | PASS |
| 52 | [GitHub Copilot cloud agent (01/04/2026)](https://github.blog/changelog/2026-04-01-research-plan-and-code-with-copilot-cloud-agent/) | Competitor primary | Research/plan/code trên branch, test và PR trong GitHub | PASS |
| 53 | [GitHub Copilot app preview (14/05/2026)](https://github.blog/changelog/2026-05-14-github-copilot-app-is-now-available-in-technical-preview/) | Competitor primary | GitHub-native issue/PR/check context và agent review surface | PASS |
| 54 | [Codex mobile and programmatic access (14/05/2026)](https://openai.com/index/work-with-codex-from-anywhere/) | Competitor primary | Mobile control, synced state và scoped credentials cho CI/automation | PASS |
| 55 | [Cursor Start India (28/07/2026)](https://cursor.com/blog/cursor-start) | Primary | Local pricing, UPI và bundled Cursor models/cloud agents | PASS |

## Prediction Signals

| Signal cluster | Source IDs | Reading used in CP3 |
|---|---|---|
| Autonomous workflow | 12, 13, 45, 47 | Execution + triggers + artifacts + risk classification có thể thành policy-gated lifecycle |
| Runtime/platform | 15, 46, 50 | Environment reliability và reusable harness là moat ngoài raw model |
| Model economics | 17, 48, 49, 51 | Routing/role allocation giải pricing anxiety và model commoditization |
| Enterprise control | 11, 16, 38, 47, 49 | Org hierarchy và policy primitives đang hội tụ |
| Multi-surface distribution | 13, 15, 17, 44 | Agent/review state đã trải desktop, cloud, integrations và SDK |

## Competitor Context

| Pressure | Source IDs | Implication |
|---|---|---|
| GitHub owns repo/PR/identity/editor distribution | 52, 53 | Threat mạnh nhất; Cursor phải vượt feature parity bằng workflow/runtime/economics |
| OpenAI bundles model + agent + automation | 29, 54 | Gây áp lực giá và distribution lên standalone agent product |
| Anthropic bundles terminal agent + compliance | 30 | Power user và enterprise có thể giữ editor hiện hữu |
| Google bundles async GitHub agent | 31 | Background execution tự thân không còn là moat |

## Mâu thuẫn và giới hạn

- Review cộng đồng có selection bias; chúng chỉ được dùng để nhận diện lực chuyển đổi, không đại diện toàn bộ user base.
- Case study và số liệu adoption do Cursor công bố là bằng chứng định hướng, không phải kiểm định độc lập. Memo ghi rõ nguồn khi dùng.
- Không dùng valuation, ARR hay market share để suy ra product quality.
- Product Hunt hiển thị launch năm 2024 cho listing hiện tại, trong khi HN và changelog xác nhận sản phẩm đã public từ 2023; timeline dùng ngày nguồn gốc cụ thể, không dùng nhãn tổng hợp của Product Hunt.
- Hai URL từng ghi ngày 13/08/2026 (`/blog/builds`, `/blog/aiuc-1`) không xác minh được khi audit CP3 nên đã bị loại; không prediction nào dựa vào chúng.
- HTTP `403` từ Reddit/OpenAI/Product Hunt được ghi là access restriction, không được tính là broken link; không có major claim nào phụ thuộc duy nhất vào các trang bị chặn.

## Tổng hợp

- Nguồn đã kiểm tra và giữ lại trong registry: **53**
- URL duy nhất trên toàn repository: **57**
- Broken URL sau khi sửa: **0**
- Primary/competitor primary: **40**
- Founder interview: **1**
- Community/review: **10**
- Research độc lập: **2**
- URL hoặc claim bị loại vì không đủ bằng chứng: **2**

## CP1 final milestone coverage

| Final milestone | Original source re-opened 14/08/2026 | Claim/date supported |
|---|---|---|
| AI-first editor launch — 24/03/2023 | HN launch + founder interview | PASS |
| Codebase-wide context — 19/07/2023 | Cursor 0.2.49 changelog | PASS |
| Agent in Composer — 24/11/2024 | Cursor 0.43 changelog | PASS |
| Background Agent GA — 04/06/2025 | Cursor 1.0 changelog | PASS |
| Multi-agent + Composer — 29/10/2025 | Cursor 2.0 changelog | PASS |
| Enterprise governance — 31/10/2025 | Cursor official blog | PASS |
| Automations — 05/03/2026 | Cursor official blog | PASS |
| Cursor SDK — 29/04/2026 | Cursor official blog | PASS |
