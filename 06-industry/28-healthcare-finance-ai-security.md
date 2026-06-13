# Bài 28: AI Security in Healthcare & Finance — Sector-Specific Risks

## Healthcare

### HIPAA + AI (2026)

- Proposed HIPAA Security Rule update (May 2026): eliminates "addressable" safeguard distinction
- Mandates **annual risk assessments explicitly including AI systems**
- No special AI exemption — AI vendors = business associates, need BAAs
- LLM context windows count as "access" — every prompt with PHI needs legal basis

### Key Risks

- Re-identification of anonymized data via AI
- AI chat systems exposing PHI
- Model training on patient data without consent
- Hallucinated medical information → patient harm

### Compliance Checklist

- BAAs with all AI vendors
- Encryption for all ePHI in AI pipelines
- Human oversight for AI-assisted decisions
- 60-day breach notification clock applies to AI incidents

## Financial Services

### AI Fraud Detection Market

- Financial services AI market: **$65 billion** by 2026
- 90% US banks use AI for fraud detection
- 25-40% improvement in fraud detection rates
- Global banking fraud costs exceeded **$45 billion** in 2024

### The Dual-Use Problem

Same AI that improves detection **also increases attack throughput**:
- Rules-based systems obsolete — fraudsters probe boundaries within weeks
- AI-powered attacks outpace static defenses
- Model Risk Management (MRM) now must cover AI-specific threats

### Key Considerations

- Adversarial robustness for fraud models
- Model explainability for regulatory compliance
- Real-time transaction monitoring at scale
- Bias detection in credit/lending decisions

## References

- [Kiteworks: AI Compliance in Healthcare](https://www.kiteworks.com/hipaa-compliance/ai-compliance-healthcare-requirements/)
- [HIPAA Update 2026](https://itecsonline.com/post/hipaa-compliance-in-the-age-of-ai-what-healthcare-must-know-in-2026)
- [Morgan Lewis: AI Healthcare Checklist](https://www.morganlewis.com/pubs/2026/05/ai-in-healthcare-a-practical-checklist-for-compliance-and-risk-management)
- [Blockchain Council: AI Security in Finance](https://www.blockchain-council.org/ai/ai-security-in-finance-fraud-detection-model-risk-compliance/)
- [GroovyWeb: AI Fraud Detection Build vs Buy](https://www.groovyweb.co/blog/ai-fraud-detection-build-vs-buy-2026)
