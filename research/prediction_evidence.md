# Prediction Evidence — Cursor

Research date: **14/08/2026**. Forecast horizon: **14/02/2027–14/08/2027** (6–12 tháng). Các mục dưới đây tách rõ **FACT** (đã xảy ra), **SIGNAL** (suy luận từ fact) và **PREDICTION** (phán đoán có thể kiểm chứng).

## Current Signals

### Signal 1 — Agent trở thành surface chính

**Date:** 02/04/2026
**Source:** [Cursor 3](https://cursor.com/blog/cursor-3)
**Observed signal (FACT):** Cursor 3 tạo workspace mới xoay quanh nhiều local/cloud agents, multi-repo, handoff và PR review thay vì file editor là trung tâm.
**Connected milestone from CP1:** Cursor 2.0 multi-agent; Background Agent.
**Connected user/JTBD from CP2:** Current engineer muốn delegate task bounded và review output.
**What it may imply (SIGNAL):** Control surface sẽ tiếp tục dịch từ “viết code” sang “điều phối và phê duyệt work.”

### Signal 2 — Always-on workflow đã có primitive

**Date:** 05/03/2026
**Source:** [Automations](https://cursor.com/blog/automations)
**Observed signal (FACT):** Agent chạy theo schedule/event từ Slack, Linear, GitHub, PagerDuty hoặc webhook; có sandbox, MCP, memory và tự verify.
**Connected milestone from CP1:** Automations.
**Connected user/JTBD from CP2:** Delegate maintenance/incident/review mà không prompt từng run.
**What it may imply (SIGNAL):** Cursor có đủ primitive để productize pipeline event → change → review, thay vì chỉ phiên chat.

### Signal 3 — Computer use và artifact giảm review cost

**Date:** 24/02/2026
**Source:** [Cloud agents with computer use](https://cursor.com/blog/agent-computer-use)
**Observed signal (FACT):** Cloud agent dùng VM, test UI và trả video/screenshot/log cùng merge-ready PR; Cursor nói hơn 30% PR nội bộ lúc đó đến từ cloud agents.
**Connected milestone from CP1:** Background Agent; multi-agent.
**Connected user/JTBD from CP2:** Ship change có thể kiểm chứng; Anxiety về silent mistakes.
**What it may imply (SIGNAL):** Artifact/risk evidence sẽ trở thành input để quyết định tự merge hay yêu cầu human review.

### Signal 4 — Risk-based autonomy đã thành product

**Date:** 11/06/2026
**Source:** [Auto-review](https://cursor.com/blog/agent-autonomy-auto-review)
**Observed signal (FACT):** Classifier đánh giá tool action theo context; action thấp rủi ro chạy tiếp, action vượt boundary bị thu hẹp/chặn. Cursor nói cùng nguyên lý sẽ áp dụng ở nhiều nơi hơn.
**Connected milestone from CP1:** Enterprise governance; Agent.
**Connected user/JTBD from CP2:** Current buyer cần autonomy nhưng không mất accountability.
**What it may imply (SIGNAL):** Policy động theo risk có thể nối agent execution với review/merge gates.

### Signal 5 — Customer đã tự xây autonomous pipeline

**Date:** 15/04/2026
**Source:** [Amplitude](https://cursor.com/blog/amplitude)
**Observed signal (FACT, customer-reported):** Automations nối feedback/observability/review tới cloud agents; low-risk PR có thể auto-merge, high-risk PR được route tới reviewer.
**Connected milestone from CP1:** Automations; Background Agent; enterprise governance.
**Connected user/JTBD from CP2:** Delegate task và scale throughput có guardrail.
**What it may imply (SIGNAL):** Workflow tiên tiến của customer là candidate để Cursor đóng gói thành first-party product.

### Signal 6 — Cloud runtime là bottleneck và moat

**Date:** 02/06/2026 và 30/07/2026
**Source:** [Cloud-agent lessons](https://cursor.com/blog/cloud-agent-lessons) · [Cloud-agent environment](https://cursor.com/blog/cloud-agent-environment)
**Observed signal (FACT):** Cursor gọi environment là product/operating layer; đầu tư checkpoint/restore, network policy, credentials, self-healing và environment versioning.
**Connected milestone from CP1:** Background Agent; SDK.
**Connected user/JTBD from CP2:** Agent phải chạy test đáng tin trong codebase thật; enterprise lo security/reliability.
**What it may imply (SIGNAL):** Differentiation dịch khỏi model access sang runtime/environment dùng lại trên nhiều surface.

### Signal 7 — Swarm chuyển từ research sang economics có cấu trúc

**Date:** 20/07/2026
**Source:** [Agent swarms and model economics](https://cursor.com/blog/agent-swarm-model-economics)
**Observed signal (FACT):** Cursor thử planner–worker mixes, shared context và orchestration; chất lượng gần nhau nhưng chi phí khác lớn, worker chiếm phần lớn token.
**Connected milestone from CP1:** Cursor 2.0 multi-agent + Composer model.
**Connected user/JTBD from CP2:** Repo-scale migration/maintenance và parallel delegation.
**What it may imply (SIGNAL):** Router có thể phát triển từ chọn một model/request sang chọn model theo vai trò trong multi-agent task.

### Signal 8 — Router biến model choice thành economic layer

**Date:** 22/07/2026
**Source:** [Cursor Router](https://cursor.com/blog/router)
**Observed signal (FACT):** Router phân loại request, có Cost/Balance/Intelligence, admin policy và chạy trên desktop/web/iOS/CLI/SDK; Teams bật mặc định. Cursor dùng satisfaction/keep-rate và cost per commit để đánh giá.
**Connected milestone from CP1:** Cursor Router candidate; Composer model; SDK.
**Connected user/JTBD from CP2:** Pricing anxiety và buyer cần budget; Pull phải vượt bundle của model providers.
**What it may imply (SIGNAL):** Cursor sẽ giảm manual model selection và bán outcome/cost governance thay vì chỉ access model.

### Signal 9 — Cursor-owned model là route cost-efficient

**Date:** 18/05/2026
**Source:** [Composer 2.5](https://cursor.com/composer)
**Observed signal (FACT):** Cursor định vị Composer là model price-efficient cho long-running agents và mở qua SDK.
**Connected milestone from CP1:** Composer model trong Cursor 2.0; SDK.
**Connected user/JTBD from CP2:** Agent dài cần economics dự đoán được.
**What it may imply (SIGNAL):** Cursor có incentive route workload volume cao về model của mình, giữ frontier models cho planning/judgment.

### Signal 10 — Organization đã là control hierarchy

**Date:** 03/06/2026
**Source:** [Organizations for Enterprise](https://cursor.com/blog/organizations)
**Observed signal (FACT):** Org → teams → groups quản lý identity, model access, spend, agent permission và analytics; Cursor công khai sẽ thêm policy controls.
**Connected milestone from CP1:** Enterprise governance; SDK.
**Connected user/JTBD from CP2:** Buyer/enabler là platform/security/engineering leader, khác early adopter cá nhân ở accountability.
**What it may imply (SIGNAL):** Policy sẽ được định nghĩa ở org rồi áp xuyên desktop, cloud, Automation và SDK.

### Signal 11 — Review/approval đã rời desktop

**Date:** 17/07/2026 và 29/07/2026
**Source:** [Latest changelog](https://cursor.com/changelog)
**Observed signal (FACT):** Slack agent hiển thị plan, làm multi-repo/cross-channel; iPad/iPhone có inbox, full-PR review, checks, approvals và merge.
**Connected milestone from CP1:** Background Agent; Automations; Distribution/SDK.
**Connected user/JTBD from CP2:** User muốn delegate rồi can thiệp tại decision point thay vì theo dõi từng token.
**What it may imply (SIGNAL):** Cursor đang xây review queue/control plane đa surface, không chỉ IDE.

### Signal 12 — Competitors đã bundle cùng interaction model

**Date:** 01/04–14/05/2026
**Source:** [GitHub Copilot cloud agent](https://github.blog/changelog/2026-04-01-research-plan-and-code-with-copilot-cloud-agent/) · [GitHub Copilot app](https://github.blog/changelog/2026-05-14-github-copilot-app-is-now-available-in-technical-preview/) · [OpenAI Codex app](https://openai.com/index/introducing-the-codex-app/)
**Observed signal (FACT):** GitHub đặt agent cạnh issue/PR/repo và OpenAI bundle multi-agent/automation trong ChatGPT subscription.
**Connected milestone from CP1:** Wrapper → Moat; Workflow Moat; Distribution.
**Connected user/JTBD from CP2:** Habit giữ user trong VS Code/GitHub; nếu Pull ngang nhau, bundle làm giảm switching incentive.
**What it may imply (SIGNAL):** Cursor phải defend bằng cross-model economics, runtime, policy và integrated workflow—not feature parity.

## Prediction Candidates

Điểm mỗi candidate: Specificity + CP1 + CP2 + Current signal + Falsifiability + Strategic importance, mỗi tiêu chí `/5`, tổng `/30`.

| # | Prediction candidate | Type | S | CP1 | CP2 | Signal | F | Strategic | Total | Keep/Drop |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---|
| 1 | Risk-tiered lifecycle từ event đến verified PR và auto-merge cho low-risk change | Product/workflow | 5 | 5 | 5 | 5 | 5 | 5 | **30** | **KEEP** |
| 2 | Một org policy/control plane áp xuyên desktop, cloud, Automations và SDK | Enterprise/segment | 5 | 5 | 5 | 5 | 5 | 5 | **30** | **KEEP** |
| 3 | Router thành default economic layer; Composer xử lý workload cost-sensitive | Monetization/moat | 5 | 4 | 5 | 5 | 5 | 5 | **29** | **KEEP** |
| 4 | Planner–worker swarm được productize cho repo-scale migration | Agent strategy | 5 | 4 | 4 | 4 | 5 | 5 | 27 | DROP: current evidence vẫn chủ yếu research |
| 5 | Versioned/self-healing agent environment thành artifact dùng lại trên mọi surface | Platform | 5 | 4 | 4 | 5 | 4 | 5 | 27 | DROP: overlap với control-plane prediction |
| 6 | Cursor mở rộng local pricing sang thêm ≥2 emerging markets | Monetization/segment | 5 | 2 | 3 | 3 | 5 | 3 | 21 | DROP: một India launch chưa đủ pattern |
| 7 | Mobile trở thành surface khởi tạo/review chính cho cloud agents | Distribution | 4 | 4 | 4 | 4 | 4 | 3 | 23 | DROP: strategic depth thấp hơn top 3 |
| 8 | Cursor hỗ trợ deploy/rollout first-party ngoài PR | Workflow expansion | 4 | 4 | 4 | 3 | 5 | 5 | 25 | DROP: evidence trực tiếp còn yếu; gộp boundary vào falsifier P1 |
| 9 | Cursor mở rộng core segment sang PM/design/QA | Segment expansion | 4 | 3 | 3 | 3 | 5 | 3 | 21 | DROP: evidence tập trung ở một customer |
| 10 | Marketplace/plugin trở thành distribution channel có monetization | Platform/business | 4 | 3 | 3 | 3 | 4 | 4 | 21 | DROP: thiếu pricing/creator-economy signal |

Ba lựa chọn final khác nhau: **P1** thay đổi workflow, **P2** thay đổi buyer/control layer, **P3** thay đổi economics và cách Cursor defend trước model-provider bundling. Nếu một prediction sai, hai prediction còn lại vẫn có thể đúng.

## Final Prediction 1 — Product / Workflow

### Prediction

**Trước 14/08/2027, Cursor sẽ GA hoặc enterprise-preview một workflow first-party dùng risk policy để nhận event, sửa và tự verify code, mở PR, rồi tự merge ít nhất nhóm change low-risk; high-risk change được route tới human approval cùng artifact/evidence.**

### Supporting Milestone — CP1

Background Agent (06/2025) → Automations (03/2026) → enterprise governance tạo đủ execution, trigger và control primitives.

### User/JTBD Support — CP2

JTBD “delegate task bounded với guardrail”; Pull là closed loop, nhưng Anxiety về silent mistakes buộc autonomy phải risk-tiered.

### Current Signal

Auto-review đã classify risk trong agent loop; Automations đã trigger/verify; Amplitude đã tự nối pipeline và auto-merge low-risk PR. Cursor có incentive productize pattern đang do customer tự ghép.

### Competitive Context

GitHub sở hữu issue/PR distribution và cloud agent. Cursor cần đi sâu hơn vào policy + verification xuyên tool, không chỉ tạo PR.

### Why Now / Why Cursor

Primitive đã tồn tại và customer behavior chứng minh readiness; Cursor sở hữu agent, sandbox, artifact, Bugbot và hooks đủ để đóng loop trong 6–12 tháng.

### User & Business Impact

Engineer chuyển từ prompt từng task sang quản lý exception/review queue; Cursor tăng cloud-agent consumption và trở thành workflow infrastructure khó thay hơn editor subscription.

### Strongest Argument Against

Auto-merge production code tạo liability và review debt; Cursor có thể giữ merge là customer-configured integration thay vì first-party product.

### Falsifier

Đến 14/08/2027, Cursor vẫn yêu cầu user khởi tạo từng run hoặc không có first-party risk policy quyết định low-risk auto-merge/human review.

### Confidence

**High — 75%.**

## Final Prediction 2 — Enterprise / Segment

### Prediction

**Trước 14/08/2027, Cursor sẽ cho organization định nghĩa ít nhất một policy về agent permission/network hoặc spend/model một lần và enforce + audit policy đó trên cả desktop agent, cloud agent, Automations và SDK/service-account runs.**

### Supporting Milestone — CP1

Enterprise governance (10/2025) tạo hooks/rules/audit; Automations và SDK (03–04/2026) làm surface phân mảnh, buộc governance đi theo organization thay vì app.

### User/JTBD Support — CP2

Current buyer là platform/security/engineering leader; barrier chính là policy, privacy, cost và accountability khi rollout từ cá nhân sang organization.

### Current Signal

Organizations đã gom identity, groups, model access, spend và agent permission; Auto-review nói cùng principle sẽ mở rộng tới nhiều nơi; Router đã có admin control xuyên nhiều clients.

### Competitive Context

Claude Code và Codex bundle admin/compliance với model subscription; GitHub có identity/repo advantage. Cursor cần vendor-neutral control plane để giữ enterprise differentiation.

### Why Now / Why Cursor

Surface count đã vượt desktop, trong khi enterprise customers không thể vận hành bốn policy silo. Cursor đã có hierarchy và audit foundation nên đây là bước adjacent, không phải category leap.

### User & Business Impact

Team rollout nhanh hơn và developer nhận guardrail nhất quán ở mọi entry point; Cursor tăng seat/usage expansion và enterprise switching cost ở workflow/policy, không cần data lock-in.

### Strongest Argument Against

SDK/self-hosted environments có thể quá mở để enforce đồng nhất; enterprise có thể giữ policy ở CI, cloud IAM hoặc third-party gateway.

### Falsifier

Đến 14/08/2027, desktop, cloud, Automations và SDK vẫn có cấu hình/audit silo và không có policy org-level enforce được trên cả bốn surface.

### Confidence

**High — 80% (most confident).**

## Final Prediction 3 — Monetization / Moat

### Prediction

**Trước 14/08/2027, Auto/Router sẽ là default cho cả Teams và individual paid plans; admin/user có budget hoặc optimization policy theo task, và Composer/Cursor-owned model sẽ là route mặc định cho phần lớn workload cost-sensitive.**

### Supporting Milestone — CP1

Composer model (10/2025) cho Cursor sở hữu một phần model economics; SDK (04/2026) mở workload programmatic; Router (07/2026 candidate milestone) đã biến routing thành product layer.

### User/JTBD Support — CP2

Pricing unpredictability là Anxiety lớn; team cần delegate task dài mà chi phí không tăng theo việc chọn frontier model thủ công.

### Current Signal

Router đã default cho Teams, có Cost/Balance/Intelligence và cost-per-commit framing; Composer được định vị cho long-running agent; swarm research cho thấy planner/worker model mix thay đổi cost rất lớn.

### Competitive Context

OpenAI/Anthropic bundle model + agent trong subscription. Cursor không thắng bằng độc quyền model; router trung lập cộng model riêng giúp tối ưu outcome/cost và giảm phụ thuộc vendor.

### Why Now / Why Cursor

Agent volume làm token cost thành buyer problem ngay bây giờ; Cursor có production routing traffic, keep-rate signal, caching và model/harness để tối ưu toàn loop.

### User & Business Impact

User bớt chọn model và bill dễ kiểm soát hơn; Cursor cải thiện gross margin/price differentiation đồng thời giữ quyền chọn frontier model.

### Strongest Argument Against

User power-user muốn tự chọn model và có thể mất trust nếu route bị ẩn; model providers có thể giảm giá/bundle nhanh hơn lợi ích routing.

### Falsifier

Đến 14/08/2027, paid individual vẫn mặc định chọn model thủ công, Router không có task-level budget/optimization policy, hoặc Cursor-owned model không phải route thường dùng cho cost-sensitive work.

### Confidence

**Medium-high — 70%.**

## Most Confident Prediction

**Prediction 2 — unified enterprise control plane (80%).** Đây là pattern lịch sử mạnh nhất (enterprise governance → Automations/SDK), gắn trực tiếp với barrier lớn nhất của current buyer (control/accountability), và có signal rõ nhất: Organizations đã là hierarchy GA, Cursor công khai tiếp tục thêm policy controls, còn Auto-review/Router cung cấp policy primitives cần mở rộng xuyên surface.

## Critical Assumption

Enterprise sẽ tiếp tục tăng delegation và muốn Cursor—thay vì CI/IAM gateway hoặc model provider—là nơi quản trị agent. Nếu ROI không vượt review burden, một security incident lớn làm autonomy co lại, hoặc enterprise ép toàn bộ policy lên lớp hạ tầng ngoài Cursor, Prediction 2 sẽ gãy dù sản phẩm agent vẫn tiến bộ.

## CP3 Audit & Rubric

- [x] 12 current signals, có date/source và tách FACT–SIGNAL–PREDICTION
- [x] 10 candidates được score `/30`; đúng 3 final predictions
- [x] Horizon 6–12 tháng; mỗi prediction specific và falsifiable
- [x] Mỗi prediction nối CP1 → CP2 → current/competitive signal
- [x] Có Why Now, Why Cursor, user/business impact, counterargument và falsifier
- [x] Chọn most confident prediction và critical assumption

| Prediction | Specificity | Evidence & reasoning từ CP1–CP2 | Total |
|---|---:|---:|---:|
| 1 — Policy-gated PR lifecycle | 5/5 | 5/5 | **10/10** |
| 2 — Enterprise control plane | 5/5 | 5/5 | **10/10** |
| 3 — Router economic layer | 5/5 | 5/5 | **10/10** |
| **TOTAL CP3** |  |  | **30/30** |
