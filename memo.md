# Memo Teardown — Cursor

**Track:** Track 1 — AI Product  
**Lab:** K3 LAB16

## Thành viên

- Nguyễn Quang Huy — 2A202601873
- Lăng Thị Phương Huế — 2A202601915
- Cao Các Tường — 2A202601236
- Đinh Lê Quỳnh Phương — 2A202601865
- Nguyễn Khánh Toàn — 2A202601843

**Vì sao chọn sản phẩm này:**  
Cursor là đại diện xuất sắc cho làn sóng phần mềm "AI-native" (thiết kế từ lõi xung quanh AI) thay vì chỉ là "AI-enabled", giúp chúng ta hiểu rõ cách các primitive lập trình mới thay đổi hoàn toàn năng suất lập trình và cách xây dựng rào cản phòng thủ (moat) của startup trước các Big Tech.

# §1. Timeline các cập nhật lớn

| Thời điểm | Cập nhật | Context lúc đó | Nguyên lý |
|---|---|---|---|
| 24/03/2023 | **Public editor xây cho AI, không chỉ extension.** Decision sở hữu editor cho phép Cursor thay đổi navigation, edit, terminal/LSP và feedback loop ở cấp sản phẩm. [HN launch](https://news.ycombinator.com/item?id=35285047) · [Founder interview](https://a16z.com/podcast/michael-truell-how-cursor-builds-at-the-speed-of-ai/) | Copilot đã khiến autocomplete AI có ích, nhưng user sớm hỏi tại sao không dùng editor hiện hữu + Copilot. Cursor chỉ đáng tồn tại như app riêng nếu AI sẽ thay đổi primitive lập trình vượt giới hạn extension. | **AI-native UX:** khi AI đổi primitive của công việc, product cần kiểm soát interaction layer đủ sâu. |
| 19/07/2023 | **Đưa context building vào codebase-wide chat**, đồng thời nối Cmd+K với linter feedback. [Nguồn](https://cursor.com/changelog/0-2-49) | Chat/inline edit đã ở trong IDE nhưng user vẫn phải chỉ file và mang context tới model. Bottleneck chuyển từ “có model” sang “model thấy đúng phần repo và biết output có lỗi hay không”. | **Context > Model:** grounding và feedback đúng có thể tạo nhiều giá trị hơn chỉ nâng raw model. |
| 24/11/2024 | **Đưa Agent vào Composer:** tự chọn context, dùng terminal, sửa nhiều file và trả inline diff. [Nguồn](https://cursor.com/changelog/0-43-x) | Với repo context và multi-file edit, AI đã làm được task lớn hơn completion; phần việc còn lại là user phải tự điều phối tìm file → sửa → chạy lệnh → đọc lỗi. Terminal access khép loop này. | **Assistant → Agent:** tăng delegation khi AI có context, tools, observable state và review path. |
| 04/06/2025 | **Cursor 1.0 đưa Background Agent ra GA và BugBot vào PR review.** [Nguồn](https://cursor.com/changelog/1-0) | Cursor nói early signals của remote agent tích cực. Foreground agent vẫn chiếm sự chú ý; remote execution cho phép làm song song, còn BugBot trả kết quả vào GitHub nơi team vốn review. | **x10 Value:** giá trị đổi đơn vị từ tiết kiệm keystroke sang trả lại một block thời gian chú ý. |
| 29/10/2025 | **Cursor 2.0 biến editor thành multi-agent control plane và giới thiệu Composer model.** Tối đa tám agent chạy song song trong worktree/remote isolation. [Nguồn](https://cursor.com/changelog/2-0) | Khi agent làm task dài, bottleneck trở thành orchestration, conflict, latency và cost. Isolation giải quyết xung đột; model riêng cho phép co-design model với harness thay vì chỉ chuyển tiếp API. | **Wrapper → Moat:** differentiation dịch sang context, orchestration, runtime, workflow và model tối ưu cho harness. |
| 31/10/2025 | **Thêm enterprise governance:** Hooks, Team Rules, analytics, Audit Log và Sandbox Mode. [Nguồn](https://cursor.com/blog/enterprise) | Cursor công bố đã được dùng tại hàng chục nghìn enterprise. Buyer tổ chức không thể scale agent chỉ bằng output quality; họ cần policy enforcement, shared context, secrets control và auditability. | **Define Good:** enterprise AI chỉ “good” khi useful output đi cùng compliance, traceability và controllable risk. |
| 05/03/2026 | **Ra mắt Automations:** agent chạy theo schedule/event từ Slack, Linear, GitHub, PagerDuty và webhook. [Nguồn](https://cursor.com/blog/automations) | Code production tăng nhờ agent nhưng review, monitoring và maintenance chưa tăng tương ứng. Event-driven triggers kéo agent vào toàn lifecycle thay vì chờ prompt trong editor. | **Workflow Moat:** capability bền hơn khi gắn với trigger, context, integration và feedback của công việc thật. |
| 29/04/2026 | **Public Cursor SDK:** export cùng runtime, harness và models để chạy local/cloud, trong CI/CD hoặc sản phẩm khác. [Nguồn](https://cursor.com/blog/typescript-sdk) | Coding agent chuyển từ interactive tool của cá nhân sang programmatic infrastructure của tổ chức. Editor không còn là surface đủ rộng cho pipeline và embedded use cases. | **Distribution:** platform hóa harness đã chứng minh để capability xuất hiện trong workflow mà app chính không sở hữu. |

## Vì sao chọn những mốc này?

Mỗi mốc tạo một trajectory change riêng, không chỉ tăng feature count: sở hữu surface → context → task execution → async work → agent fleet/model layer → enterprise governance → always-on workflow → platform. Tập hợp này bao phủ user behavior, interaction primitive, moat, segment và business position; các update incremental hoặc chỉ biểu đạt lại thesis cũ được loại để tránh changelog noise.

## Các milestone đã cân nhắc nhưng loại

### One-click VS Code extension import — 04/05/2023

**Lý do cân nhắc:** Giảm switching cost của một editor mới bằng cách giữ extensions và thói quen VS Code.  
**Lý do loại:** Đây là tactic distribution/enabler cho quyết định lớn hơn là sở hữu editor; bỏ import làm adoption khó hơn nhưng không thay đổi product trajectory độc lập.

### `.cursor/rules` + Better Codebase Understanding — 23/01/2025

**Lý do cân nhắc:** Đưa convention và shared context vào repo, làm agent nhất quán hơn.  
**Lý do loại:** Nó củng cố context layer nhưng không tạo interaction primitive mới; milestone Agent tháng 11/2024 và enterprise governance tháng 10/2025 đại diện hai trajectory changes mạnh hơn.

### Cursor Router — 22/07/2026

**Lý do cân nhắc:** Router chọn model theo task/cost/quality, phản ứng trực tiếp với model commoditization và bill anxiety.  
**Lý do loại:** Đây là optimization/economic layer quan trọng nhưng tại thời điểm audit chưa mở user job hay segment mới rõ như SDK; product direction platform đã được chứng minh mạnh hơn.

### Cursor 3 Agents Window — 02/04/2026

**Lý do cân nhắc:** UI lấy nhiều agent làm trung tâm thay vì file/editor.  
**Lý do loại:** Đây là biểu hiện UX rõ hơn của multi-agent thesis đã được Cursor 2.0 thiết lập; chọn cả hai sẽ double-count cùng một strategic decision.

## Trajectory

```text
AI-first editor
→ codebase-aware assistant
→ tool-using Agent
→ asynchronous delegation
→ multi-agent control plane
→ governed enterprise system
→ event-driven worker
→ programmable agent infrastructure
```

## Câu hỏi phản biện CP1

### Q1. Đâu là milestone nhóm đã cân nhắc nhưng loại?

One-click VS Code import, `.cursor/rules`, Cursor Router và Cursor 3 Agents Window. Chúng đều có source tốt nhưng hoặc là enabler/refinement, hoặc trùng strategic meaning với mốc mạnh hơn.

### Q2. Vì sao chúng không đủ tư cách là product decision cuối?

Counterfactual yếu hơn: bỏ từng update có thể làm product kém thuận tiện, nhưng không xóa một bước tiến hóa riêng khỏi trajectory. Final milestones đều thay đổi control boundary, workflow, segment hoặc strategic position.

### Q3. Milestone nào quan trọng nhất?

**Agent trong Composer — 24/11/2024.** Đây là điểm Cursor chuyển từ “AI giúp sửa code” sang “AI nhận task và tự đóng loop bằng context + terminal + multi-file edits”.

### Q4. Nếu bỏ milestone đó, trajectory Cursor thay đổi thế nào?

Background Agent, multi-agent, Automations và SDK sẽ thiếu primitive cốt lõi để mở rộng. Cursor có thể vẫn là codebase-aware editor tốt, nhưng chưa trở thành agent platform.

### Q5. Nguyên lý nào xuất hiện mạnh nhất xuyên suốt timeline?

**Moat nằm ở context + workflow + orchestration, không chỉ raw model.** Mỗi bước mở rộng phạm vi delegation bằng cách sở hữu thêm context, tools, runtime, control hoặc distribution.

### Q6. Cursor tạo moat bằng model hay workflow/context?

Chủ yếu bằng workflow/context/harness; Composer model là một lớp bổ trợ cho latency, cost và co-design. Nếu model bên ngoài thay thế được nhau, control plane, repo context, runtime và enterprise integration vẫn là phần giữ product khác biệt.

## CP1 checkpoint audit

- [x] 8 final milestones, đều là product decisions
- [x] Chronological; date được xác minh
- [x] Product update và context cụ thể cho từng row
- [x] Named principle có causal reasoning riêng
- [x] 8/8 milestones có original source
- [x] 4 excluded milestones và lý do loại theo impact
- [x] Có logic chọn mốc và trajectory xuyên suốt
- [x] Principle reverts + reusable patterns nằm trong `research/principle_reverts.md`

## Rubric self-score

| Hạng mục | Điểm | Lý do |
|---|---:|---|
| Milestone selection + context | 9/10 | Selection có counterfactual và source mạnh; launch dùng HN + founder retrospective thay vì official launch announcement còn hoạt động. |
| Revert principle | 19/20 | Tám causal reverts, principle đa dạng và reusable; một phần context lịch sử vẫn là inference từ chuỗi changelog. |
| **TOTAL CP1** | **28/30** | CP1 đạt PASS, không còn blocker nghiêm trọng. |

# §2. Tệp user & JTBD

## Early adopters vs tệp hiện tại

| | Early adopters | Tệp hiện tại |
|---|---|---|
| **Đặc điểm** | Product/software engineer 2–7 năm tại startup/đội nhỏ; daily VS Code user, đã dùng Copilot + ChatGPT, tự chọn tool và tự review nên chịu được rủi ro editor non. | **Lõi:** product engineer trong team 10–500+ kỹ sư, làm codebase production nhiều file. **Buyer phụ:** engineering/platform/security leader cần budget, rules, audit và privacy. Công ty thường trả phí. |
| **JTBD chính** | Hiểu repo/library lạ; ship change có thể kiểm chứng mà không copy context qua chat–editor–terminal; giữ flow khỏi việc cơ học. | Ship feature/bug/refactor end-to-end; giao task bounded local/cloud và nhận diff + test để review; scale adoption nhưng vẫn kiểm soát risk. |
| **Trước đó họ làm bằng cách nào** | VS Code + Copilot completion; ChatGPT copy/paste; grep/docs/Google; terminal/test và apply patch thủ công. | IDE/agent rời rạc; engineer làm task tuần tự; teammate/CI/manual review; team policy nằm rải trong docs, RBAC và pipeline. |
| **Trigger adoption** | Codebase context + inline/apply workflow tạo gain lớn hơn “editor cũ + Copilot”; one-click import giảm mất extensions/muscle memory. | Agent đóng loop multi-file + terminal; Background Agent trả attention; rules/hooks/sandbox/audit giảm rủi ro rollout. |

Nguồn chính: [HN launch](https://news.ycombinator.com/item?id=35285047), [community switch từ Vim](https://news.ycombinator.com/item?id=41727350), [Coinbase](https://cursor.com/blog/coinbase), [Money Forward](https://cursor.com/blog/money-forward), [Cursor customers](https://cursor.com/customers). Community evidence chỉ cho thấy behavior; customer metrics là self-reported.

## JTBD chính

### JTBD 1 — Hiểu đúng codebase

> Khi nhận bug/feature trong repo lớn hoặc chưa quen, tôi muốn dựng nhanh mental model về kiến trúc, dependency và nơi cần sửa, để bắt đầu implementation đúng chỗ mà không mất hàng giờ tự mở file và gom context.

**Old alternative:** IDE search/grep, đọc docs, lần call sites và hỏi teammate.

### JTBD 2 — Ship change có thể kiểm chứng (primary)

> Khi phải giao feature, bug fix, migration hoặc refactor trong codebase production, tôi muốn biến intent thành diff nhiều file và đóng feedback loop, để ship nhanh hơn nhưng vẫn review, test và chịu trách nhiệm về chất lượng.

**Old alternative:** code thủ công + Copilot snippet; copy/paste với ChatGPT; tự ghép patch và chạy edit–test–fix qua terminal.

### JTBD 3 — Giữ flow

> Khi implementation bị ngắt bởi boilerplate, tra API, lint/test failure và sửa lặp lại, tôi muốn xử lý các bước cơ học ngay trong working context, để dành attention cho kiến trúc và trade-off.

**Old alternative:** web/docs, scripts, autocomplete và chuyển liên tục giữa editor–chat–terminal.

### JTBD 4 — Delegate có guardrail

> Khi nhiều task độc lập hoặc maintenance cạnh tranh attention, tôi muốn giao task bounded cho agent local/cloud và nhận lại diff, test/artifact, để tăng throughput song song mà không mất accountability.

**Old alternative:** tự làm tuần tự, giao teammate hoặc tự điều phối nhiều chat/terminal/branch.

## Dịch chuyển tệp

**Early:** AI-curious VS Code power user, adoption cá nhân, risk tolerance cao. **Current:** professional engineer dùng agent trên production code; mở rộng tới team/enterprise buyer cần governance. Không phải “developer → non-developer”; QA/product/design mới là secondary evidence.

```text
Codebase context (07/2023)
→ giảm tự gom context → hiểu/sửa repo khả thi → VS Code power user dùng daily

Agent in Composer (11/2024)
→ context + terminal + multi-file diff → đóng loop task → product engineer dùng cho work thật

Background Agent + enterprise governance (06–10/2025)
→ async delegation + rules/hooks/sandbox/audit → giảm attention/risk → team và enterprise rollout
```

## Switching Cost — Four Forces

### Push

Workflow cũ phân mảnh giữa IDE, Copilot, chatbot, docs và terminal; user phải đóng gói context, áp patch và chạy feedback loop. Money Forward cho biết basic autocomplete/chat trước đó không tạo time saving đủ rõ. Pain đẩy mạnh nhất khi repo lớn và deadline ngắn.

### Pull

Cursor gom repo context → plan/edit nhiều file → terminal/test → diff/review vào một loop, rồi mở delegation async. Outcome là giảm time-to-change và attention spent, không chỉ “có Agent.” Coinbase dùng ticket → implementation → review; community stories ghi nhận bỏ Copilot/Vim vì context và apply workflow.

### Anxiety

Agent có thể quên brief, sửa quá phạm vi hoặc tạo code khó maintain; command và source code tăng security blast radius; usage khó đoán làm mất budget trust. Senior maintainer và enterprise buyer cảm nhận mạnh nhất, nên vẫn cần human review, sandbox, privacy, audit và budget control. [Negative review](https://www.reddit.com/r/CursorAI/comments/1k3uz9k/my_honest_review_after_3_months_with_cursorai/) · [Pricing backlash](https://www.reddit.com/r/programming/comments/1lu8eyb/cursor_pay_more_get_less_and_dont_ask_how_it_works/)

### Habit / Inertia

Extensions, keybindings, debugger, remote dev, terminal setup và team convention khiến editor cũ rất sticky; user từng bỏ Cursor chỉ vì remote SSH regression. One-click VS Code import làm yếu lực này nhưng không xóa nhu cầu stability và review/rollback quen thuộc.

## Lực mạnh nhất

**Pull mạnh nhất trong quyết định chuyển sang Cursor.** Push đã tồn tại trước Cursor và có thể được giải một phần bằng Copilot/ChatGPT; Habit và Anxiety còn chống adoption. Chỉ khi context + execution + verification tạo outcome khác cấp độ, user mới có lý do bỏ workflow quen. Nếu hỏi lực giữ user *ở lại Cursor*, đó là habit mới quanh rules, shortcuts, agent/review workflow và environment—not data lock-in.

## Nếu lực đó biến mất

Nếu VS Code/GitHub, Claude Code hoặc Codex có loop context–agent–review tương đương với bundle/cost dễ hiểu hơn, switching incentive giảm mạnh: user cá nhân quay lại editor cũ và enterprise ưu tiên vendor sẵn identity/repo/procurement. Cursor phải thắng bằng reliability của context/harness, model-routing economics và governed workflow/integration; “AI trong editor” không còn đủ.

## CP2 checkpoint audit

- [x] Early/current segment cụ thể và có evidence
- [x] 7 candidates, chọn 4 JTBD không dựa trên feature; có old alternatives
- [x] Segment shift nối causal với 3 milestone CP1
- [x] Có positive, negative, switching và counter-switch evidence
- [x] Four Forces + strongest force + counterfactual hoàn chỉnh

**Rubric estimate: User specificity + JTBD 10/10; Segment shift + Four Forces 10/10; TOTAL CP2 20/20.** Chi tiết và giới hạn nguồn nằm trong `research/user_research.md`.
