# Bài 22: AI Hallucination Security — Package Confusion & Slopsquatting

## The Attack: Slopsquatting

1. LLMs hallucinate **non-existent package names** consistently
2. Attackers monitor hallucination patterns
3. Register malicious packages with those exact names
4. Developers trust AI suggestion → install malicious package

## Statistics

| Metric | Value |
|--------|-------|
| Hallucinated package instances | **500,000+** (Endor Labs) |
| Legal AI hallucination rate | **69-88%** on high-stakes queries |
| Stanford: AI legal research hallucination | **17%+ of queries** |

## Real-World Example

- Attacker identified popular models frequently suggest non-existent Python package
- Registered name on PyPI
- Loaded with **multi-stage credential harvester**
- Developers installing based on LLM recommendation → compromised

## Legal Risk

- **Mata v. Avianca** (2023): AI-hallucinated citations → sanctions
- Alabama (2025): Attorneys submitted **5 ChatGPT-fabricated citations**
- Firms with **explicit bans** on unverified AI still had violations

## Defense

1. **Verify all packages** — Check existence before install
2. **Lockfiles** — Pin exact versions, review additions
3. **Private registries** — Namespace protection
4. **AI output validation** — Never auto-install AI-suggested dependencies
5. **Monitor hallucination patterns** — Pre-register common hallucinated names

## References

- [Aikido: Slopsquatting Package Hallucination Attacks](https://www.aikido.dev/blog/slopsquatting-ai-package-hallucination-attacks)
- [BeyondScale: AI Hallucination Security Risk](https://beyondscale.tech/blog/ai-hallucination-security-risk-enterprise)
- [Arxiv: Package Hallucinations by Code Generating LLMs](https://arxiv.org/abs/2406.10279)
- [Beeble: Ghost in the Repository](http://beeble.com/en/blog/the-ghost-in-the-repository-how-hallucinated-dependencies-are-breaking-the-secure-software-supply-chain)
- [DevX: AI Hallucinations in Production Code](https://www.devx.com/uncategorized/ai-hallucinations-production-code-risks-mitigations-2026/)
