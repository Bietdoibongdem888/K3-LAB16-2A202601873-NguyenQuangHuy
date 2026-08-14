# Principle Reverts — Cursor

## 1. Launch editor AI-first — 24/03/2023

### Observation

Cursor public một editor “built for programming with AI”, thay vì chỉ phát hành extension cho editor hiện hữu. Trong thread launch, founder Michael Truell nói các speedup ông kỳ vọng cần thay đổi ở cấp editor, như kết nối terminal/LSP với auto-fix và thay đổi code navigation/understanding.

### Context

Copilot đã chứng minh autocomplete AI có giá trị, nhưng phản ứng sớm trên HN đặt thẳng câu hỏi: tại sao không dùng editor có Copilot? Đó là bài test product thật: editor riêng chỉ hợp lý nếu AI sẽ thay đổi interaction primitive vượt quá giới hạn extension.

### Decision logic

Sở hữu surface cho phép Cursor kiểm soát context, diff, terminal, navigation và sau này là agent loop. Alternative principle là **Workflow Moat**, nhưng ở thời điểm launch causal logic mạnh hơn là **AI-native UX**: product team cần quyền tái cấu trúc cách user lập trình trước khi moat thực sự tồn tại.

### Principle

**AI-native UX** — khi AI thay đổi primitive của công việc, product cần kiểm soát interaction layer đủ sâu; “AI add-on” không còn đủ.

### Reusable pattern

Chỉ build surface mới khi capability tương lai đòi thay đổi object, control và feedback loop cốt lõi; nếu extension vẫn làm được job, một app mới chỉ tăng switching cost.

### Source

- [HN launch thread, 24/03/2023](https://news.ycombinator.com/item?id=35285047)
- [Michael Truell on the decision to own the editor](https://a16z.com/podcast/michael-truell-how-cursor-builds-at-the-speed-of-ai/)

## 2. Codebase-wide context — 19/07/2023

### Observation

Cursor thêm khả năng kiểm soát context building cho chat toàn codebase và cải thiện flow để Cmd+K tạo code không có linter errors.

### Context

Chat v2 và inline Cmd+K trước đó đã đưa AI vào editor, nhưng user vẫn phải chỉ định file/code/docs. Bottleneck không chỉ là model sinh code, mà là model nhìn thấy đúng phần repo và nhận feedback từ linter.

### Decision logic

Cursor chuyển differentiation từ “có chat trong IDE” sang “chat hiểu hệ thống đang được sửa”. Alternative principle là **Workflow Moat**, nhưng **Context > Model** giải thích trực tiếp hơn vì capability mới thay đổi input và grounding của cùng model.

### Principle

**Context > Model** — trong task domain-specific, đúng context và feedback có thể tạo nhiều giá trị hơn việc chỉ đổi sang model mạnh hơn.

### Reusable pattern

Trước khi tăng model cost, hãy product hóa việc thu thập, hiển thị và sửa context; biến context từ prompt thủ công thành một phần có thể điều khiển của UX.

### Source

- [Advanced context for codebase-wide chat, 19/07/2023](https://cursor.com/changelog/0-2-49)

## 3. Agent trong Composer — 24/11/2024

### Observation

Cursor đưa một early Agent vào Composer: agent có thể tự chọn context, dùng terminal, tạo thay đổi nhiều file và hiển thị inline diffs trong sidebar.

### Context

Repo context đã khiến AI đủ hữu ích cho task lớn hơn một completion. Nhưng user vẫn phải điều phối chuỗi “tìm file → sửa → chạy lệnh → đọc lỗi → sửa lại”. Terminal access và autonomous context selection khép chuỗi đó thành một goal-seeking loop.

### Decision logic

Decision không phải “thêm feature Agent”; nó dời ranh giới trách nhiệm từ user điều phối từng thao tác sang AI thực hiện task, còn user giao intent và review output. **Assistant → Agent** giải thích bước nhảy này tốt hơn AI-native UX chung chung.

### Principle

**Assistant → Agent** — khi AI đã đáng tin ở các thao tác nhỏ, bước product tiếp theo là mở rộng phạm vi delegation và cho nó công cụ để tự đóng loop.

### Reusable pattern

Không tăng autonomy chỉ bằng prompt dài hơn. Cần đồng thời có context selection, tools, observable state, rollback/review và success feedback.

### Source

- [New Composer UI, Agent, Commit Messages, 24/11/2024](https://cursor.com/changelog/0-43-x)

## 4. Background Agent GA + BugBot — 04/06/2025

### Observation

Cursor 1.0 đưa Background Agent remote ra GA cho mọi user và đưa BugBot vào PR review trên GitHub.

### Context

Cursor cho biết early signals của Background Agent là tích cực. Foreground agent vẫn chiếm màn hình và sự chú ý; remote execution cho phép user tiếp tục việc khác, còn BugBot đặt output vào review workflow nơi team vốn ra quyết định.

### Decision logic

Giá trị không chỉ là agent “mạnh hơn” mà là lấy lại thời gian chú ý và xử lý song song. Alternative principle là Distribution vì BugBot vào GitHub, nhưng **x10 Value** giải thích tốt hơn lý do user chấp nhận delegation remote: benefit chuyển từ tiết kiệm keystroke sang tiết kiệm một block thời gian.

### Principle

**x10 Value** — switching/delegation xảy ra khi improvement thay đổi đơn vị giá trị, từ thao tác nhanh hơn sang công việc hoàn tất trong lúc user làm việc khác.

### Reusable pattern

Khi synchronous AI đã tốt, async execution có thể tạo step-change lớn hơn tăng thêm vài điểm quality; hãy đo thời gian chú ý được trả lại, không chỉ token hay code generated.

### Source

- [Cursor 1.0, 04/06/2025](https://cursor.com/changelog/1-0)

## 5. Cursor 2.0: multi-agent + Composer model — 29/10/2025

### Observation

Cursor 2.0 cho phép quản lý và chạy tối đa tám agent song song trong worktree/remote isolation, đồng thời giới thiệu Composer — agentic coding model đầu tiên của Cursor.

### Context

Khi một agent có thể làm task dài, bottleneck chuyển sang orchestration, conflict và cost/latency. Worktree isolation giải quyết xung đột; model riêng được Cursor công bố là nhanh hơn các model tương đương, cho thấy application bắt đầu tối ưu cả harness lẫn model economics.

### Decision logic

Cursor đi khỏi vị thế UI gọi model bên thứ ba: product gồm control plane, isolation, context/harness và một model riêng. Alternative principle là Model Commoditization, nhưng **Wrapper → Moat** mô tả đầy đủ hơn phản ứng chiến lược.

### Principle

**Wrapper → Moat** — khi model access dễ bị sao chép, differentiation phải dịch sang orchestration, workflow, context, runtime và phần model được tối ưu cho chính harness.

### Reusable pattern

AI application chỉ nên sở hữu model khi model-harness co-design cải thiện latency/cost/quality cho job cụ thể; nếu không, multi-model portability thường có giá trị hơn vertical integration.

### Source

- [Cursor 2.0, 29/10/2025](https://cursor.com/changelog/2-0)

## 6. Enterprise governance layer — 31/10/2025

### Observation

Cursor ra mắt Hooks, Team Rules, upgraded analytics, Audit Log và Sandbox Mode cho enterprise; Hooks có thể log hoặc chặn action và Team Rules đưa shared context/best practice tới toàn tổ chức.

### Context

Nguồn chính thức nói Cursor đã được dùng tại hàng chục nghìn enterprise. Ở quy mô này, “agent tạo code tốt” chưa đủ: buyer cần policy enforcement, observability, secrets protection, shared conventions và auditability.

### Decision logic

Decision đổi success metric từ output cá nhân sang adoption an toàn ở cấp tổ chức. Alternative principle là Switching Cost, nhưng **Define Good** causal hơn: enterprise chỉ gọi agent là “good” khi capability đi cùng control và evidence.

### Principle

**Define Good** — success của AI product phải bao gồm constraint của buyer; trong enterprise, quality = useful output + policy compliance + traceability + controllable risk.

### Reusable pattern

Muốn đi từ prosumer sang enterprise, đừng chỉ thêm SSO/billing. Hãy biến hành vi AI thành thứ có thể quan sát, giới hạn và kiểm toán.

### Source

- [Introducing Cursor for Enterprise, 31/10/2025](https://cursor.com/blog/enterprise)

## 7. Automations — 05/03/2026

### Observation

Cursor cho phép agent chạy theo schedule hoặc event từ Slack, Linear, GitHub, PagerDuty và webhook; agent khởi động sandbox, dùng MCP/model được cấu hình và có memory giữa các run.

### Context

Cursor nêu một bottleneck cụ thể: agent làm tốc độ tạo code tăng, nhưng review, monitoring và maintenance chưa tăng tương ứng. Event-driven automation kéo agent vào toàn software lifecycle thay vì chỉ phản hồi prompt trong editor.

### Decision logic

Cursor biến agent từ công cụ được “mở lên dùng” thành worker luôn nằm trong operational workflow. Alternative principle là Assistant → Agent, nhưng **Workflow Moat** sâu hơn vì trigger, integration và recurring history tạo stickiness ngoài capability của một run.

### Principle

**Workflow Moat** — AI trở nên bền vững khi được gọi bởi event thật, dùng context thật và trả output vào nơi công việc tiếp tục.

### Reusable pattern

Sau interactive agent, bước platform mạnh là event-driven agent. Chọn workflow có trigger rõ, feedback đo được và failure path có owner; tránh automation chỉ vì có thể.

### Source

- [Build agents that run automatically, 05/03/2026](https://cursor.com/blog/automations)

## 8. Cursor SDK — 29/04/2026

### Observation

Cursor public SDK cho phép tổ chức dùng cùng runtime, harness và models của Cursor từ code, chạy local hoặc cloud và nhúng agent vào CI/CD hay sản phẩm riêng.

### Context

Nguồn chính thức mô tả coding agent đang chuyển từ interactive tool của cá nhân sang programmatic infrastructure của organization. Khi teams muốn gọi agent từ pipeline và internal application, editor không còn là distribution surface đủ rộng.

### Decision logic

SDK biến capability nội bộ thành platform primitive và cho Cursor xuất hiện bên trong workflow/sản phẩm khác. Alternative principle là Wrapper → Moat, nhưng **Distribution** giải thích trực tiếp hơn việc chuyển từ destination app thành embedded infrastructure.

### Principle

**Distribution** — khi core capability đã ổn định, SDK/API mở thêm jobs và surfaces mà app chính không thể sở hữu trực tiếp.

### Reusable pattern

Chỉ platform hóa sau khi đã có một opinionated product loop chạy tốt; SDK nên export lợi thế thật của harness/runtime, không chỉ bọc endpoint model.

### Source

- [Build programmatic agents with the Cursor SDK, 29/04/2026](https://cursor.com/blog/typescript-sdk)

## Pattern xuyên suốt

```text
Own the interaction surface
→ own context
→ give AI tools
→ move execution async
→ orchestrate many agents
→ govern organization-wide use
→ attach agents to events
→ export the harness as infrastructure
```

Pattern mạnh nhất: **Khi user đã tin AI ở task nhỏ, hãy mở rộng delegation bằng context, tools, isolated runtime và governance — không chỉ bằng model mạnh hơn.**
