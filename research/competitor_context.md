# Competitor Context — Cursor

Ngày kiểm tra: **14/08/2026**. Chỉ giữ đối thủ tác động trực tiếp tới distribution, agent workflow, enterprise control, pricing hoặc moat của Cursor.

## 1. GitHub Copilot / Microsoft / VS Code

**Product:** GitHub Copilot cloud agent + Copilot app + VS Code.
**Current capability:** Cloud agent nhận issue/prompt, research/plan/code trên branch, chạy test và tạo PR; GitHub-native app bắt đầu từ issue/PR/checks và hỗ trợ steer–review–ship trong một nơi.
**Why it matters to Cursor:** Đây là threat mạnh nhất vì capability gần Cursor nhưng distribution nằm sẵn ở repo, PR, identity, billing và editor habit. Cursor phải thắng ở cross-model routing, runtime reliability và governed workflow—not chỉ agent UI.
**Source:** [Copilot cloud agent](https://github.blog/changelog/2026-04-01-research-plan-and-code-with-copilot-cloud-agent/) · [Copilot app](https://github.blog/changelog/2026-05-14-github-copilot-app-is-now-available-in-technical-preview/)
**Date:** 01/04/2026; 14/05/2026.

## 2. OpenAI Codex

**Product:** Codex app/CLI/IDE/cloud trong ChatGPT plans.
**Current capability:** Multi-agent/worktree, diff review, skills, scheduled Automations, mobile control và programmatic credentials; usage được bundle qua ChatGPT subscriptions.
**Why it matters to Cursor:** OpenAI sở hữu model và distribution bundle nên có thể nén giá của standalone agent. Cursor cần chứng minh harness/context/router đem lại cost per outcome tốt hơn và giữ model portability.
**Source:** [Codex app](https://openai.com/index/introducing-the-codex-app/) · [Codex mobile/programmatic access](https://openai.com/index/work-with-codex-from-anywhere/)
**Date:** 02/02/2026; 14/05/2026.

## 3. Anthropic Claude Code

**Product:** Terminal-native Claude Code trong Team/Enterprise.
**Current capability:** Claude + Claude Code cùng subscription, premium seats, managed policy, usage analytics, spend caps và Compliance API.
**Why it matters to Cursor:** Power user có thể giữ editor/terminal hiện hữu và đi thẳng tới model provider; enterprise buyer cũng có admin/compliance, làm yếu cả Pull lẫn governance differentiation của Cursor.
**Source:** [Claude Code for Team & Enterprise](https://www.anthropic.com/news/claude-code-on-team-and-enterprise)
**Date:** 20/08/2025 (current capability rechecked 14/08/2026).

## 4. Google Jules

**Product:** Asynchronous GitHub coding agent.
**Current capability:** Chạy task trong cloud, làm việc với GitHub repo và được phân phối qua Google AI plans.
**Why it matters to Cursor:** Background task bị commoditize; Cursor không thể coi “agent chạy nền” là moat mà phải khác biệt ở environment, verification, orchestration và enterprise workflow.
**Source:** [Jules public launch](https://blog.google/innovation-and-ai/models-and-research/google-labs/jules-now-available/)
**Date:** 06/08/2025 (current positioning rechecked 14/08/2026).

## 5. Windsurf và agentic IDEs

**Product:** Các AI-native editor cạnh tranh trực tiếp.
**Current capability:** IDE-native chat/context/agent và VS Code-like migration path; product set xuất hiện trực tiếp cạnh Cursor trong user consideration.
**Why it matters to Cursor:** Feature parity làm “AI editor” mất uniqueness. Threat này củng cố nhu cầu Cursor mở moat ra runtime, model economics, policy và distribution ngoài desktop. Không dùng nguồn này để claim market share hay feature chi tiết chưa kiểm chứng.
**Source:** [Product Hunt alternative set](https://www.producthunt.com/products/cursor?launch=cursor-1-0)
**Date:** Rechecked 14/08/2026.

## Competitive Synthesis

| Pressure | Competitor advantage | Cursor response signal | Prediction implication |
|---|---|---|---|
| Capability convergence | GitHub/OpenAI có multi-agent, cloud, review, automation | Cursor đầu tư risk policy, cloud runtime và artifacts | Productize verified, policy-gated lifecycle |
| Distribution/bundling | GitHub sở hữu repo/PR/VS Code; OpenAI/Anthropic sở hữu model subscription | Cursor chạy desktop/web/mobile/Slack/CLI/SDK | Moat phải xuyên surface, không khóa trong editor |
| Model commoditization | Model provider có direct harness và giá bundle | Router + Composer + keep-rate/cost-per-commit | Routing trở thành economic layer |
| Enterprise procurement | GitHub/Anthropic có identity, policy và compliance | Organizations + hooks + audit + sandbox | Hợp nhất control plane org-level |

## Strongest Competitive Threat

**GitHub Copilot/Microsoft** là threat mạnh nhất: không chỉ copy capability mà còn loại bỏ switching cost nhờ repo, issue, PR, identity, billing và VS Code distribution đã có. OpenAI có model/bundle mạnh hơn, nhưng GitHub trực tiếp sở hữu workflow mà current Cursor user đang cố hoàn thành.

## Defensible Moat Reading

Cursor không thể dựa vào độc quyền model hoặc data lock-in chưa được chứng minh. Moat khả dĩ là tổ hợp:

```text
repo/team context
+ reliable agent environment
+ risk-aware orchestration and verification
+ model routing economics
+ policy/audit across surfaces
```

Từng phần có thể bị copy; lợi thế chỉ tồn tại nếu loop tích hợp tạo outcome/cost tốt hơn bundle của platform incumbent.
