# Presentation Notes

Tổng thời gian mục tiêu: **~6 phút 10 giây**.

## Slide 1 — Cursor AI Product Teardown

**Thời gian:** ~25s

**Nói:** Cursor bắt đầu như một editor xây quanh AI, nhưng thesis của nhóm không dừng ở “AI giúp viết code”. Timeline cho thấy Cursor liên tục mở rộng đơn vị công việc: từ completion, sang change nhiều file, rồi sang task và software work có thể giao cho agent.

**Chuyển:** Để thấy vì sao trajectory này đáng phân tích, trước hết cần trả lời tại sao Cursor là AI-native.

## Slide 2 — Vì sao Cursor đáng teardown?

**Thời gian:** ~30s

**Nói:** Nếu bỏ AI, value proposition chính của Cursor biến mất; đây không phải editor thường có thêm chatbot. User problem là đóng loop từ intent tới diff, test và review mà không tự vận chuyển context giữa nhiều tool. Sản phẩm cũng có 18 milestone candidates và một tension Product Sense rõ: model mạnh có thể commoditize, vậy moat nằm ở đâu?

**Chuyển:** Hai slide timeline tiếp theo cho thấy Cursor đã trả lời câu hỏi đó qua product decisions.

## Slide 3 — Timeline I: Sở hữu workflow

**Thời gian:** ~45s

**Nói:** Năm 2023, Cursor chọn sở hữu editor để thay interaction layer, rồi đầu tư vào codebase context. Tháng 11/2024 là mốc mạnh nhất: Agent tự chọn context, dùng terminal và trả diff, biến AI từ assistant thành actor trong feedback loop. Cursor 1.0 sau đó đưa task ra background, trả lại một block attention thay vì chỉ tiết kiệm keystroke.

**Chuyển:** Khi delegation tăng, bottleneck chuyển từ khả năng sinh code sang orchestration, control và distribution.

## Slide 4 — Timeline II: Mở rộng control plane

**Thời gian:** ~45s

**Nói:** Cursor 2.0 thêm multi-agent và model Composer; enterprise governance thêm rules, hooks, sandbox và audit. Automations đưa agent vào event-driven workflow; SDK đưa cùng harness ra CI/CD và sản phẩm khác. Đây không phải bốn feature rời — chúng mở rộng cùng một control plane từ editor sang organization và platform.

**Chuyển:** Từ tám quyết định, nhóm rút ra bốn nguyên lý có thể dùng cho AI product khác.

## Slide 5 — Bốn nguyên lý xuyên timeline

**Thời gian:** ~45s

**Nói:** Một, khi AI đổi primitive công việc, product phải sở hữu interaction layer đủ sâu. Hai, context và feedback đúng thường tạo giá trị hơn chỉ đổi model. Ba, delegation chỉ tăng khi có tool, observable state và review path. Bốn, moat bền nằm ở workflow, runtime và governance — nơi model capability được biến thành outcome có thể kiểm soát.

**Chuyển:** Các quyết định này cũng làm tệp user thay đổi, nhưng không theo hướng developer sang non-developer.

## Slide 6 — User shift và JTBD

**Thời gian:** ~50s

**Nói:** Early adopter là VS Code power user ở startup, đã dùng Copilot và ChatGPT, chấp nhận editor non để đổi lấy tốc độ. Current primary vẫn là professional engineer, nhưng làm production codebase trong team và có buyer về platform/security. JTBD chính là ship một change nhiều file có thể kiểm chứng; Agent và governance mở rộng job từ hỗ trợ cá nhân sang delegation có guardrail.

**Chuyển:** Việc user có đổi workflow hay không phụ thuộc vào bốn lực, không chỉ capability.

## Slide 7 — Four Forces: Pull phải thắng Habit và Anxiety

**Thời gian:** ~50s

**Nói:** Push là workflow cũ phân mảnh; Pull là closed loop context–edit–test–review. Anxiety là output sai, security và bill khó đoán; Habit là editor muscle memory và team convention. Nhóm chọn Pull là lực mạnh nhất vì Push có thể được giải một phần bằng tool khác, còn Habit và Anxiety đều chống adoption. Nếu competitor đạt closed loop tương đương, lý do đổi editor giảm mạnh.

**Chuyển:** Chính tension giữa delegation và control dẫn tới ba dự đoán 6–12 tháng.

## Slide 8 — Ba dự đoán có falsifier

**Thời gian:** ~65s

**Nói:** Một, Cursor productize policy-gated PR lifecycle: low-risk có thể auto-merge, high-risk về human approval. Hai, organization có một control plane enforce policy trên desktop, cloud, Automations và SDK. Ba, Router trở thành economic layer mặc định, dùng budget policy và model riêng cho workload cost-sensitive. Mỗi dự đoán nối một chuỗi milestone với JTBD hoặc barrier, và đều có mốc 14/08/2027 để kiểm tra.

**Chuyển:** Trong ba dự đoán, nhóm tự tin nhất với control plane enterprise, nhưng có một giả định then chốt.

## Slide 9 — Big bet và điều có thể làm thesis gãy

**Thời gian:** ~40s

**Nói:** Unified enterprise control plane có confidence 80% vì hierarchy và policy primitives đã hiện hữu, còn surface đang phân mảnh nhanh. Giả định là enterprise muốn Cursor làm nơi quản trị agent. Thesis gãy nếu review burden vượt ROI, có security incident khiến autonomy co lại, hoặc policy được đẩy hoàn toàn xuống CI/IAM hay model provider.

**Chuyển:** Từ case Cursor, nhóm rút ra ba bài học ngắn cho bất kỳ AI product nào.

## Slide 10 — Takeaway

**Thời gian:** ~25s

**Nói:** Model capability mở cửa, nhưng workflow mới giữ giá trị. Context là một product layer, không chỉ chi tiết kỹ thuật. Và khi trust tăng, UX chuyển từ assistance sang delegation — nhưng control và verification phải tăng cùng tốc độ.

**Kết:** Đó là lý do nhóm nhìn Cursor không chỉ như AI editor, mà như một control plane đang hình thành cho software work.
