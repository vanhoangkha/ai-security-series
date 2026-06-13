# AI Security Series 2026

A comprehensive technical series on AI Security covering the full threat landscape — from foundational frameworks to real-world breaches, offensive techniques, and defense architectures. Written for security engineers, developers, and CISOs.

**27 posts | 120+ sources | Last updated: June 2026**

---

## About

This repository documents the rapidly evolving AI security landscape through structured, research-backed articles. Each post includes actionable guidance, code examples where applicable, and references to primary sources (Google GTIG, Anthropic, MITRE, IBM X-Force, Cisco, SANS, Verizon DBIR, WEF, OWASP, and academic papers).

---

## Table of Contents

### Part 1 — Foundations

| # | Title | Summary |
|---|-------|---------|
| 01 | [AI Security Landscape 2026](01-foundations/01-ai-security-landscape-2026.md) | Threat overview, AI Security Stack (5 layers), key statistics |
| 02 | [OWASP Top 10 for LLM Applications](01-foundations/02-owasp-top-10-llm.md) | Each vulnerability explained with defense code |
| 25 | [MITRE ATLAS Framework](01-foundations/25-mitre-atlas.md) | 16 tactics, 84 techniques, usage guide |

### Part 2 — Vulnerabilities

| # | Title | Summary |
|---|-------|---------|
| 03 | [Prompt Injection Deep Dive](02-vulnerabilities/03-prompt-injection-deep-dive.md) | Direct, indirect, multimodal; defense patterns |
| 04 | [Model Supply Chain Security](02-vulnerabilities/04-model-supply-chain-security.md) | Pickle exploits, Hugging Face risks, backdoored weights |
| 05 | [Agentic AI and MCP Security](02-vulnerabilities/05-agentic-ai-mcp-security.md) | 30 CVEs in 60 days, 7 risk categories |
| 08 | [AI-Generated Code Security](02-vulnerabilities/08-ai-generated-code-security.md) | 25-62% of AI code carries vulnerabilities |
| 22 | [Hallucination as Attack Vector](02-vulnerabilities/22-hallucination-security.md) | Slopsquatting, package confusion attacks |

### Part 3 — Attacks

| # | Title | Summary |
|---|-------|---------|
| 07 | [Real-World Incidents 2026](03-attacks/07-real-world-incidents-2026.md) | 8 documented breaches and case studies |
| 09 | [Deepfake and AI Social Engineering](03-attacks/09-deepfake-social-engineering.md) | 40% of BEC now uses AI-generated media |
| 10 | [Multi-Turn Attacks and Jailbreaking](03-attacks/10-multi-turn-attacks-jailbreaking.md) | 88% success rate on frontier models (Cisco) |
| 11 | [RAG Security](03-attacks/11-rag-security.md) | Knowledge base poisoning, 10 passages = 98% success |
| 13 | [Data Poisoning](03-attacks/13-data-poisoning.md) | 250 documents and $60 compromise any model |
| 18 | [AI Worms](03-attacks/18-ai-worms.md) | Self-propagating agent malware, Morris II |
| 19 | [AI-Powered Exploit Generation](03-attacks/19-ai-exploit-generation.md) | Mythos, zero-day discovery acceleration |
| 20 | [LLMjacking](03-attacks/20-llmjacking.md) | Cloud compute theft, $100K/day impact |
| 21 | [Nation-State AI Threats](03-attacks/21-nation-state-ai-threats.md) | APTs weaponizing Gemini across all stages |

### Part 4 — Defense

| # | Title | Summary |
|---|-------|---------|
| 06 | [AI Red Teaming](04-defense/06-ai-red-teaming.md) | Framework, methodology, tooling |
| 12 | [Cloud AI Security on AWS](04-defense/12-cloud-ai-security-aws.md) | AWS AI Security Framework, Bedrock hardening |
| 15 | [AI Security Tools](04-defense/15-ai-security-tools.md) | 12 tools compared, defense-in-depth stack |
| 17 | [AI Agent Sandboxing](04-defense/17-ai-agent-sandboxing.md) | Firecracker, gVisor, V8 isolation patterns |
| 24 | [Content Provenance and Watermarking](04-defense/24-ai-content-provenance.md) | C2PA, SynthID, EU requirements |
| 27 | [LLM API and Inference Security](04-defense/27-llm-api-security.md) | Token-aware rate limiting, spend controls |

### Part 5 — Governance

| # | Title | Summary |
|---|-------|---------|
| 14 | [EU AI Act and Governance](05-governance/14-ai-governance-eu-ai-act.md) | AI Omnibus May 2026, compliance timeline |
| 16 | [Shadow AI](05-governance/16-shadow-ai.md) | 80% of workers use unapproved AI tools |
| 26 | [CISO Playbook](05-governance/26-ciso-playbook.md) | Budget allocation, strategy, priorities |

### Part 6 — Industry

| # | Title | Summary |
|---|-------|---------|
| 23 | [Physical AI Security](06-industry/23-physical-ai-security.md) | Autonomous vehicles, IoT, adversarial physical attacks |
| 28 | [Healthcare and Finance](06-industry/28-healthcare-finance-ai-security.md) | HIPAA compliance, fraud detection, model risk |

---

## Key Findings

- 2,130 AI-related CVEs disclosed in 2025, a 34.6% year-over-year increase
- Multi-turn attack success rates reach 88% on frontier models from all major providers
- 250 poisoned documents at $60 cost can backdoor any LLM regardless of size
- LLMjacking attacks cost victims $46,000 to $100,000+ per day in stolen compute
- First documented autonomous AI cyberattack occurred in early 2026
- AI discovered 10,000+ critical vulnerabilities in production software within one month
- 40% of business email compromise attacks now incorporate AI-generated deepfakes
- 80% of enterprise workers use unauthorized AI tools with no visibility or controls

---

## Sources

Primary research drawn from:

- Google Threat Intelligence Group (GTIG)
- Anthropic Research
- MITRE ATLAS / Center for Threat-Informed Defense
- IBM X-Force
- Cisco Security Research
- SANS Institute
- Verizon Data Breach Investigations Report 2026
- World Economic Forum Global Cybersecurity Outlook
- OWASP AI Security Projects
- Trend Micro TrendAI
- Cloud Security Alliance
- Academic papers (arxiv)

Full reference lists are included at the end of each post.

---

## Author

**Van Hoang Kha**

Cloud Security Engineer based in Ho Chi Minh City. Working at the intersection of cloud infrastructure, security, and community enablement. Designing and automating security on AWS — IAM, least privilege, Zero Trust.

- [LinkedIn](https://linkedin.com/in/vanhoangkha)
- [AWS First Cloud Journey](https://cloudjourney.awsstudygroup.com)

---

## License

This work is shared for educational purposes under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Reference with attribution.
