# Prediction Evidence - Cursor

Horizon: **14/08/2026 -> 14/08/2027**. Đây là predictions, không phải roadmap đã xác nhận.

## Prediction 1 - Policy-gated self-driving PR lifecycle

**Prediction:** Trước 14/08/2027, Cursor sẽ phát hành ít nhất một workflow first-party (GA hoặc enterprise preview) cho phép agent nhận event, sửa code, chạy test/UI verification, mở PR và tự merge hoặc kích hoạt rollout dưới policy, không cần prompt cho từng run.

**Falsification:** Không có workflow first-party nào thực hiện được chuỗi trên, hoặc merge/rollout vẫn luôn cần người khởi tạo từng run.

Evidence anchors:

- [Cloud agents with computer use](https://cursor.com/blog/agent-computer-use) nêu rõ hướng “self-driving codebases” và near-term focus vào coordination + learning from past runs.
- [Automations](https://cursor.com/blog/automations) đã có schedule/event triggers, sandbox, MCP và memory.
- [Cloud agent Builds](https://cursor.com/blog/builds) giảm startup/reliability bottleneck; [AIUC-1](https://cursor.com/blog/aiuc-1) thêm guardrails cần cho autonomy.
- User/JTBD link: team muốn giao task dài nhưng anxiety về action sai; policy-gated autonomy giải quyết cả Pull và Anxiety.

Confidence: **High (75%)**.

## Prediction 2 - Router becomes the default economic layer

**Prediction:** Trước 14/08/2027, Auto/Router sẽ trở thành default cho cả individual paid plans lẫn Teams, có budget/policy theo task; Composer hoặc model do Cursor vận hành sẽ là một route mặc định cho workload cost-sensitive.

**Falsification:** Paid individual default vẫn là chọn model thủ công và Router không có task-level budget/policy; Cursor-owned model không xuất hiện trong default routing.

Evidence anchors:

- [Cursor Router](https://cursor.com/changelog) đã phân loại task, có Cost/Balance/Intelligence và admin controls; Teams bật mặc định.
- [Cursor 2.0](https://cursor.com/changelog/2-0) giới thiệu Composer, cho thấy Cursor không muốn chỉ chuyển tiếp model của bên khác.
- [Pricing docs](https://docs.cursor.com/account/pricing) và community feedback về cost/context cho thấy choice overload và bill anxiety là blocker.
- Competitor link: model providers có thể bundle agent; routing đa model là cách Cursor giữ model portability và tối ưu unit economics.

Confidence: **Medium-high (70%)**.

## Prediction 3 - One enterprise control plane across every agent surface

**Prediction:** Trước 14/08/2027, Cursor sẽ hợp nhất identity, permission/network policy, spend limit và audit trail ở cấp organization cho desktop, cloud agents, Automations và SDK; ít nhất một policy sẽ được định nghĩa một lần và enforce trên cả bốn surface.

**Falsification:** Các surface vẫn có admin/policy silo riêng, không có shared audit + enforceable organization policy.

Evidence anchors:

- [Enterprise](https://cursor.com/blog/enterprise): hooks, rules, sandbox, audit.
- [Organizations](https://cursor.com/blog/organizations): budget/model/permission theo cohort và business unit.
- [SDK](https://cursor.com/blog/typescript-sdk): cùng harness chạy local/cloud/self-hosted và nhúng vào CI/product.
- [AIUC-1](https://cursor.com/blog/aiuc-1): governance agent được test định kỳ; enterprise adoption đòi evidence xuyên surface.
- Segment link: current user là engineering organization, khác early adopter cá nhân ở nhu cầu control và accountability.

Confidence: **High (80%) - most confident**.

## Critical assumption

Các tổ chức tiếp tục tăng mức delegation cho coding agents nhưng chỉ khi governance/reliability bắt kịp. Nếu model capability plateau, ROI không vượt review burden, hoặc sự cố bảo mật lớn khiến enterprise quay lại human-in-the-loop chặt, cả ba prediction sẽ chậm hoặc sai.

## Cross-consistency

```text
Timeline: context -> agent -> async -> multi-agent -> automation -> platform/router
Users: individual power user -> governed engineering organization
Predictions: autonomous lifecycle + routing economics + unified governance
```
