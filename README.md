# K3 LAB16 — Track 1 AI Product Teardown

## Product

Cursor

## Members

- Nguyễn Quang Huy — 2A202601873
- Lăng Thị Phương Huế — 2A202601915
- Cao Các Tường — 2A202601236
- Đinh Lê Quỳnh Phương — 2A202601865
- Nguyễn Khánh Toàn — 2A202601843

## Checkpoint CP0 — Chọn sản phẩm & khai phá nguồn

### Điều kiện 1 — AI là core experience

Cursor là **AI-native**, không chỉ AI-enabled. AI không phải lớp hỗ trợ gắn lên một value proposition độc lập: các primitive chính của sản phẩm là Tab completion, chat có codebase context, inline edit, Composer/Agent, terminal/test loop và cloud/background agents. Nếu bỏ AI, phần còn lại chủ yếu là một bản editor tương thích VS Code; value proposition “chuyển ý định thành thay đổi code có thể kiểm chứng ngay trong workflow” biến mất.

### Điều kiện 2 — Có đủ dữ liệu timeline

- **18 milestone candidates** đã được thu thập trước khi lọc.
- Khoảng thời gian: **24/03/2023–22/07/2026**.
- Bao phủ launch, privacy, VS Code migration, chat/context, inline edit, Composer, Agent, background agent, multi-agent, enterprise, automations, SDK và model routing.
- Xem [research/milestone_candidates.md](research/milestone_candidates.md).

### Điều kiện 3 — Use case & JTBD rõ

Use case lõi: professional developer thay đổi codebase thật, nhiều file, cần giữ context, chạy test và review output mà không liên tục chuyển giữa chatbot, editor và terminal.

JTBD candidates:

1. **Khi tiếp cận codebase lạ, tôi muốn hiểu kiến trúc và dependency mà không tự gom từng mẩu context, để bắt đầu thay đổi đúng chỗ.**
2. **Khi phải giao feature hoặc fix bug dưới áp lực thời gian, tôi muốn chuyển ý định thành thay đổi nhiều file có thể review và kiểm chứng, để ship nhanh hơn nhưng vẫn kiểm soát chất lượng.**
3. **Khi có công việc kỹ thuật lặp lại hoặc kéo dài, tôi muốn giao task cho agent chạy nền với guardrail, để tập trung vào quyết định có leverage cao hơn.**
4. **Khi triển khai AI coding cho cả team, tôi muốn agent tuân theo context, rules và policy chung, để tăng tốc mà không mất governance.**

Primary JTBD là candidate 2; nó mô tả tiến bộ người dùng cần đạt, không phụ thuộc một feature cụ thể.

## CP0 Deliverables

- [Source audit](research/sources.md)
- [Milestone candidates](research/milestone_candidates.md)
- [User/JTBD research](research/user_research.md)

## CP0 Status

**CP0: PASS**

- AI core: PASS
- Milestone candidates ≥ 12: PASS (18)
- Ít nhất 3 loại nguồn: PASS (official/primary, founder interview, community/review, independent research)
- Source thật và hỗ trợ đúng claim: PASS
- Use case/JTBD: PASS
- Product và thành viên trong README: PASS

## Checkpoint CP1 — Timeline & Revert nguyên lý

CP1 chọn **8 product decisions** từ 18 candidates và dựng trajectory:

```text
AI-first editor → codebase context → Agent → async delegation
→ multi-agent/model layer → enterprise governance
→ Automations → programmable agent infrastructure
```

Deliverables:

- [§1 Timeline trong memo](memo.md)
- [Candidate scoring và KEEP/DROP](research/milestone_candidates.md)
- [Principle reverts và reusable patterns](research/principle_reverts.md)
- [Source audit](research/sources.md)

**CP1: PASS — 28/30 self-assessment**
