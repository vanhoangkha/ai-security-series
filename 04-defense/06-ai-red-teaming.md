# Bài 6: AI Red Teaming — Từ Theory đến Practice

## AI Red Teaming khác gì Traditional Pentesting?

| Aspect | Traditional Pentesting | AI Red Teaming |
|--------|----------------------|----------------|
| Attack surface | Deterministic code paths | Probabilistic model behavior |
| Vulnerabilities | Discrete bugs | Behavioral failures |
| Patches | Code fixes | Retraining, guardrails, architectural changes |
| Reproducibility | High | Low — same input can give different results |

## AI Red Teaming Framework

### Phase 1: Scoping
- Define target system boundaries
- Identify AI components vs traditional components
- Classify data sensitivity

### Phase 2: Threat Modeling
- Map OWASP LLM Top 10 to specific system
- Identify custom threat scenarios
- Prioritize by impact × likelihood

### Phase 3: Execution
- Prompt injection campaigns (direct, indirect, multimodal)
- Jailbreak testing across multiple strategies
- Data extraction attempts
- Agent manipulation (tool abuse, privilege escalation)
- Supply chain verification

### Phase 4: Validation & Reporting
- Confirm exploitability
- Measure blast radius
- Document reproduction steps
- Provide actionable remediation

## Tools & Automation

- **Microsoft PyRIT** — Python Risk Identification Toolkit
- **Garak** — LLM vulnerability scanner
- **Mindgard** — Continuous AI security testing platform
- **Custom harnesses** — Adaptive attackers evolving strategies over hundreds of rounds

## When to Red Team

- Pre-deployment (mandatory)
- After model updates/fine-tuning
- After tool/plugin additions
- Quarterly for production systems
- After security incidents

## References

- [Repello.ai: AI Red Teaming Complete Guide 2026](https://repello.ai/blog/the-essential-guide-to-ai-red-teaming-in-2024)
- [Microsoft: Planning Red Teaming for LLMs](https://learn.microsoft.com/en-us/azure/foundry/openai/concepts/red-teaming)
- [Mindgard: AI Red Teaming in 2026](https://mindgard.ai/blog/what-is-ai-red-teaming)
- [Akto.io: Continuous Testing for Agentic AI](https://www.akto.io/blog/ai-red-teaming)
