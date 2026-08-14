# Cursor — Milestone Candidates

CP1 review toàn bộ 18 candidates theo sáu tiêu chí, mỗi tiêu chí 0–5: strategic importance, workflow impact, segment impact, moat impact, evidence quality và principle clarity. Điểm số hỗ trợ judgment, không thay thế reasoning. Final selection giữ đúng **8** product decisions.

| # | Date | Candidate | Category | Score /30 | Source | Status |
|---:|---|---|---|---:|---|---|
| 1 | 24/03/2023 | Public launch một editor xây cho AI | Launch | 27 | [HN launch](https://news.ycombinator.com/item?id=35285047), [founder interview](https://a16z.com/podcast/michael-truell-how-cursor-builds-at-the-speed-of-ai/) | **KEEP** |
| 2 | 16/04/2023 | Ghost Mode không lưu dữ liệu | Enterprise | 18 | [0.2.4](https://cursor.com/changelog/0-2-4) | DROP — trust feature sớm nhưng chưa đổi workflow/positioning mạnh bằng enterprise governance |
| 3 | 04/05/2023 | One-click import extension từ VS Code | Distribution | 23 | [0.2.9](https://cursor.com/changelog/0-2-9) | DROP — tactic giảm friction, được subsume bởi quyết định lớn hơn là sở hữu editor |
| 4 | 24/06/2023 | Chat v2 với `@` file/code/docs | Core workflow | 20 | [0.2.34](https://cursor.com/changelog/0-2-34) | DROP — cải tiến interaction, nhưng codebase context tháng 7 đổi trajectory rõ hơn |
| 5 | 03/07/2023 | Cmd+K inline edits + docs retrieval | Core workflow | 21 | [0.2.39](https://cursor.com/changelog/0-2-39) | DROP — quan trọng cho flow nhưng incremental so với context ở cấp repo |
| 6 | 19/07/2023 | Context cho codebase-wide chat | Context capability | 27 | [0.2.49](https://cursor.com/changelog/0-2-49) | **KEEP** |
| 7 | 24/11/2024 | Agent trong Composer tự chọn context và dùng terminal | Agentic capability | 30 | [0.43](https://cursor.com/changelog/0-43-x) | **KEEP** |
| 8 | 23/01/2025 | `.cursor/rules` + model hiểu codebase | Context capability | 23 | [0.45](https://cursor.com/changelog/0-45-x) | DROP — enabler mạnh nhưng không tạo interaction primitive mới như Agent |
| 9 | 04/06/2025 | Cursor 1.0: Background Agent GA + BugBot | Agentic capability | 28 | [1.0](https://cursor.com/changelog/1-0) | **KEEP** |
| 10 | 29/07/2025 | Shared native terminal + context visibility | Core workflow | 20 | [1.3](https://cursor.com/changelog/1-3) | DROP — tăng steerability/trust nhưng là refinement của agent loop |
| 11 | 06/08/2025 | Background Agent hoạt động trong GitHub PR | Distribution | 24 | [1.4](https://cursor.com/changelog/1-4) | DROP — mở surface mới nhưng trajectory async đã được đại diện bởi 1.0 và Automations |
| 12 | 29/10/2025 | Cursor 2.0: multi-agent interface + model Composer | Competitive response | 29 | [2.0](https://cursor.com/changelog/2-0) | **KEEP** |
| 13 | 31/10/2025 | Hooks, Team Rules, audit, sandbox cho enterprise | Enterprise | 28 | [Enterprise](https://cursor.com/blog/enterprise) | **KEEP** |
| 14 | 24/02/2026 | Cloud agent dùng computer, tự test và tạo artifacts | Agentic capability | 26 | [Computer use](https://cursor.com/blog/agent-computer-use) | DROP — rất mạnh nhưng là capability bridge; Automations thể hiện business/workflow shift rõ hơn |
| 15 | 05/03/2026 | Automations chạy theo schedule/event | Business model | 29 | [Automations](https://cursor.com/blog/automations) | **KEEP** |
| 16 | 02/04/2026 | Cursor 3 Agents Window | Core workflow | 25 | [3.0](https://cursor.com/changelog/3-0) | DROP — UI expression của multi-agent thesis đã bắt đầu ở 2.0 |
| 17 | 29/04/2026 | Public Cursor SDK | Platform expansion | 28 | [SDK](https://cursor.com/blog/typescript-sdk) | **KEEP** |
| 18 | 22/07/2026 | Cursor Router chọn model theo task/cost/quality | Competitive response | 26 | [Router](https://cursor.com/changelog) | DROP — economic layer quan trọng nhưng chưa đổi user job/segment mạnh bằng SDK |

## Score rubric

`Score = Strategic + Workflow + Segment + Moat + Evidence + Principle clarity`, tối đa 30. Điểm gần nhau được phân xử bằng counterfactual: nếu bỏ mốc đó, câu chuyện sản phẩm có mất một bước tiến hóa riêng hay chỉ mất một implementation/refinement?

## Final selection

1. Launch AI-first editor — 24/03/2023
2. Codebase-wide context — 19/07/2023
3. Agent trong Composer — 24/11/2024
4. Background Agent GA + BugBot — 04/06/2025
5. Cursor 2.0 multi-agent + Composer model — 29/10/2025
6. Enterprise governance layer — 31/10/2025
7. Automations — 05/03/2026
8. Cursor SDK — 29/04/2026

## CP1 selection audit

- Final milestones: **8**
- KEEP: **8**; DROP: **10**
- Chronology: PASS
- Original source per final milestone: PASS (8/8)
- Mỗi mốc thay đổi ít nhất một trong workflow, interaction primitive, segment, moat hoặc strategic position: PASS
