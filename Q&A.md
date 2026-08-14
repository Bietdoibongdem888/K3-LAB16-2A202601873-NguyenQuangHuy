# Q&A — Cursor Product Teardown

## CP2 — User Segments & JTBD

### Q1. Early adopter cụ thể là ai?

Product/software engineer 2–7 năm tại startup nhỏ hoặc product team tốc độ cao; dùng VS Code hằng ngày, đã dùng Copilot + ChatGPT, có quyền tự chọn editor và đủ kỹ năng review output AI sai.

### Q2. Evidence nào chứng minh?

HN launch 03/2023 cho thấy audience biết Copilot, so trực tiếp với editor cũ và chấp nhận thử workflow mới; founder nói speedup cần editor-level changes. One-click VS Code import cho thấy target đã có settings/extensions; community comparison ghi nhận context/integration là lý do chuyển.

### Q3. Current user khác early adopter ở đâu?

Current primary vẫn là developer nhưng làm trong team trên production code với task phức tạp hơn và risk tolerance thấp hơn. Adoption có company payment, rollout, shared rules, privacy, audit và budget; buyer gồm engineering/platform/security leader.

### Q4. JTBD quan trọng nhất là gì?

Khi phải giao feature, bug fix, migration hoặc refactor trong codebase production, user muốn biến intent thành diff nhiều file và đóng feedback loop để ship nhanh hơn nhưng vẫn review, test và chịu trách nhiệm chất lượng.

### Q5. Tại sao đó là JTBD chứ không phải feature?

Job “ship một change có thể kiểm chứng” vẫn tồn tại nếu Cursor biến mất. Agent, Composer, Tab hay Chat chỉ là các solution cạnh tranh để hoàn thành job đó.

### Q6. Trước Cursor user làm job đó bằng gì?

VS Code/JetBrains + manual coding + Copilot completion; copy/paste code và lỗi vào ChatGPT; IDE search/grep/docs; tự áp patch và chạy edit–test–fix trong terminal.

### Q7. Milestone nào làm thay đổi segment?

Codebase context 07/2023 giúp power user hiểu/sửa repo; Agent trong Composer 11/2024 đóng loop task cho professional engineer; Background Agent + enterprise governance 06–10/2025 kết hợp async delegation với rules, sandbox và audit để team/enterprise rollout.

### Q8. Trong Four Forces lực nào mạnh nhất?

Pull: outcome “context → edit nhiều file → test → review” trong một loop. Push có thể được giải một phần bằng tool khác, còn Habit và Anxiety chống lại adoption; vì vậy Pull phải đủ lớn mới khiến user đổi editor.

### Q9. Nếu lực đó biến mất thì sao?

Nếu VS Code/GitHub, Claude Code hoặc Codex đạt loop tương đương với bundle/cost tốt hơn, incentive đổi editor giảm mạnh. Cursor phải dựa vào reliability của context/harness, routing economics và governed team workflow.

### Q10. Điều gì khiến user không chuyển dù product tốt?

Editor/extension muscle memory, remote-dev và team convention; lo output sai hoặc tăng review debt; source-code/privacy/compliance risk; pricing khó dự đoán; procurement và identity/repo stack đã gắn với vendor khác.
