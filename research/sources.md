# Source Audit - Cursor

Ngày kiểm tra: **14/08/2026**. Mỗi nguồn dưới đây đã được mở, đối chiếu publisher, ngày và claim sử dụng. `Primary` là nguồn do Cursor/Anysphere hoặc đối thủ liên quan trực tiếp công bố; `Community` là bằng chứng hành vi/cảm nhận, không được dùng để khẳng định số liệu công ty.

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
| 18 | [Cloud agent Builds (13/08/2026)](https://cursor.com/blog/builds) | Primary | Snapshot môi trường giúp startup nhanh và resilient hơn | PASS |
| 19 | [AIUC-1 certification (13/08/2026)](https://cursor.com/blog/aiuc-1) | Primary | Independent audit, adversarial testing và ongoing evaluation cho agent safeguards | PASS |
| 20 | [Cursor Models & Pricing](https://cursor.com/docs/models-and-pricing) | Primary | Usage pools/on-demand usage; Teams Standard $40/user/tháng; Enterprise custom | PASS |
| 21 | [Cursor Enterprise page](https://cursor.com/enterprise) | Primary | Indexing, privacy mặc định và nhu cầu quản trị enterprise | PASS |
| 22 | [Cloud Agents documentation](https://cursor.com/docs/cloud-agent) | Primary | Isolated cloud VM, source-control connection và khả năng test/verify | PASS |
| 23 | [Cursor on Product Hunt](https://www.producthunt.com/products/cursor?launch=cursor-1-0) | Community | Người dùng coi tích hợp AI, context đa file và VS Code compatibility là lý do đổi | PASS |
| 24 | [HN launch thread (24/03/2023)](https://news.ycombinator.com/item?id=35285047) | Community | Phản ứng launch sớm và hoài nghi về editor/wrapper | PASS |
| 25 | [Cursor pricing megathread](https://www.reddit.com/r/cursor/comments/1lwjxic/pricing_megathread/) | Community | Anxiety về minh bạch usage và thay đổi pricing | PASS |
| 26 | [Cursor pay-as-you-go discussion (21/06/2026)](https://www.reddit.com/r/cursor/comments/1uboz5c/cursors_20_plan_is_incredible_but_the_payasyougo/) | Community | Context overhead/cost là friction; tốc độ Composer vẫn tạo pull | PASS |
| 27 | [Cursor appreciation post (01/06/2026)](https://www.reddit.com/r/cursor/comments/1ttxvgk/cursor_appreciation_post/) | Community | Tốc độ, guardrail và review phù hợp project nhỏ | PASS |
| 28 | [GitHub Copilot coding agent (13/02/2026)](https://github.blog/changelog/2026-02-13-network-configuration-changes-for-copilot-coding-agent/) | Competitor primary | GitHub có background agent tự mở PR | PASS |
| 29 | [OpenAI Codex app (02/02/2026; Windows 04/03/2026)](https://openai.com/index/introducing-the-codex-app/) | Competitor primary | Multi-agent, scheduled Automations và phân phối qua ChatGPT/CLI/IDE/cloud | PASS |
| 30 | [Claude Code for Team & Enterprise (20/08/2025)](https://www.anthropic.com/news/claude-code-on-team-and-enterprise) | Competitor primary | Claude Code đi vào enterprise với admin/compliance | PASS |
| 31 | [Google Jules public launch (06/08/2025)](https://blog.google/innovation-and-ai/models-and-research/google-labs/jules-now-available/) | Competitor primary | Asynchronous agent + GitHub + subscription distribution | PASS |
| 32 | [METR study of experienced OSS developers](https://arxiv.org/abs/2507.09089) | Research | AI coding không mặc định tạo năng suất; trust/measurement vẫn là constraint | PASS |
| 33 | [Programming by Chat study](https://arxiv.org/abs/2604.00436) | Research | IDE chat là progressive specification; người dùng quản lý autonomy/context | PASS |
| 34 | [Michael Truell on owning the editor and focusing on power users (10/11/2025)](https://a16z.com/podcast/michael-truell-how-cursor-builds-at-the-speed-of-ai/) | Founder interview | CEO Cursor giải thích quyết định sở hữu editor và tập trung power users thay vì “democratization” | PASS |

## Mâu thuẫn và giới hạn

- Review cộng đồng có selection bias; chúng chỉ được dùng để nhận diện lực chuyển đổi, không đại diện toàn bộ user base.
- Case study và số liệu adoption do Cursor công bố là bằng chứng định hướng, không phải kiểm định độc lập. Memo ghi rõ nguồn khi dùng.
- Không dùng valuation, ARR hay market share để suy ra product quality.
- Product Hunt hiển thị launch năm 2024 cho listing hiện tại, trong khi HN và changelog xác nhận sản phẩm đã public từ 2023; timeline dùng ngày nguồn gốc cụ thể, không dùng nhãn tổng hợp của Product Hunt.

## Tổng hợp

- Nguồn đã kiểm tra: **34**
- Primary/competitor primary: **26**
- Founder interview: **1**
- Community/review: **5**
- Research độc lập: **2**
- URL/claim đã được sửa trong final source validation: **9 findings**
- Broken URL hoặc unsupported claim còn lại sau sửa: **0**

Chi tiết từng URL và remediation: [SOURCE_AUDIT.md](SOURCE_AUDIT.md).

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
