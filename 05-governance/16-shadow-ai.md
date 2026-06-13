# Bài 16: Shadow AI — Mối Đe Dọa Từ Bên Trong

## Scale of Problem

| Stat | Source |
|------|--------|
| **80%+** workers dùng AI tools chưa được approve | RiskPublishing 2026 |
| **90%** security professionals dùng unauthorized AI | RiskPublishing 2026 |
| **38%** employees share confidential data với AI | CybSafe/NCA |
| **78%** AI users bring own tools to work | Microsoft/LinkedIn |
| **47%** dùng AI qua personal accounts | Gartner |
| **45%** workers dùng AI trên corporate devices (from 15%) | Verizon DBIR 2026 |

## Tại sao Shadow AI nguy hiểm hơn Shadow IT?

> "It requires only a browser and deadline, not coding skills, enabling any employee to leak data without realizing it." — Kiteworks

- **DLP không detect AI data flows** — logging, access tools không designed cho prompts
- SaaS platforms thêm AI features **mà process sensitive data by default**
- Developers add AI capabilities **trước khi security teams review**
- AI note-taking tools = **covert data exfiltration channel**

## Insider Threat Model Thay Đổi

Traditional: User chỉ steal data họ có access → bounded by permissions.

AI era:
- AI tools **aggregate và synthesize** data across boundaries
- Single prompt có thể leak data mà DLP không detect
- **Agentic AI as ultimate insider threat** — agents launch other agents, spend money, modify systems

## Verizon DBIR 2026 Key Finding

> Lần đầu tiên trong 19 năm: **exploiting software vulnerabilities (31%)** vượt stolen credentials làm leading initial access vector.

## Defense Strategy

1. **AI Usage Policy** — Clear, enforceable rules
2. **Sanctioned alternatives** — Provide enterprise AI tools
3. **DLP for AI** — Monitor prompt/response patterns
4. **Browser isolation** — Prevent data paste vào external AI
5. **API discovery** — Detect outbound connections to AI services
6. **Training** — Specifically about data in prompts

## References

- [CIO.com: Shadow AI Expanding Across Enterprise](https://www.cio.com/article/4178708/shadow-ai-the-hidden-risk-expanding-across-the-enterprise.html)
- [Kiteworks: Shadow AI Data Leak Risks](https://www.kiteworks.com/cybersecurity-risk-management/shadow-ai-data-leak-risks/)
- [The Register: Shadow AI Surges](https://www.theregister.com/ai-ml/2026/05/19/shadow-ai-surges-in-the-workplace/)
- [ZDNet: Enterprise AI Agents as Insider Threat](https://www.zdnet.com/article/enterprise-ai-agents-insider-threat/)
- [Proofpoint: Insider Risk in the Age of AI](https://www.proofpoint.com/uk/blog/information-protection/ai-next-insider-threat-turning-point-for-insider-risk)
