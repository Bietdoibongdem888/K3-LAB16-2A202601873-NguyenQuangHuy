# User Research - Cursor

## Early Adopters

**Segment cụ thể:** product/software engineer tại startup nhỏ hoặc đội sản phẩm tốc độ cao; dùng VS Code hằng ngày; đã thử GitHub Copilot và ChatGPT; thường phải copy/paste code giữa editor và chatbot; theo dõi AI tooling và sẵn sàng đổi workflow nếu có lợi thế đủ lớn.

Bằng chứng:

- [HN launch thread tháng 3/2023](https://news.ycombinator.com/item?id=35285047) cho thấy audience ban đầu là developer kỹ thuật, biết Copilot và hoài nghi liệu editor mới có hơn “theme + Copilot” hay không.
- [One-click VS Code extension import](https://cursor.com/changelog/0-2-9) chỉ có ý nghĩa lớn khi target user đã có settings/extensions và muscle memory trong VS Code.
- [Chat v2](https://cursor.com/changelog/0-2-34), [inline Cmd+K](https://cursor.com/changelog/0-2-39) và [codebase-wide context](https://cursor.com/changelog/0-2-49) trực tiếp xử lý pain của người dùng AI sớm: phải chỉ định context thủ công và rời flow.

## Current Users

**Segment lõi hiện tại:** professional engineering teams xây và duy trì codebase thật, từ startup/product teams đến enterprise engineering organizations; họ muốn giao task cho nhiều agent nhưng vẫn cần review, security, policy, cost control và audit.

Bằng chứng:

- [Cursor Enterprise](https://cursor.com/blog/enterprise) thêm Hooks, Team Rules, analytics, audit và sandbox - các capability dành cho engineering organization, không phải hobbyist đơn lẻ.
- [Organizations](https://cursor.com/blog/organizations) cho phép ngân sách, model và permission khác nhau theo business unit/team.
- [Cloud agent Builds](https://cursor.com/blog/builds) giải quyết setup/reliability ở repo phức tạp; [AIUC-1](https://cursor.com/blog/aiuc-1) giải quyết enterprise anxiety về hành vi agent.
- [Cursor SDK](https://cursor.com/blog/typescript-sdk) mở rộng user từ “developer ngồi trong editor” sang platform/engineering team nhúng agent vào CI/CD và internal product.

Không kết luận “Cursor dành cho tất cả developer”. Student/hobbyist và non-engineer có thể dùng, nhưng evidence sản phẩm hiện tại ưu tiên professional teams và organizations.

## Positive Reviews

- Product Hunt reviewers nhấn mạnh AI nằm tự nhiên trong editor, context đa file và migration từ VS Code; đây là bằng chứng định tính cho **workflow moat + switching cost thấp**. [Nguồn](https://www.producthunt.com/products/cursor?launch=cursor-1-0)
- Một thảo luận tháng 6/2026 đánh giá Composer nhanh hơn đáng kể so với workflow Cline/VS Code dù chi phí cao hơn; đây là tín hiệu pull về latency và harness, không phải benchmark độc lập. [Nguồn](https://www.reddit.com/r/cursor/comments/1uboz5c/cursors_20_plan_is_incredible_but_the_payasyougo/)
- User CLI/Vim ghi nhận Composer 2.5 nhanh và hiệu quả khi có guardrails/review, đặc biệt cho project nhỏ. [Nguồn](https://www.reddit.com/r/cursor/comments/1ttxvgk/cursor_appreciation_post/)

## Negative Reviews / Skepticism

- Pricing megathread tháng 7/2025 thể hiện mất trust khi limits và usage không đủ rõ; người dùng muốn biết model availability và cost trước khi gửi request. [Nguồn](https://www.reddit.com/r/cursor/comments/1lwjxic/pricing_megathread/)
- Thảo luận 2026 phàn nàn context overhead làm chi phí pay-as-you-go cao. Đây là anxiety trực tiếp đối với agent dài và lý do Cursor cần Router/cost control. [Nguồn](https://www.reddit.com/r/cursor/comments/1uboz5c/cursors_20_plan_is_incredible_but_the_payasyougo/)
- Product Hunt review thừa nhận output có thể verbose/khó maintain và vẫn cần review từng dòng. [Nguồn](https://www.producthunt.com/products/cursor?launch=cursor-1-0)
- Nghiên cứu METR trên experienced OSS developers cho thấy AI tools không mặc định làm task nhanh hơn; đây là cảnh báo chống đồng nhất “nhiều code” với “productivity”. [Nguồn](https://arxiv.org/abs/2507.09089)

## Segment Shift

```text
2023: AI-curious VS Code power user
  -> import extensions + inline AI + repo context
2024-2025: professional product engineer
  -> Composer/Agent + terminal + background task + review
2025-2026: engineering team / enterprise organization
  -> multi-agent + hooks/rules/audit + cloud runtime + automation + SDK
```

Shift không phải “từ developer sang non-developer”. Nó là **từ cá nhân chấp nhận rủi ro để tăng tốc sang tổ chức cần delegation có thể kiểm soát**.

## JTBD Candidates

| Candidate job | Job hay feature? | Quyết định |
|---|---|---|
| Viết autocomplete nhanh hơn | Quá gần feature Tab | Loại |
| Tạo code từ prompt | Quá rộng và output-centric | Loại |
| Hiểu codebase lạ mà không tự gom context | Job chức năng rõ | Giữ làm supporting job |
| Chuyển ý định thành thay đổi production đã được kiểm tra mà không rời workflow | Có nhiều alternative; ổn định qua feature | **Primary** |
| Giao các task lặp lại cho agent chạy nền với guardrail | Job mới nổi của team | Giữ làm expansion job |

### Primary JTBD

> **Khi phải thay đổi một codebase thật dưới áp lực giao hàng, hãy giúp tôi chuyển ý định thành thay đổi có thể review và kiểm chứng mà không phải tự gom context hoặc qua lại giữa chat, editor và terminal, để tôi ship nhanh hơn nhưng vẫn kiểm soát chất lượng.**

Supporting jobs:

1. Hiểu kiến trúc và dependency của repo đủ nhanh để ra quyết định đúng.
2. Giảm công việc cơ học: boilerplate, refactor, test, fix lint và tra docs.
3. Giao task dài/lặp lại cho agent, nhận lại diff + bằng chứng thay vì giám sát từng token.
4. Chuẩn hóa cách agent làm việc theo rules, hooks và policy của team.

Previous alternatives: VS Code + GitHub Copilot; ChatGPT/Claude với copy/paste context; search docs/web; terminal chạy test thủ công; extension agent như Cline; giao việc cho đồng đội.

## Four Forces

| Force | Evidence-based analysis |
|---|---|
| **Push** | Fragmentation giữa editor-chat-terminal; phải gom context; công việc multi-file và lặp lại làm chậm delivery. |
| **Pull** | Một loop thống nhất có repo context, edit nhiều file, terminal/test, review diff, background/cloud agent và artifacts. |
| **Anxiety** | Hallucination, code khó maintain, prompt injection/data exposure, pricing khó đoán, agent chạy command sai, lock-in vào model/vendor. |
| **Habit** | Muscle memory, extensions, shortcuts, settings, remote dev và policy đã nằm trong VS Code; review code thủ công vẫn là cơ chế trust. |

**Lực mạnh nhất: Pull.** Compatibility với VS Code chỉ làm yếu Habit; động lực đủ lớn để đổi editor là closed loop “intent -> context -> edit -> test -> review”. Nếu agent chỉ autocomplete tốt hơn, lợi ích không đủ x10 để trả switching cost.

## What would make users switch away?

- Một lựa chọn được bundle sẵn trong GitHub/Microsoft/OpenAI/Anthropic có chất lượng agent tương đương nhưng cost dễ hiểu hơn.
- Cursor không kiểm soát context overhead, latency hoặc reliability của cloud environment.
- Enterprise security/compliance không theo kịp autonomy.
- Người dùng mất trust vì pricing hoặc agent tạo code nhanh nhưng tăng burden review/maintenance.
