# Cursor — Milestone Candidates

18 candidates được khai phá rộng trước khi lọc. Danh sách bao phủ thay đổi về workflow, expectation, segment, monetization, vị thế, moat và counterfactual; toàn bộ vẫn ở trạng thái `CANDIDATE` trong CP0.

| # | Date | Candidate | Why it matters | Source | Status |
|---:|---|---|---|---|---|
| 1 | 24/03/2023 | Public launch một editor xây cho AI | Đặt cược vào surface riêng thay vì extension; tạo quyền thay đổi primitive lập trình | [HN launch](https://news.ycombinator.com/item?id=35285047) | CANDIDATE |
| 2 | 16/04/2023 | Ghost Mode không lưu dữ liệu | Privacy xuất hiện từ rất sớm | [0.2.4](https://www.cursor.com/changelog/v0-2-4-chat-scrolling-ghost-mode-2023-04-16-) | CANDIDATE |
| 3 | 04/05/2023 | One-click import extension từ VS Code | Triệt switching cost khi yêu cầu user đổi editor | [0.2.9](https://cursor.com/changelog/0-2-9) | CANDIDATE |
| 4 | 24/06/2023 | Chat v2 với `@` file/code/docs | Biến context thành object người dùng thấy và điều khiển | [0.2.34](https://cursor.com/changelog/0-2-34) | CANDIDATE |
| 5 | 03/07/2023 | Cmd+K inline edits + docs retrieval | Giữ AI trong flow và đưa knowledge vào editor | [0.2.39](https://cursor.com/changelog/0-2-39) | CANDIDATE |
| 6 | 19/07/2023 | Context cho codebase-wide chat | Chuyển lợi thế từ prompt đơn sang hiểu repo | [0.2.49](https://cursor.com/changelog/0-2-49) | CANDIDATE |
| 7 | 24/11/2024 | Agent trong Composer tự chọn context và dùng terminal | Từ suggestion/edit sang goal-seeking loop | [0.43](https://cursor.com/changelog/0-43-x) | CANDIDATE |
| 8 | 23/01/2025 | `.cursor/rules` + model hiểu codebase | Đóng gói context tổ chức và convention vào repo | [0.45](https://cursor.com/changelog/0-45-x) | CANDIDATE |
| 9 | 04/06/2025 | Cursor 1.0: Background Agent GA + BugBot | Mở workflow async và code review, vượt khỏi editor foreground | [1.0](https://www.cursor.com/en/changelog?v=1.0) | CANDIDATE |
| 10 | 29/07/2025 | Shared native terminal + context visibility | Tăng trust và khả năng can thiệp vào agent | [1.3](https://cursor.com/changelog/1-3) | CANDIDATE |
| 11 | 06/08/2025 | Background Agent hoạt động trong GitHub PR | Đưa distribution sang nơi team review code | [1.4](https://cursor.com/changelog/1-4) | CANDIDATE |
| 12 | 30/10/2025 | Cursor 2.0: multi-agent interface + model Composer | Biến editor thành control plane cho agent và bắt đầu sở hữu model economics | [2.0](https://cursor.com/changelog/2-0) | CANDIDATE |
| 13 | 31/10/2025 | Hooks, Team Rules, audit, sandbox cho enterprise | Chuyển buyer từ cá nhân sang tổ chức có governance | [Enterprise](https://cursor.com/blog/enterprise) | CANDIDATE |
| 14 | 24/02/2026 | Cloud agent dùng computer, tự test và tạo artifacts | “Good” chuyển từ diff sang bằng chứng chạy được | [Computer use](https://cursor.com/blog/agent-computer-use) | CANDIDATE |
| 15 | 05/03/2026 | Automations chạy theo schedule/event | Agent trở thành always-on production workflow, không đợi prompt | [Automations](https://cursor.com/blog/automations) | CANDIDATE |
| 16 | 02/04/2026 | Cursor 3 Agents Window | UI lấy agent làm trung tâm thay vì file/editor | [3.0](https://cursor.com/changelog/3-0) | CANDIDATE |
| 17 | 29/04/2026 | Public Cursor SDK | Product hóa harness/runtime/context thành platform nhúng được | [SDK](https://cursor.com/blog/typescript-sdk) | CANDIDATE |
| 18 | 22/07/2026 | Cursor Router chọn model theo task/cost/quality | Trừu tượng hóa model, kiểm soát margin và user choice overload | [Router](https://cursor.com/changelog) | CANDIDATE |

## Kết quả CP0

- Candidate milestones: **18**
- Khoảng thời gian: **24/03/2023–22/07/2026**
- Source mix cho CP0: official changelog/blog/docs, founder interview, HN/Product Hunt/Reddit và research độc lập.
- Tất cả giữ trạng thái `CANDIDATE`; CP0 chưa chọn 6–8 milestones. Việc lọc chỉ diễn ra ở checkpoint sau.

## AI core và JTBD gate

- **AI core:** PASS. Bỏ AI làm mất Tab, context-aware chat/edit, Agent và cloud automation — tức mất value proposition chính.
- **AI-native:** Cursor tổ chức lại primitive từ gõ code thủ công sang autocomplete → instruction → task → delegation; AI-enabled product vẫn có value proposition lõi khi bỏ AI, Cursor thì không.
- **Use case rõ:** thay đổi codebase thật với context, edit, test và review trong một workflow.
- **JTBD rõ:** “Khi phải giao feature hoặc fix bug dưới áp lực thời gian, tôi muốn chuyển ý định thành thay đổi nhiều file có thể review và kiểm chứng, để ship nhanh hơn nhưng vẫn kiểm soát chất lượng.”
