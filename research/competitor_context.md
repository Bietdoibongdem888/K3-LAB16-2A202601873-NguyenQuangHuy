# Competitor Context - Cursor (14/08/2026)

## Competitive frame

Cuộc cạnh tranh không còn là “ai autocomplete tốt hơn”. Các đối thủ đang hội tụ vào **agent + environment + review + distribution + governance**.

| Competitor | Current strategic pressure | Implication for Cursor | Source |
|---|---|---|---|
| GitHub Copilot / Microsoft | Coding agent chạy nền bằng GitHub Actions, tự mở PR; distribution nằm ngay repo và VS Code | Cursor không thể chỉ dựa vào IDE; phải thắng ở harness, context, multi-model và agent control plane | [GitHub](https://github.blog/changelog/2026-02-13-network-configuration-changes-for-copilot-coding-agent/) |
| OpenAI Codex | App/CLI/IDE/cloud dưới một ChatGPT subscription; worktrees, multi-agent, automations | Model provider có thể bundle model + agent + distribution, nén margin của wrapper | [OpenAI](https://openai.com/index/introducing-the-codex-app/) |
| Anthropic Claude Code | Terminal-native, được bundle vào Team/Enterprise, có admin/compliance | Power users có thể chọn harness gần model và giữ editor hiện tại | [Anthropic](https://www.anthropic.com/news/claude-code-on-team-and-enterprise) |
| Google Jules | Async cloud agent tích hợp GitHub và bundle qua Google AI tiers | Background task trở thành commodity; reliability và workflow integration mới phân biệt | [Google](https://blog.google/innovation-and-ai/models-and-research/google-labs/jules-now-available/) |
| VS Code | Nền tảng extension và muscle memory lớn; là alternative mặc định | Fork giúp Cursor giảm switching cost nhưng tạo dependency và nguy cơ feature parity từ upstream | [VS Code base evidenced by import decision](https://cursor.com/changelog/0-2-9) |
| Windsurf / agentic IDEs | Cạnh tranh trực tiếp về IDE-native context, pricing và agent UX | Làm giảm uniqueness của “AI editor”; Cursor cần platform moat ngoài editor | [Product Hunt alternative set](https://www.producthunt.com/products/cursor?launch=cursor-1-0) |

## Strategic reading

**FACT:** Cursor đã mở rộng từ editor sang cloud agents, Automations, SDK, Router và enterprise governance.

**INFERENCE:** Moat bền hơn model access là tổ hợp context engine, agent harness, reliable environment, policy, distribution đa surface và organizational adoption. Từng thành phần có thể bị sao chép; lợi thế nằm ở loop tích hợp và tốc độ học từ workflow, không được hiểu là dữ liệu training độc quyền khi chưa có nguồn.

## Big Tech threat

Mối đe dọa lớn nhất là bundle: GitHub/Microsoft sở hữu repo + IDE distribution; OpenAI/Anthropic/Google sở hữu frontier model và subscription. Nếu capability ngang nhau, Cursor phải chứng minh ROI tốt hơn trên toàn loop và cho phép model portability. Router và Composer là hai phản ứng: trừu tượng hóa vendor, đồng thời sở hữu một phần economics/model stack.
