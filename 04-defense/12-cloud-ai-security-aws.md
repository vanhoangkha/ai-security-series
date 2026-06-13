# Bài 12: AI Security trên Cloud — AWS, Azure & Deployment Security

## AWS AI Security Framework (2026)

AWS publish framework chính thức:
- **Security controls tại đúng layer, đúng phase**
- AI Security Scoping Matrix — assess controls throughout AI lifecycle
- "Location of your AI agent is a security decision"

## Key Cloud AI Risks

| Risk | Detail |
|------|--------|
| Misconfigured deployments | Expose data through model prompts |
| Exposed inference endpoints | Agents can find and exploit unprotected APIs |
| Model loading from external registries | Runtime supply chain risk |
| Overprivileged IAM roles | AI agents với broad permissions |
| Lack of runtime monitoring | Batch vs agentic workloads có threat model khác |

## Cloud-Specific Threat Model

> "A foundation model is an opaque artifact loaded from a registry you don't own, given access to data and tools, and instructed in plain text that anyone in the input path can rewrite."

## AWS Native vs Third-Party Tools

| Scenario | Recommendation |
|----------|---------------|
| Batch SageMaker inference, no tool-calling | AWS native tools sufficient |
| Agents calling external APIs | Need runtime behavioral monitoring |
| Running on EKS | Need container-level AI security |
| Loading models from external registries | Need supply chain verification |

## Defense Architecture

```
┌─────────────────────────────────────────────┐
│              Network Layer                    │
│  (VPC, Security Groups, WAF for API Gateway) │
├─────────────────────────────────────────────┤
│              AI Gateway/Firewall              │
│  (LLM Firewall, semantic inspection)         │
├─────────────────────────────────────────────┤
│              Guardrails Layer                 │
│  (Input/output validation, PII filtering)    │
├─────────────────────────────────────────────┤
│              Model Runtime                    │
│  (Isolated compute, scoped IAM, monitoring)  │
├─────────────────────────────────────────────┤
│              Data Layer                       │
│  (Encrypted storage, access logging, DLP)    │
└─────────────────────────────────────────────┘
```

## AWS Bedrock Security Checklist

- Enable Bedrock Guardrails (content filtering, PII redaction)
- Use Trend Micro Vision One for misconfiguration detection
- Scoped IAM execution roles — minimal permissions
- Network segmentation — private subnets for inference
- CloudTrail logging cho all model invocations
- Regular security assessment against AI Scoping Matrix

## References

- [AWS: AI Security Framework](https://aws.amazon.com/blogs/security/the-aws-ai-security-framework-securing-ai-with-the-right-controls-at-the-right-layers-at-the-right-phases/)
- [AWS: AI Security Scoping Matrix](https://aws.amazon.com/ai/security/generative-ai-scoping-matrix/)
- [AWS: Why Agent Location is a Security Decision](https://aws.amazon.com/blogs/publicsector/why-the-location-of-your-ai-agent-is-a-security-decision/)
- [Cloud Security Alliance: Securing AI in AWS](https://cloudsecurityalliance.org/articles/securing-ai-workloads-in-aws-why-bedrock-and-sagemaker-need-runtime-detection-and-ai-powered-response)
- [AWS: Detecting Misconfigurations with Trend AI](https://aws.amazon.com/blogs/awsmarketplace/detecting-misconfigurations-and-mitigating-ai-risks-to-secure-amazon-bedrock-with-trendai-vision-one/)
