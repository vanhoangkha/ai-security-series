# Bài 8: AI-Generated Code Security — Con Dao Hai Lưỡi

## Thống kê đáng báo động

| Metric | Data |
|--------|------|
| Code samples có vulnerability | **25.7%** (study 522 samples, 6 LLMs) |
| GPT-5.2 (safest model) | 19.5% vulnerable |
| 3 models tied worst | 29.9% vulnerable |
| GitHub Copilot (2021 study) | ~40% vulnerable |
| General AI-generated code | **Up to 62%** carry exploitable vulns |
| CVEs traced to AI-generated code (Mar 2026 alone) | **35+** |
| Orgs with security incident from AI code | **56%** (Snyk 2025) |
| AI hallucinating non-existent packages | **500,000+ instances** (Endor Labs) |

## Key Findings

**Cycode State of Product Security 2026:**
- 100% tổ chức có AI-generated code trong production
- 81% không có visibility vào cách AI được sử dụng trong dev lifecycle

**IOActive Research:**
> "Organizations must treat AI output as untrusted input — especially for infrastructure, authentication, and cryptography."

## AI Coding Assistants Security Comparison

| Tool | Privacy/Security Posture |
|------|--------------------------|
| Windsurf | Zero data retention by default |
| Cursor | Requires manual opt-in to Privacy Mode |
| GitHub Copilot Enterprise | Enterprise controls available |
| Kiro | Enterprise security posture đang mature |

## Package Hallucination Attack

- AI hallucinate non-existent package names → attacker register chúng trên npm/PyPI
- 500,000+ instances documented
- Supply chain attack vector hoàn toàn mới — tạo ra bởi AI behavior

## Mitigation

1. **Treat AI output as untrusted input** — mandatory security review trước deployment
2. **SAST/DAST cho AI code** — scan giống human-written code
3. **Visibility tools** — track AI-generated code trong codebase
4. **Lock down package names** — verify packages exist trước khi dùng
5. **Đặc biệt review**: infrastructure, auth, crypto code từ AI

## References

- [AppSecSanta: 6 LLMs vs OWASP Top 10](https://appsecsanta.com/research/ai-code-security-study-2026)
- [Veracode: Spring 2026 GenAI Code Security](https://www.veracode.com/blog/spring-2026-genai-code-security)
- [IOActive: Security Gap in AI-Generated Code](https://www.ioactive.com/the-security-gap-in-ai-generated-code/)
- [BeyondScale: AI Coding Assistant Security Guide](https://beyondscale.tech/blog/ai-coding-assistant-security-enterprise-guide)
- [AIMagicX: AI Coding Security Risks 2026](https://www.aimagicx.com/blog/ai-coding-security-risks-agentic-development-2026)
