# Bài 1: Tổng Quan AI Security Landscape 2026 — Mối Đe Dọa Đang Thay Đổi

## Bối cảnh

2026 đánh dấu bước ngoặt của AI Security. Theo Trend Micro, **2,130 CVE liên quan đến AI** được công bố riêng trong 2025, tăng 34.6% so với năm trước. IBM X-Force ghi nhận hàng chục lỗ hổng mới ảnh hưởng trực tiếp đến AI systems trong nửa đầu 2026.

## Tại sao AI Security khác biệt?

AI security là bài toán hai chiều:
1. **AI systems chính là mục tiêu** — LLM bị khai thác qua prompt injection, AI-generated code chứa lỗ hổng, model supply chain là attack surface mới
2. **AI là vũ khí tấn công** — Autonomous agents né detection, semantic-layer attacks khiến kiến trúc phát hiện dựa trên con người trở nên lỗi thời

## 3 Chiều Kích Mới (World Economic Forum)

- **Attack Surface mở rộng**: Tích hợp AI tạo ra lỗ hổng mà traditional controls không designed để xử lý
- **Agentic AI & Supply Chain Attacks**: Đã vượt qua ngưỡng từ "POC thú vị" sang "compromise quy mô hệ sinh thái, worm-like, zero human in the loop"
- **Shadow AI**: 100% tổ chức có AI-generated code trong production, 81% không có visibility vào cách AI được sử dụng (Cycode 2026)

## AI Security Stack 2026

Theo nghiên cứu, AI Security Stack gồm 5 layer:
1. **Governance** — Policy layer: ai có quyền dùng model nào, data gì, rule gì
2. **Red Teaming** — Pre-deployment offense testing
3. **MLSecOps** — Security trong ML pipeline
4. **Threat Detection** — LLM runtime monitoring
5. **Agentic Defense** — Bảo vệ AI agents

## Key Takeaway

> "AI didn't slightly amplify existing threats; autonomous, semantic-layer attacks made human-paced detection architectures structurally obsolete." — Cyber Strategy Institute

## References

- [Trend Micro: State of AI Security Report](https://www.trendmicro.com/vinfo/us/security/news/threat-landscape/fault-lines-in-the-ai-ecosystem-trendai-state-of-ai-security-report/)
- [WEF: Global Cybersecurity Outlook 2026](https://www.weforum.org/publications/global-cybersecurity-outlook-2026/)
- [IBM X-Force: Agentic AI Security Risks](https://www.ibm.com/think/x-force/agentic-ai-growing-fast-vulnerabilities)
- [AI Security Stack 2026](https://guptadeepak.com/research/ai-security-stack-2026/)
- [Cyber Strategy Institute: 2026 AI Cybersecurity Risks](https://cyberstrategyinstitute.com/2026-ai-cybersecurity-risks/)
