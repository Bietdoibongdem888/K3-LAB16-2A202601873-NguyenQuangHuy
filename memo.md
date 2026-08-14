# Memo Teardown — Cursor

**Track:** Track 1 — AI Product  
**Lab:** K3 LAB16

## Thành viên

- Nguyễn Quang Huy — 2A202601873
- Lăng Thị Phương Huế — 2A202601915
- Cao Các Tường — 2A202601236
- Đinh Lê Quỳnh Phương — 2A202601865
- Nguyễn Khánh Toàn — 2A202601843

## Vì sao chọn Cursor

Cursor là sản phẩm AI-native vì AI quyết định interaction model cốt lõi: hiểu codebase, sửa nhiều file, dùng terminal, chạy task nền và trả diff để review. Nếu bỏ AI, phần còn lại chủ yếu là một editor tương thích VS Code; value proposition “biến intent thành software change có thể kiểm chứng” biến mất. Cursor cũng có đủ lịch sử để quan sát một trajectory rõ: từ hỗ trợ viết code sang nhận task, rồi sang điều phối agent và hạ tầng workflow.

# §1. Timeline các cập nhật lớn

| Thời điểm | Product decision | Context và nguyên lý |
|---|---|---|
| 24/03/2023 | **Ra mắt editor xây quanh AI, không chỉ extension.** [HN launch](https://news.ycombinator.com/item?id=35285047) · [Founder interview](https://a16z.com/podcast/michael-truell-how-cursor-builds-at-the-speed-of-ai/) | Copilot đã chứng minh autocomplete hữu ích, nên Cursor chỉ đáng là app riêng nếu có thể thay navigation, edit và feedback loop ở cấp editor. **AI-native UX:** khi AI đổi primitive công việc, product cần sở hữu interaction layer đủ sâu. |
| 19/07/2023 | **Đưa context building vào codebase-wide chat** và nối Cmd+K với linter feedback. [Changelog 0.2.49](https://cursor.com/changelog/0-2-49) | Bottleneck chuyển từ “có model” sang “model thấy đúng phần repo và biết output có lỗi hay không”. **Context > Model:** grounding và feedback đúng có thể tạo nhiều giá trị hơn chỉ nâng raw model. |
| 24/11/2024 | **Đưa Agent vào Composer:** tự chọn context, dùng terminal, sửa nhiều file và trả inline diff. [Changelog 0.43](https://cursor.com/changelog/0-43-x) | User không còn phải tự điều phối từng bước tìm file → sửa → chạy lệnh → đọc lỗi. **Assistant → Agent:** tăng delegation khi AI có context, tool, observable state và review path. |
| 04/06/2025 | **Cursor 1.0 đưa Background Agent ra GA và BugBot vào PR review.** [Changelog 1.0](https://cursor.com/changelog/1-0) | Foreground agent vẫn chiếm sự chú ý; remote execution cho phép làm song song và trả kết quả vào GitHub. **x10 Value:** giá trị chuyển từ tiết kiệm keystroke sang trả lại một block thời gian chú ý. |
| 29/10/2025 | **Cursor 2.0 biến editor thành multi-agent control plane và giới thiệu Composer model.** [Changelog 2.0](https://cursor.com/changelog/2-0) | Task dài tạo bottleneck mới ở orchestration, conflict, latency và cost. **Wrapper → Moat:** khác biệt dịch sang context, orchestration, runtime, workflow và model tối ưu cho harness. |
| 31/10/2025 | **Thêm enterprise governance:** Hooks, Team Rules, analytics, Audit Log và Sandbox Mode. [Enterprise](https://cursor.com/blog/enterprise) | Buyer tổ chức cần policy, shared context, secrets control và auditability trước khi scale agent. **Define Good:** output chỉ “good” khi useful đi cùng traceability và controllable risk. |
| 05/03/2026 | **Ra mắt Automations:** agent chạy theo schedule/event từ Slack, Linear, GitHub, PagerDuty và webhook. [Automations](https://cursor.com/blog/automations) | Agent bước ra khỏi prompt trong editor để tham gia maintenance và lifecycle work. **Workflow Moat:** capability bền hơn khi gắn với trigger, context, integration và feedback của công việc thật. |
| 29/04/2026 | **Public Cursor SDK:** đưa runtime, harness và models vào CI/CD hoặc sản phẩm khác. [Cursor SDK](https://cursor.com/blog/typescript-sdk) | Editor không còn là surface đủ rộng cho programmatic workflow. **Distribution:** platform hóa harness đã chứng minh để capability xuất hiện nơi app chính không sở hữu. |

Tám mốc được chọn từ **18 candidates** vì mỗi mốc xóa hoặc tạo một bước tiến hóa riêng: editor → context → Agent → async work → multi-agent/model layer → governance → event-driven worker → programmable infrastructure. Bốn mốc nổi bật đã cân nhắc nhưng loại là One-click VS Code import (enabler), `.cursor/rules` (context refinement), Cursor 3 Agents Window (trùng multi-agent thesis) và Cursor Router (economic optimization chưa mở job/segment mới). Danh sách và scoring đầy đủ nằm trong [research/milestone_candidates.md](research/milestone_candidates.md).

# §2. Tệp user & JTBD

## Early adopter và user hiện tại

| | Early adopter | User hiện tại |
|---|---|---|
| **Persona** | Product/software engineer 2–7 năm tại startup/đội nhỏ; dùng VS Code hằng ngày, đã thử Copilot + ChatGPT, tự chọn tool và tự review output. | Product engineer trong team 10–500+ kỹ sư, làm production codebase nhiều file. Buyer phụ là engineering/platform/security leader cần budget, rules, audit và privacy. |
| **Job chính** | Hiểu repo lạ và ship change mà không tự chuyển context qua chat–editor–terminal. | Ship feature/bug/refactor end-to-end; delegate task bounded và nhận diff + test để review; scale adoption có guardrail. |
| **Old alternative** | VS Code + Copilot completion; ChatGPT copy/paste; grep/docs; terminal/test thủ công. | IDE/agent rời rạc; engineer làm tuần tự; team policy nằm trong docs, CI, RBAC và manual review. |

Evidence chính đến từ [HN launch](https://news.ycombinator.com/item?id=35285047), [community switch từ Vim](https://news.ycombinator.com/item?id=41727350), [Coinbase](https://cursor.com/blog/coinbase), [Money Forward](https://cursor.com/blog/money-forward) và [Cursor customers](https://cursor.com/customers). Community evidence chỉ cho thấy behavior; customer metrics là self-reported.

## Bốn JTBD cuối

1. **Hiểu đúng codebase:** khi nhận bug/feature trong repo lớn hoặc chưa quen, dựng nhanh mental model về kiến trúc, dependency và nơi cần sửa. Old alternative: IDE search/grep, docs và hỏi teammate.
2. **Ship change có thể kiểm chứng — primary:** khi giao feature, bug fix, migration hoặc refactor, biến intent thành diff nhiều file và đóng feedback loop để ship nhanh nhưng vẫn review, test và chịu trách nhiệm chất lượng. Old alternative: code thủ công + Copilot snippet + ChatGPT copy/paste.
3. **Giữ flow:** xử lý boilerplate, tra API, lint/test failure và sửa lặp ngay trong working context để dành attention cho kiến trúc và trade-off. Old alternative: chuyển liên tục giữa editor, web/docs, chat và terminal.
4. **Delegate có guardrail:** giao task bounded cho agent local/cloud và nhận lại diff, test/artifact để tăng throughput song song mà không mất accountability. Old alternative: tự làm tuần tự hoặc tự điều phối nhiều branch/chat/terminal.

Segment shift không phải “developer → non-developer”. Codebase context (07/2023) làm editor đủ hữu ích cho VS Code power user; Agent (11/2024) đóng loop task cho professional engineer; Background Agent + governance (06–10/2025) giảm attention cost và organizational risk để team/enterprise rollout.

## Four Forces

| Force | Evidence và tác động |
|---|---|
| **Push** | Workflow cũ phân mảnh giữa IDE, Copilot, chatbot, docs và terminal; user phải tự đóng gói context, áp patch và chạy feedback loop. Pain tăng theo kích thước repo và deadline. |
| **Pull — mạnh nhất** | Cursor gom repo context → plan/edit nhiều file → terminal/test → diff/review vào một loop, rồi mở async delegation. Outcome là giảm time-to-change và attention spent, không chỉ “có Agent”. |
| **Anxiety** | Agent có thể quên brief, sửa quá phạm vi, tăng security blast radius hoặc làm bill khó đoán. Human review, sandbox, privacy, audit và budget control vẫn bắt buộc. |
| **Habit / Inertia** | Extensions, keybindings, debugger, remote dev và team convention làm editor cũ sticky. VS Code compatibility làm yếu lực này nhưng không xóa nhu cầu stability và rollback. |

**Pull là lực mạnh nhất** vì Push đã tồn tại trước Cursor và có thể được giải một phần bằng Copilot/ChatGPT, còn Habit và Anxiety chống adoption. Nếu VS Code/GitHub, Claude Code hoặc Codex tạo loop context–agent–review tương đương với bundle/cost tốt hơn, switching incentive sẽ giảm mạnh; Cursor phải thắng bằng reliability của context/harness, routing economics và governed workflow.

# §3. Ba dự đoán hướng đi — 6–12 tháng

Horizon: **14/02/2027–14/08/2027**, tính từ ngày audit 14/08/2026. Đây là prediction có falsifier, không phải roadmap đã xác nhận.

## Dự đoán 1 — Policy-gated PR lifecycle

**Cursor sẽ GA hoặc enterprise-preview một workflow first-party dùng risk policy để nhận event, sửa và tự verify code, mở PR, rồi tự merge ít nhất nhóm change low-risk; high-risk change được route tới human approval cùng artifact.** Background Agent → Automations → governance đã tạo execution, trigger và control; JTBD “delegate có guardrail” giải thích vì sao autonomy phải risk-tiered. [Auto-review](https://cursor.com/blog/agent-autonomy-auto-review) và pipeline tại [Amplitude](https://cursor.com/blog/amplitude) là tín hiệu gần. **Falsifier:** đến 14/08/2027 vẫn phải khởi tạo từng run hoặc không có first-party risk policy cho auto-merge/human review.

## Dự đoán 2 — Unified enterprise control plane

**Cursor sẽ cho organization định nghĩa ít nhất một policy về agent permission/network hoặc spend/model một lần và enforce + audit trên desktop agent, cloud agent, Automations và SDK/service-account runs.** Enterprise governance + Automations + SDK làm surface phân mảnh; current buyer cần policy và accountability trước rollout. [Organizations](https://cursor.com/blog/organizations) đã gom identity, spend và permission. **Falsifier:** bốn surface vẫn có cấu hình/audit silo tới 14/08/2027. Đây là prediction nhóm tự tin nhất (**80%**).

## Dự đoán 3 — Router trở thành economic layer mặc định

**Auto/Router sẽ là default cho cả Teams và individual paid plans, có budget/optimization policy theo task; Composer/Cursor-owned model sẽ là route mặc định cho phần lớn workload cost-sensitive.** Composer + SDK + [Router](https://cursor.com/blog/router) tiếp nối principle “workflow/context/harness > raw model”; CP2 xác định pricing anxiety là barrier. **Falsifier:** paid individual vẫn manual-model-first, Router thiếu task-level budget policy hoặc Cursor-owned model không phải route thường dùng cho cost-sensitive work tới 14/08/2027.

**Critical assumption:** enterprise tiếp tục tăng delegation và muốn Cursor — thay vì CI/IAM gateway hoặc model provider — là nơi quản trị agent. Một security incident lớn, ROI không vượt review burden, hoặc policy bị đẩy hoàn toàn xuống hạ tầng ngoài Cursor sẽ làm Prediction 2 gãy.

# §4. AI Log

| Việc | AI làm hay nhóm làm? | Nhóm kiểm chứng/phán đoán lại thế nào? |
|---|---|---|
| Tìm và gom nguồn ban đầu | AI hỗ trợ tìm, phân loại và tóm tắt; các commit CP0–CP2 lưu kết quả đã chọn. | Lần quét đầu mở **57 URL duy nhất**: 44 trả 200, 12 bị chặn 403 do anti-bot và 1 link Cursor cũ trả 404. Sau khi thay link hỏng bằng changelog chính thức, trạng thái cuối là 45 URL trả 200, 12 access-restricted và 0 broken. |
| Lập 18 milestone candidates | AI hỗ trợ tổng hợp từ changelog/blog. | Repo chấm theo 6 tiêu chí và dùng counterfactual; giữ 8, loại 10. Không suy diễn contribution của từng thành viên. |
| Chọn 8 milestone cuối | AI hỗ trợ scoring và phát hiện mốc trùng strategic meaning; judgment cuối được trình bày ở cấp nhóm. | Mỗi mốc phải làm mất một bước riêng trong trajectory nếu bị bỏ; 8/8 ngày và claim được đối chiếu lại với nguồn gốc. |
| Revert nguyên lý | AI đề xuất tên và causal chain. | Nguyên lý generic bị loại; mỗi nguyên lý phải nối context → decision → reusable lesson và khác vai trò với mốc kế tiếp. |
| Research competitor/model context | AI tổng hợp Cursor, GitHub, OpenAI, Anthropic và Google. | Chỉ dùng source primary của từng vendor cho capability/date; competitor context là pressure, không được viết như bằng chứng Cursor chắc chắn sẽ hành động. |
| User research | AI hỗ trợ đọc customer story và community discussion. | Community chỉ dùng cho sentiment/switching clues; số liệu customer story được ghi là self-reported, không suy rộng thành market share. |
| Viết JTBD candidates | AI đề xuất 7 candidates. | Giữ 4 job vẫn tồn tại nếu Cursor biến mất; loại các câu chỉ gọi tên feature như “dùng Cursor Agent”. |
| Four Forces | AI tổng hợp Push, Pull, Anxiety và Habit. | Pull được chọn là mạnh nhất bằng counterfactual: nếu closed loop đạt parity ở tool khác, lý do đổi editor giảm mạnh. |
| Brainstorm predictions | AI tạo và score 10 candidates. | Nhóm sở hữu đúng 3 lựa chọn cuối; mỗi prediction phải có horizon, CP1 + CP2 anchor, counterargument và falsifier. |
| Draft và rút gọn memo | AI viết lại cấu trúc và copy. | Nội dung research dump được giữ trong `research/`; memo chỉ giữ 8 mốc, 4 JTBD, Four Forces, đúng 3 predictions và các nguồn mạnh nhất. |
| Draft slides và notes | AI tạo structure, copy, time budget và PDF. | Flow được kiểm tra theo timeline → principles → user shift → predictions; PDF được render từng trang để kiểm tra font, cutoff, overlap và contrast. |
| Final rubric/source audit | AI chạy kiểm tra file, URL, placeholder, secret, conflict marker và Git diff. | Kết quả được ghi trong `FINAL_AUDIT.md`; presentation chỉ là preparation estimate, không giả định điểm live performance. |

AI làm nhiều nhất ở **tổng hợp, drafting và kiểm tra cơ học**. Human team sở hữu **việc chọn luận điểm cuối, chấp nhận trade-off và bảo vệ reasoning khi thuyết trình**. Repository không có bằng chứng đủ để gán công việc cụ thể cho từng thành viên, nên AI Log không ghi contribution cá nhân.

# Sources

Source registry và kết quả audit đầy đủ: [research/sources.md](research/sources.md). Research chi tiết: [milestone candidates](research/milestone_candidates.md), [principle reverts](research/principle_reverts.md), [user research](research/user_research.md), [competitor context](research/competitor_context.md) và [prediction evidence](research/prediction_evidence.md).
