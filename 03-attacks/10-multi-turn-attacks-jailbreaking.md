# Bài 10: Multi-Turn Attacks & Jailbreaking — Vượt Qua Guardrails

## Cisco Research: Frontier Models Under Pressure

**30,000 single-turn prompts + 7,000 multi-turn attacks** across 1,400+ conversations:

| Metric | Result |
|--------|--------|
| Multi-turn Attack Success Rate (max) | **88%** |
| Single-turn ASR (same models, max) | 64.91% |
| Multi-turn ASR (min) | 7.89% |
| Key finding | Two regimes produce **different model ordering** |

> "No frontier model is multi-turn immune." — Cisco Blog

**Models tested:** OpenAI, Anthropic, Google, xAI, Amazon frontier models.

## Tại sao Multi-Turn nguy hiểm hơn?

- Single-turn benchmarks **không reflect real-world risk**
- Attackers gradually escalate qua multiple turns
- Model "partial compliance" ở turn N → full compliance ở turn N+1
- Safety benchmarks dùng single prompts → **overestimate security**

## Attack Techniques

### Crescendo
- Interact với model theo cách seemingly benign
- Gradually escalate qua nhiều turns
- Model không nhận ra escalation pattern

### Siege (Tree Search)
- Breadth-first expansion mỗi turn
- Branch multiple adversarial prompts
- Exploit partial compliance từ previous responses

### Knowledge-Driven Multi-Turn
- Dùng domain knowledge để craft progression
- Context accumulation qua conversation

## Guardrails Themselves Are Vulnerable

> "Security guardrails deployed to prevent prompt injection can themselves be hacked through prompt injection." — Infosecurity Magazine (June 2026)

- Guardrails là thêm một layer of LLM → cũng vulnerable
- Pattern-matching firewalls fail against: Policy Puppetry, KROP, Unicode injection

## Defense

- **LLM Firewalls** — inspect natural language semantics cả 2 chiều
- **LlamaFirewall** (Meta, open-source) — Chain-of-Thought auditing
- **Behavioral monitoring** — Track conversation trajectory, not just individual messages
- **Rate limiting per topic** — Limit escalation patterns

## References

- [Cisco: Proprietary Problems — Multi-Turn Attacks](https://blogs.cisco.com/ai/proprietary-problems)
- [HelpNetSecurity: Frontier Models Collapse Under Multi-Turn](https://www.helpnetsecurity.com/2026/05/28/cisco-multi-turn-ai-attacks/)
- [CSOnline: AI Models More Vulnerable Than Claimed](https://www.csoonline.com/article/4177903/ai-models-more-vulnerable-than-claimed-when-faced-with-iterative-attacks.html)
- [Infosecurity: Major Security Gaps in LLM Guardrails](https://www.infosecurity-magazine.com/news/major-security-gaps-llm-guardrails/)
- [Arxiv: Crescendo Multi-Turn Jailbreak](https://arxiv.org/html/2404.01833v1)
