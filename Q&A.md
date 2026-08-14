# Q&A — Cursor Product Teardown

Mỗi câu trả lời được giữ ở mức 2–5 câu để dùng trực tiếp khi phản biện.

## Product selection

### Q1. Vì sao chọn Cursor?

Cursor là AI-native: AI quyết định interaction model từ context, edit nhiều file, terminal tới background agent. Sản phẩm có hơn ba năm changelog và một trajectory đủ rõ để phân tích product decisions, user shift và moat.

### Q2. Cursor có thực sự AI-native không?

Có. Nếu bỏ AI, Cursor chủ yếu còn một editor tương thích VS Code; value proposition “biến intent thành software change có thể kiểm chứng” biến mất. AI không phải add-on mà là lõi của navigation, edit, execution và review loop.

### Q3. Tại sao không chọn ChatGPT?

ChatGPT rộng hơn nhưng khó cô lập một product trajectory cho coding workflow. Cursor hẹp hơn, có mốc quyết định cụ thể và cho phép nối product change với persona, JTBD, switching cost và prediction rõ hơn.

## Timeline và principles

### Q4. Milestone quan trọng nhất là gì?

Agent trong Composer ngày 24/11/2024. Đây là điểm Cursor chuyển từ “AI giúp sửa code” sang “AI nhận task, tự chọn context, dùng terminal và trả diff”. Background Agent, Automations và SDK đều mở rộng primitive này.

### Q5. Milestone nào đã bị loại?

One-click VS Code import, `.cursor/rules`, Cursor 3 Agents Window và Cursor Router là bốn ví dụ nổi bật. Chúng có nguồn tốt nhưng là enabler, refinement hoặc trùng strategic meaning với mốc mạnh hơn.

### Q6. Tại sao Cursor Router không đủ lớn để vào final timeline?

Router quan trọng cho cost và model choice, nhưng tại ngày audit nó chưa mở một user job hoặc segment mới rõ bằng SDK. Nhóm vẫn dùng Router làm current signal cho Prediction 3, không double-count nó như một trajectory shift độc lập.

### Q7. Context nào quyết định milestone Agent?

Codebase context và multi-file edit đã làm task lớn hơn autocomplete khả thi, nhưng user vẫn tự điều phối tìm file, sửa, chạy lệnh và đọc lỗi. Terminal access cùng auto-context khép loop đó, nên Agent là decision chứ không chỉ đổi tên feature.

### Q8. Nguyên lý mạnh nhất xuyên timeline là gì?

**Context + workflow + orchestration > raw model.** Mỗi bước mở rộng delegation bằng cách sở hữu thêm context, tool, runtime, verification hoặc distribution; model mạnh là điều kiện cần nhưng không đủ.

## Moat

### Q9. Cursor có phải chỉ là wrapper?

Ở launch, rủi ro “wrapper” là hợp lý vì Cursor dùng model bên ngoài. Nhưng product đã thêm repo context, agent harness, runtime, orchestration, enterprise controls và model routing; đó là các lớp workflow có giá trị riêng.

### Q10. Moat của Cursor nằm ở đâu?

Moat có cơ sở nhất là integrated loop: repo/team context, reliable agent runtime, risk-aware orchestration, cross-model economics và governance. Nhóm không khẳng định data lock-in hay raw model độc quyền vì evidence chưa đủ.

### Q11. Nếu model nào cũng mạnh như nhau thì Cursor còn gì?

Khi model commoditize, context quality, task routing, runtime reliability, review artifact và policy càng quan trọng. Cursor có thể đổi model phía dưới trong khi giữ workflow và control plane phía trên.

### Q12. Nếu Microsoft đưa trải nghiệm giống Cursor vào VS Code thì sao?

Đó là threat mạnh nhất vì Microsoft/GitHub sở hữu editor, repo, identity và procurement. Cursor phải thắng ở outcome/cost toàn loop và tốc độ productization, không thể chỉ dựa vào feature parity.

## User và JTBD

### Q13. Early adopter cụ thể là ai?

Product/software engineer 2–7 năm tại startup hoặc product team nhỏ, dùng VS Code hằng ngày, đã thử Copilot + ChatGPT, có quyền tự chọn editor và đủ kỹ năng review output AI sai.

### Q14. Current user khác early adopter ở đâu?

Current primary vẫn là developer nhưng làm production codebase trong team, task nhiều file và risk tolerance thấp hơn. Company payment, shared rules, privacy, audit và budget khiến engineering/platform/security leader trở thành buyer phụ.

### Q15. JTBD chính là gì?

Khi giao feature, bug fix, migration hoặc refactor, user muốn biến intent thành diff nhiều file và đóng feedback loop để ship nhanh nhưng vẫn review, test và chịu trách nhiệm chất lượng.

### Q16. Tại sao đó là JTBD chứ không phải feature?

Job “ship một change có thể kiểm chứng” vẫn tồn tại nếu Cursor biến mất. Agent, Composer, Tab hay Chat chỉ là các solution cạnh tranh để hoàn thành job đó.

### Q17. Trước Cursor user giải quyết bằng gì?

VS Code/JetBrains + code thủ công + Copilot completion; copy/paste code và lỗi sang ChatGPT; IDE search/grep/docs; tự áp patch và chạy edit–test–fix trong terminal.

## Four Forces

### Q18. Force nào mạnh nhất?

Pull: outcome “context → edit nhiều file → test → review” trong một loop. Push có thể được giải một phần bằng tool khác, còn Habit và Anxiety chống adoption, nên Pull phải đủ mạnh để user đổi editor.

### Q19. Nếu Pull biến mất thì sao?

Nếu VS Code/GitHub, Claude Code hoặc Codex đạt loop tương đương với bundle/cost tốt hơn, incentive đổi editor giảm mạnh. Cursor phải dựa vào reliability của harness, routing economics và governed team workflow.

### Q20. Anxiety lớn nhất là gì?

Agent có thể tạo change chạy được nhưng sai phạm vi hoặc khó maintain, trong khi command và source code làm tăng blast radius. Vì vậy verification artifact, sandbox, audit và human review là điều kiện adoption chứ không phải chi tiết phụ.

### Q21. Habit nào khó phá nhất?

Daily muscle memory và infrastructure quanh extensions, keybindings, debugger, remote dev, terminal setup và team convention. One-click VS Code import giảm friction nhưng một regression editor vẫn có thể khiến user quay lại workflow cũ.

## Predictions

### Q22. Prediction nào tự tin nhất?

Unified enterprise control plane, 80%. Organizations đã có hierarchy, policy primitives xuất hiện trong Auto-review/Router, và desktop–cloud–Automation–SDK đang tạo nhu cầu quản trị thống nhất.

### Q23. Prediction nào dễ sai nhất?

Router trở thành default cho individual paid plans, 70%. Power user có thể phản đối hidden routing, còn model providers có thể giảm giá hoặc bundle nhanh hơn lợi ích kinh tế của Cursor.

### Q24. Critical assumption là gì?

Enterprise tiếp tục tăng delegation và muốn Cursor — không phải CI/IAM gateway hoặc model provider — làm nơi quản trị agent. Nếu review burden cao hơn ROI hoặc policy bị đẩy hoàn toàn xuống hạ tầng ngoài Cursor, thesis này gãy.

### Q25. Điều gì chứng minh Prediction 1 sai?

Đến 14/08/2027, Cursor vẫn yêu cầu user khởi tạo từng run hoặc không có first-party risk policy quyết định low-risk auto-merge so với human review. Customer tự ghép pipeline riêng không đủ để prediction được tính là đúng.

### Q26. Tại sao predictions dựa trên Product Sense chứ không phải đoán?

Mỗi prediction có causal chain từ milestone CP1, job/barrier CP2 tới current signal và competitive pressure. Nhóm còn ghi counterargument, falsifier và confidence, nên có thể kiểm tra được thay vì chỉ kể xu hướng.

## AI Log và verification

### Q27. AI đã làm phần nào?

AI hỗ trợ tìm và phân loại nguồn, tổng hợp candidates, đề xuất principles/JTBD/predictions, draft memo/slides/notes và chạy audit cơ học. Mức sử dụng được ghi theo từng activity trong §4 của memo.

### Q28. Phần nào là judgment của nhóm?

Nhóm sở hữu lựa chọn 8 milestones, 4 JTBD, strongest force và đúng 3 predictions, cùng trade-off đằng sau chúng. AI tăng tốc synthesis nhưng không thể thay nhóm chịu trách nhiệm defend reasoning.

### Q29. Nhóm kiểm chứng hallucination thế nào?

Audit cuối trích 57 URL duy nhất và mở lại từng URL; 8/8 final milestone có nguồn gốc. Claim community được giới hạn ở sentiment/behavior, customer metrics được ghi self-reported, và link 404 duy nhất đã được thay.

### Q30. Nếu bỏ AI, nhóm có defend bài được không?

Có, nếu nhóm giải thích được causal chain: editor → context → Agent → async/governed workflow → predictions. AI đã làm nhiều ở synthesis và drafting; ownership thật nằm ở khả năng giải thích vì sao mốc được chọn, lực nào mạnh nhất và falsifier nào làm prediction sai.
