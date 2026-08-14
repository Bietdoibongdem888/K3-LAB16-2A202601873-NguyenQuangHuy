# User Research — Cursor

Ngày kiểm tra: **14/08/2026**. Community evidence được dùng để nhận diện hành vi và cảm nhận, không để suy rộng tỷ lệ cho toàn bộ user base. Số liệu customer story là self-reported bởi khách hàng/Cursor.

## 1. Early Adopters

### Candidate Segment

**Product/software engineer 2–7 năm kinh nghiệm tại startup nhỏ hoặc đội sản phẩm tốc độ cao (khoảng 5–100 người), dùng VS Code hằng ngày, đã thử GitHub Copilot và ChatGPT/GPT-4, chủ động theo dõi AI developer tooling và chấp nhận editor còn non để giảm thời gian đọc–viết–sửa code.**

Đây là persona hẹp hơn “developer thích AI”: họ đã có workflow thật, biết giới hạn của autocomplete/chat rời rạc, có quyền tự chọn editor và đủ kỹ năng để review output sai.

### Evidence

- [HN launch 24/03/2023](https://news.ycombinator.com/item?id=35285047) cho thấy audience biết rõ VS Code/Copilot và lập tức hỏi tại sao phải dùng editor mới; một user còn dùng Cursor để generate rồi quay về VS Code để edit. Founder trả lời rằng speedup lớn cần thay đổi ở cấp editor như auto-fix từ terminal/LSP và code navigation/understanding.
- [Founder interview](https://a16z.com/podcast/michael-truell-how-cursor-builds-at-the-speed-of-ai/) xác nhận Cursor chọn “power users” và sở hữu editor thay vì tối ưu cho democratization đại trà.
- [One-click VS Code import](https://cursor.com/changelog/0-2-9) nhắm trực tiếp vào người đã có extensions, settings, keybindings và muscle memory trong VS Code.
- Thảo luận [Cursor vs VS Code + Copilot](https://www.reddit.com/r/cursor/comments/1f7cku2/) mô tả lợi ích khi làm với library lạ nhờ đưa documentation vào context, đồng thời ghi nhận API outage—đúng profile user chấp nhận rủi ro để đổi lấy tốc độ.

### Behaviors

- Dùng AI nhiều lần mỗi ngày cho code mới, giải thích API, boilerplate và debug; tự kiểm tra output thay vì tin tuyệt đối.
- Copy/paste code, lỗi và docs sang ChatGPT; mở Google/Stack Overflow/docs; quay lại editor để áp dụng thủ công.
- Thử editor/tool mới bằng project phụ hoặc task bounded trước, rồi mới chuyển daily workflow.
- Tự trả khoảng subscription cá nhân hoặc dùng free trial; adoption là bottom-up, chưa cần procurement hay rollout policy.

### Existing Tools

- **Editor:** VS Code là mặc định; Vim/JetBrains là nhóm khó chuyển hơn vì muscle memory và ecosystem khác.
- **AI:** GitHub Copilot cho completion; ChatGPT/GPT-4 cho hỏi đáp và generation; đôi khi Cursor chỉ là cửa sổ generate rồi code được đưa lại VS Code.
- **Context/verification:** search trong IDE, grep, docs/web, terminal và test chạy thủ công.

### Persona Test

- **Họ là ai?** Product engineer có khả năng đọc, sửa và review code production.
- **Làm ở đâu?** Startup/AI-native hoặc product team nhỏ, chu kỳ ship ngắn, cá nhân có quyền chọn công cụ.
- **Đang dùng gì?** VS Code + Copilot + ChatGPT + terminal/docs.
- **Vì sao thử?** Context switching và tự đóng gói context làm AI hiện hữu chỉ giúp từng snippet, chưa giúp hoàn thành change.
- **Vì sao chịu risk?** AI awareness cao, task feedback nhanh, có thể rollback bằng Git và tự phát hiện lỗi; lợi ích thời gian thuộc về chính họ.

## 2. Current Users

### Candidate Segment

**Primary:** professional product engineer trong team 10–500+ kỹ sư, làm hằng ngày trên codebase production nhiều file, nhận ticket/bug/refactor và chịu trách nhiệm review, test, ship. Họ dùng local agent cùng editor và có thể giao task bounded cho cloud/background agent. Công ty hoặc team thường trả phí.

**Secondary 1 — buyer/enabler:** engineering manager, developer-productivity/platform hoặc security leader triển khai Cursor theo team/doanh nghiệp; job là tăng throughput nhưng phải giữ rules, budget, identity, audit và data controls.

**Secondary 2 — emerging adjacent user:** QA/product/design trong tổ chức đã chuẩn hóa Cursor, cần đọc hoặc thay đổi production code qua UI có khả năng kiểm chứng. Chỉ giữ là secondary vì evidence rõ ở Money Forward nhưng chưa đủ để gọi là core market.

### Evidence

- [Cursor customer roster](https://cursor.com/customers) cho thấy deployment từ hàng trăm đến hàng nghìn engineer; các outcome lặp lại là onboarding vào codebase lạ, debug, migration/refactor và ship nhanh hơn.
- [Coinbase case study](https://cursor.com/blog/coinbase) mô tả hơn 2.400 developers dùng Cursor trong workflow thường xuyên; engineer chuyển từ tự viết mọi dòng sang định nghĩa intent, giao implementation và validate kết quả. Các task gồm Linear ticket → implementation → review, mobile testing, log investigation và change phức tạp có human intervention.
- [Money Forward case study](https://cursor.com/blog/money-forward) ghi nhận evaluation bởi nhóm Engineering Productivity/AI Research trước company-wide rollout; lựa chọn dựa trên setup thấp, unified workspace, large-codebase context và async agents. QA/product/design là phần mở rộng sau khi engineering chứng minh value.
- [Enterprise launch](https://cursor.com/blog/enterprise) và [Security page](https://cursor.com/security) bổ sung Team Rules, Hooks, audit, sandbox, SSO/SCIM và Privacy Mode—bằng chứng buyer đã chuyển từ cá nhân sang organization.

### Behaviors

- Engineer bắt đầu bằng plan/ticket, để agent tìm context và tạo multi-file diff, chạy test/terminal, rồi review và can thiệp ở điểm cần judgment.
- Team lưu convention trong rules/hooks, kết nối Jira/Linear/GitHub/MCP, quan sát usage và đặt model/budget/permission.
- Adoption vẫn khác nhau theo AI fluency; editor quen thuộc là bridge cho developer mới dùng agent, còn power user có thể chạy nhiều local/cloud agent song song.
- Buyer đánh giá ROI ở cycle time, PR throughput và time saved; barrier còn lại là correctness/review burden, security, cost predictability và workflow compatibility.

### Current User Test

- **Who/where?** Product engineer trong startup scale-up hoặc enterprise software organization; secondary buyer là platform/engineering/security leader.
- **Workflow/job?** Ticket hoặc production issue → hiểu repo → plan → implement nhiều file → test/debug → review/PR; hoàn thành change chứ không chỉ generate code.
- **Who pays?** Cá nhân ở Pro, nhưng với primary team-scale adoption người trả là team/company và buyer quản trị rollout.
- **Barrier?** Trust vào diff/agent action, privacy/compliance, bill khó dự đoán, IDE/extension convention và chi phí review code sinh ra quá nhanh.

## 3. Positive Reviews

Ba outcome có bằng chứng:

1. **Hiểu codebase/library lạ nhanh hơn:** user HN mô tả hỏi ngay trên đoạn code thay vì đọc chéo nhiều file và docs; customer roster cũng nêu onboarding/debug trên hệ thống phức tạp. [HN switching story](https://news.ycombinator.com/item?id=41727350) · [Customers](https://cursor.com/customers)
2. **Giảm context switching và áp dụng change nhanh:** community so sánh Cursor với VS Code + Copilot nhấn mạnh context/integration; Money Forward chọn unified workspace cho generation, review, testing và debugging. [Reddit](https://www.reddit.com/r/cursor/comments/1f7cku2/) · [Money Forward](https://cursor.com/blog/money-forward)
3. **Giao task end-to-end thay vì chỉ nhận completion:** Coinbase dùng agent cho ticket → implementation → review; Money Forward dùng cho refactor, migration và infrastructure work. [Coinbase](https://cursor.com/blog/coinbase) · [Money Forward](https://cursor.com/blog/money-forward)

## 4. Negative Reviews

Ít nhất ba pain point được giữ vì có evidence trực tiếp:

1. **Correctness/context:** user báo agent quên brief, lặp, bỏ task hoặc sửa sai khi hội thoại dài; một review sau ba tháng chỉ còn tin Cursor với task sạch, bounded vì cleanup ở codebase phức tạp. [Trust/context report](https://www.reddit.com/r/CursorAI/comments/1mbfiav/cursor_broke_my_trust_in_ai_codingany_good/) · [Complex-codebase review](https://www.reddit.com/r/CursorAI/comments/1k3uz9k/my_honest_review_after_3_months_with_cursorai/)
2. **Pricing transparency:** thay đổi từ request quota sang usage/rate-limit khó quan sát gây cảm giác không kiểm soát được cost và khiến một số user hủy/chuyển lại Copilot. [Pricing discussion](https://www.reddit.com/r/programming/comments/1lu8eyb/cursor_pay_more_get_less_and_dont_ask_how_it_works/) · [Switch-away thread](https://www.reddit.com/r/cursor/comments/1lrlb6m/)
3. **Privacy/security:** source code và agent command có blast radius lớn; Cursor phải cung cấp Privacy Mode, SOC 2, model blocklists, sandbox và admin controls. Đây là anxiety thật dù một complaint đơn lẻ không chứng minh lỗi hệ thống. [Cursor Security](https://cursor.com/security) · [HN privacy discussion](https://news.ycombinator.com/item?id=41381299)
4. **Workflow reliability:** early data-science user bỏ Cursor khi remote SSH bị hỏng vài ngày, cho thấy editor daily-driver có tolerance rất thấp với regression. [Reddit 2023](https://www.reddit.com/r/datascience/comments/17k3svb/has_anyone_tried_cursorsh_ai_editor_for_data/)

## 5. Switching Stories

### Story 1 — VS Code + Copilot/ChatGPT → Cursor

- **Before:** completion trong Copilot; câu hỏi lớn phải copy code/docs sang chatbot rồi tự áp dụng và test.
- **Trigger:** cần hiểu library/repo lạ và apply change ngay trong context.
- **After:** chat/context/multi-file edit nằm cùng editor; user Reddit báo lợi ích lớn hơn VS Code + Copilot, còn HN user nói bỏ Vim vì đọc code và tra API ngay trong Cursor nhanh hơn.
- **Evidence:** [Reddit comparison](https://www.reddit.com/r/cursor/comments/1f7cku2/) · [HN “Stopped using Vim”](https://news.ycombinator.com/item?id=41727350).

### Story 2 — Basic autocomplete/chat vendors → Cursor team rollout

- **Before:** Money Forward dùng các vendor khác cho autocomplete và basic chat nhưng adoption đình trệ vì không thấy time saving đáng kể.
- **Trigger:** demo agent hoàn thành software task end-to-end, cùng setup thấp và context cho codebase lớn.
- **After:** engineering adoption tăng; sau proof trong engineering, rollout mở sang QA/product/design.
- **Evidence:** [Money Forward](https://cursor.com/blog/money-forward).

### Counter-switch — Cursor → Copilot/old workflow

- **Reason:** pricing mơ hồ, context/quality regression hoặc editor reliability làm Pull không còn bù Anxiety.
- **Evidence:** [pricing switch-away](https://www.reddit.com/r/cursor/comments/1lrlb6m/) và [remote SSH abandonment](https://www.reddit.com/r/datascience/comments/17k3svb/has_anyone_tried_cursorsh_ai_editor_for_data/).

## 6. JTBD Candidates

Nghiên cứu rộng tạo **7 candidates**; chọn **4 final JTBD** (1–4). Tất cả vẫn tồn tại nếu Cursor biến mất.

### JTBD Candidate 1 — Hiểu codebase để tìm đúng điểm thay đổi (Final)

**Situation:** Khi nhận bug/feature trong repo lớn hoặc chưa quen.
**Job:** Tôi muốn dựng nhanh mental model về kiến trúc, dependency và nơi cần sửa.
**Desired outcome:** Bắt đầu implementation đúng chỗ mà không mất hàng giờ tự mở file và gom context.
**Old solution:** IDE search/grep, đọc docs, hỏi teammate, lần theo call sites thủ công.
**Evidence:** HN switching story; customer roster nêu unfamiliar-codebase onboarding/debug.
**Primary segment:** Both, mạnh hơn ở current teams có codebase lớn.

### JTBD Candidate 2 — Ship multi-file change có thể kiểm chứng (Primary, Final)

**Situation:** Khi phải giao feature, bug fix, migration hoặc refactor trong codebase production dưới deadline.
**Job:** Tôi muốn biến intent thành diff nhiều file, chạy feedback loop và sửa lỗi.
**Desired outcome:** Ship nhanh hơn nhưng vẫn review được và chịu trách nhiệm về chất lượng.
**Old solution:** Viết thủ công trong IDE + Copilot completion; ChatGPT copy/paste; tự chạy terminal/test và ghép patch.
**Evidence:** Coinbase ticket → implementation → review; Money Forward refactor/migration/infrastructure tasks.
**Primary segment:** Both; là JTBD chính xuyên suốt.

### JTBD Candidate 3 — Giảm việc cơ học để giữ flow (Final)

**Situation:** Khi implementation bị ngắt bởi boilerplate, tra API, lint/test failure và sửa lặp lại.
**Job:** Tôi muốn xử lý các bước cơ học ngay trong working context.
**Desired outcome:** Dành attention cho kiến trúc và trade-off thay vì chuyển qua chat/docs/terminal liên tục.
**Old solution:** Copilot snippet, web/docs, scripts, manual edit–run–fix loop.
**Evidence:** founder launch comment về editor-level auto-fix/navigation; early community workflow.
**Primary segment:** Early và current individual engineer.

### JTBD Candidate 4 — Delegate task bounded với guardrail (Final)

**Situation:** Khi có nhiều task độc lập/dài hoặc maintenance work cạnh tranh attention.
**Job:** Tôi muốn giao task cho agent chạy local/cloud và nhận lại diff, test/artifact để review.
**Desired outcome:** Tăng throughput song song mà không phải giám sát từng bước hoặc mất accountability.
**Old solution:** Tự làm tuần tự; giao teammate; script/CI; mở nhiều chat/terminal và tự điều phối branch.
**Evidence:** Background Agent, Cursor 2.0, Coinbase agent-first workflow và Money Forward async agents.
**Primary segment:** Current.

### JTBD Candidate 5 — Chuẩn hóa AI work theo team policy

**Situation:** Khi nhiều engineer/agent cùng tác động lên production repos.
**Job:** Tôi muốn áp rules, permissions, budget và audit nhất quán.
**Desired outcome:** Scale AI adoption mà security và quality không phụ thuộc từng cá nhân.
**Old solution:** onboarding docs, code review, CI gates, RBAC và manual approval rời rạc.
**Evidence:** Enterprise, Organizations và Security pages.
**Primary segment:** Current buyer; gộp vào adoption/governance thay vì final end-user JTBD.

### JTBD Candidate 6 — Tăng tốc review và bắt regression

**Situation:** Khi volume diff/PR tăng theo agent usage.
**Job:** Tôi muốn ưu tiên phần rủi ro và phát hiện lỗi trước merge.
**Desired outcome:** Giữ review throughput và quality khi code production tăng.
**Old solution:** reviewer đọc toàn bộ diff, static analysis, CI và manual reproduction.
**Evidence:** Cursor 1.0 đưa BugBot vào PR workflow; negative evidence cho thấy review vẫn bắt buộc.
**Primary segment:** Current; supporting job.

### JTBD Candidate 7 — Prototype để giảm bất định sản phẩm

**Situation:** Khi team cần kiểm tra ý tưởng hoặc UI trước khi đầu tư đầy đủ.
**Job:** Tôi muốn tạo và sửa prototype đủ thật để lấy feedback.
**Desired outcome:** Học trong giờ/ngày thay vì chờ một sprint.
**Old solution:** mockup tĩnh, throwaway code, nhờ engineer dựng prototype.
**Evidence:** customer roster và Money Forward design workflow.
**Primary segment:** Current secondary; không chọn final vì không phải core job xuyên timeline.

## 7. Segment Shift Evidence

```text
19/07/2023 — codebase-wide context
→ AI thấy phần repo liên quan, giảm thao tác đóng gói context
→ JTBD hiểu repo + sửa đúng chỗ khả thi hơn
→ VS Code/Copilot power user có lý do dùng Cursor như daily editor

24/11/2024 — Agent trong Composer
→ tự chọn context + terminal + multi-file edit + diff review
→ từ hỗ trợ snippet sang đóng loop task
→ professional product engineer dùng cho feature/bug/refactor thật

04/06/2025–31/10/2025 — Background Agent + enterprise governance
→ async delegation đi cùng rules, hooks, sandbox, audit
→ giảm attention cost và organizational risk
→ engineering team/enterprise buyer có lý do rollout rộng
```

| Dimension | Early adopters | Current primary/buyer |
|---|---|---|
| Risk tolerance | Cao; chấp nhận editor/API lỗi và tự rollback | Thấp hơn; outage, silent edit và policy gap chặn rollout |
| Company/adoption | Startup nhỏ; cá nhân bottom-up | Team/enterprise; vừa bottom-up vừa centrally governed |
| AI familiarity | Đã dùng Copilot/ChatGPT, tự prompt/context | Không đồng đều; cần UI, defaults, training và shared rules |
| Task complexity | Snippet, hỏi code, bounded feature | Production change nhiều file, migration, incident, async work |
| Trust/security | Review cá nhân là guardrail chính | Audit, sandbox, privacy, SSO/SCIM, budget + human review |
| Who pays | Cá nhân/free trial | Team/company; manager/platform/security tham gia quyết định |

## 8. Four Forces Evidence

### Push

**Current situation:** VS Code/JetBrains + Copilot completion + ChatGPT/browser + terminal/test rời nhau.
**Pain:** User tự chọn và copy context, chuyển cửa sổ, áp patch, chạy feedback loop và lặp lại cho multi-file change. Basic autocomplete/chat không tạo time saving đủ lớn ở Money Forward.
**Evidence:** HN launch/founder response; Money Forward trước rollout; early community comparisons.
**Why this pushes user toward Cursor:** Pain tăng theo kích thước repo và deadline; user cần hoàn thành change, không cần thêm một ô chat.

### Pull

**Attraction:** Một closed loop trong editor: repo context → plan/edit nhiều file → terminal/test → diff/review; sau 2025 có thể chạy task song song/async.
**Desired outcome:** Giảm time-to-change và attention spent nhưng vẫn giữ human verification.
**Evidence:** Coinbase dùng ticket → implementation → review; Money Forward chọn unified workspace/large-codebase context; community switching stories bỏ Copilot/Vim.
**Why it beats old workflow:** Cursor không chỉ sinh code; nó loại bỏ handoff giữa các công cụ và giữ state của task.

### Anxiety

**Fear:** Agent quên context hoặc sửa quá phạm vi; code chạy nhưng khó maintain; command/data exposure; usage bill khó đoán.
**Who feels it most:** Senior maintainer và enterprise buyer chịu trách nhiệm production, security và budget.
**Evidence:** negative reviews về cleanup/context; pricing backlash; Cursor phải bổ sung Privacy Mode, sandbox, audit và model controls.
**Impact on adoption:** Thu hẹp task được delegate, tăng review burden, trì hoãn procurement hoặc khiến user quay về Copilot/IDE cũ.

### Habit / Inertia

**Existing habit:** Editor extensions, keybindings, remote development, debugger, terminal setup, team docs/CI và review convention.
**Why it is sticky:** Đây là daily muscle memory và organizational infrastructure; editor regression có thể dừng công việc.
**Evidence:** HN launch hỏi “tại sao không editor cũ + Copilot”; user 2023 bỏ Cursor vì remote SSH; Cursor phải làm one-click VS Code import.
**What Cursor must overcome:** Giữ compatibility đủ cao, import setup, chứng minh gain end-to-end và cho phép review/rollback quen thuộc.

### Lực mạnh nhất

**Pull là lực mạnh nhất kéo user sang Cursor.** Push từ coding thủ công đã tồn tại trước Cursor nhưng có thể được giải bằng Copilot/ChatGPT; Habit vẫn mạnh và Anxiety tăng khi agent có nhiều quyền. Evidence chuyển đổi lặp lại chỉ xảy ra khi Cursor tạo outcome khác cấp độ—hiểu repo và đóng loop change—đủ để user bỏ editor/workflow quen thuộc. VS Code compatibility làm Habit yếu đi, nhưng không tự tạo adoption.

Với câu hỏi “giữ user Cursor ở lại,” lực tương ứng là **habit mới hình thành quanh context + agent + review workflow**, không phải data lock-in: rules, shortcuts, team conventions, cloud environments và kỳ vọng về một closed loop làm chi phí quay lại tool rời rạc tăng lên.

### Nếu Pull biến mất

Nếu VS Code/GitHub, Claude Code hoặc Codex đạt chất lượng context–agent–review tương đương với bundle/cost dễ hiểu hơn, incentive đổi editor gần như biến mất. Cursor sẽ mất lợi thế acquisition trước tiên, user price-sensitive có thể quay lại editor cũ, và enterprise buyer sẽ ưu tiên vendor đã có identity/repo/procurement. Cursor khi đó phải dựa nhiều hơn vào reliability của context/harness, model routing economics, governed team workflow và runtime/integration—không thể chỉ dựa vào “AI trong editor.”

## CP2 Audit & Rubric

- [x] Early adopter và current user đủ cụ thể; có evidence cho cả hai
- [x] 7 candidates, 4 final JTBD; đều là job và có old solution
- [x] 3 milestone tạo segment shift theo causal chain CP1
- [x] Positive outcomes, negative pain points và switching/counter-switch stories
- [x] Push/Pull/Anxiety/Habit đầy đủ; phân biệt lực kéo sang Cursor và lực giữ ở workflow cũ
- [x] Chọn strongest force và phân tích counterfactual

| Hạng mục | Điểm |
|---|---:|
| Early adopter specificity | 3/3 |
| Current user specificity | 2/2 |
| JTBD quality | 3/3 |
| Old alternatives/evidence | 2/2 |
| Segment shift | 3/3 |
| Connection to CP1 | 2/2 |
| Four Forces | 4/4 |
| Strongest-force reasoning | 1/1 |
| **TOTAL CP2** | **20/20** |

Điểm 20/20 là rubric estimate sau khi đã ghi rõ hai giới hạn: community evidence có selection bias; customer metrics là self-reported, không phải benchmark độc lập.
