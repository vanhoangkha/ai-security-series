# Bài 15: AI Security Tools & Defense Stack 2026

## Top AI Security Tools

| Tool | Type | Key Feature |
|------|------|-------------|
| **NVIDIA Garak** | LLM vulnerability scanner | Open-source, comprehensive probe library |
| **LLM Guard** | Input/output guardrails | Real-time filtering, PII detection |
| **Lakera Guard** | AI firewall | Prompt injection detection |
| **CrowdStrike Falcon AIDR** | Threat detection | AI-specific incident response |
| **Microsoft PyRIT** | Red teaming | Automated adversarial testing |
| **LlamaFirewall** | Open-source guardrails | CoT auditing, multi-layer defense |
| **Prisma AIRS** | Platform | Full lifecycle AI security |
| **HiddenLayer** | Model security | Runtime model protection |
| **Cisco AI Defense** | Network-level | Multi-turn attack detection |
| **Wiz AI-SPM** | Posture management | Cloud AI security posture |
| **Zenity** | Agent security | Agentic AI governance |
| **Mindgard** | Continuous testing | AI red teaming automation |

## Architecture: LLM Firewall vs WAF vs Guardrails

| Layer | Function | Limitation |
|-------|----------|------------|
| **WAF** | Network-level filtering | Không hiểu semantic content |
| **Guardrails** | Output validation, content filtering | Itself vulnerable to injection |
| **LLM Firewall** | Semantic inspection cả 2 chiều | Higher latency, needs tuning |

> "An LLM firewall is not a WAF and not a guardrail. It sits at the API or network boundary and inspects natural language semantics in both directions."

## LlamaFirewall Architecture (Meta)

- **Chain-of-Thought Auditing** — Monitor reasoning process
- **Goal Hijacking Detection** — Identify when agent goals shift
- **Indirect Prompt Injection Defense** — Inspect retrieved content
- **Insecure Code Generation Blocking** — Scan generated code

## Recommendation: Defense-in-Depth Stack

```
Layer 1: Network (WAF, DDoS protection, rate limiting)
Layer 2: AI Gateway (routing, auth, logging, virtual keys)
Layer 3: LLM Firewall (semantic inspection, injection detection)
Layer 4: Guardrails (content filtering, PII redaction, schema validation)
Layer 5: Model (alignment, safety training, system prompts)
Layer 6: Monitoring (behavioral analytics, drift detection, alerting)
```

## References

- [SecurityBoulevard: Top 8 AI App Security Software 2026](https://securityboulevard.com/2026/06/top-8-ai-app-security-software-in-2026/)
- [AppSecSanta: Best AI Security Tools 2026](https://appsecsanta.com/ai-security-tools)
- [BeyondScale: LLM Firewall Enterprise Guide](https://beyondscale.tech/blog/llm-firewall-enterprise-guide)
- [LlamaFirewall Paper](https://arxiv.org/abs/2505.03574)
- [GetMaxim: Best AI Guardrails Platforms 2026](https://www.getmaxim.ai/articles/best-ai-guardrails-platforms-in-2026/)
