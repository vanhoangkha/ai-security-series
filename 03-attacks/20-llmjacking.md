# Bài 20: LLMjacking — Khi AI Compute Bị Đánh Cắp

## Định nghĩa

LLMjacking = unauthorized use of cloud-hosted LLM resources via compromised credentials, APIs, or exposed endpoints. Giống cryptojacking nhưng cho AI.

## Cost Impact

| Metric | Value |
|--------|-------|
| Cost per day per abused credential | **$46,000 - $100,000+** |
| Time to admin access (fastest case) | **8 minutes** |
| AWS principals compromised in single attack | **19** |

## Case Study: AWS 8-Minute Breach (Feb 2026)

1. Attacker achieves **admin privileges in <10 minutes**
2. Compromises 19 AWS principals
3. Abuses **Bedrock models + GPU compute**
4. Exfiltrates RAG data from S3 buckets
5. AI-assisted throughout — LLM helped with escalation

## Vercel: "Inference Theft"

> "A single prompt to an agent on a frontier model can cost $2, making AI a million times more expensive, and inference theft one of the highest-margin businesses an attacker can run."

## Cloud Security Alliance Findings

- **91%** of organizations using SageMaker had notebooks running with **root access**
- **14%** Bedrock users hadn't blocked **public access** to AI training buckets

## Defense

- **Token-aware rate limiting** (not just request count)
- **Spend alerts & caps** — hard limits on API costs
- **Credential rotation** — short-lived tokens only
- **Behavioral monitoring** — detect unusual inference patterns
- **Network segmentation** — separate AI endpoints
- Self-hosted (vLLM, Ollama) ship with **auth gaps** — explicitly remediate

## References

- [Sysdig: LLMjacking — Emerging Threat to Black Market](http://www.sysdig.com/blog/llmjacking-from-emerging-threat-to-black-market-reality)
- [CSOnline: Credentials to Cloud Admin in 8 Minutes](https://www.csoonline.com/article/4126336/from-credentials-to-cloud-admin-in-8-minutes-ai-supercharges-aws-attack-chain.html)
- [Vercel: Protecting Against Inference Theft](https://vercel.com/blog/protecting-against-inference-theft)
- [Kaspersky: LLMjacking 2026](https://www.kaspersky.com/blog/llmjacking-2026-private-ai-server-security/55768)
- [BeyondScale: LLMjacking Defense Guide](https://beyondscale.tech/blog/llmjacking-defense-guide)
