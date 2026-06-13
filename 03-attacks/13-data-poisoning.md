# Bài 13: Data Poisoning — $60 Để Compromise Bất Kỳ Model Nào

## Anthropic + UK AI Security Institute Research

> "As few as **250 malicious documents** can produce a backdoor vulnerability in a large language model — **regardless of model size or training data volume.**"

- Cost: approximately **$60** để poison training data
- Works across model sizes
- Backdoor invisible during normal operation

## Attack Economics

| Factor | Value |
|--------|-------|
| Documents needed | ~250 |
| Cost | ~$60 |
| Model size dependency | None — works on any size |
| Detection difficulty | Extremely hard |
| Trigger mechanism | Specific inputs activate backdoor |

## ZDNet Key Stats

- Prompt injection attacks succeed against **56%** of LLMs
- Model repositories harbor **hundreds of thousands** of malicious files
- Threat actors hijack autonomous AI agents to conduct cyberattacks

## Types of Data Poisoning

1. **Backdoor injection** — Model behaves normally except with trigger inputs
2. **Bias amplification** — Subtly shift model outputs toward attacker's goal
3. **Performance degradation** — Reduce accuracy for specific tasks
4. **Preference manipulation** — Poison RLHF/preference data to alter behavior

## Research: 22 Models Tested

Study tested Phi, Mistral, DeepSeek-R1, Llama 3.2, Qwen, Gemma variants:
- Significant behavioral variation
- Some models show complete "silent non-responsiveness"
- GPT models remain vulnerable even with moderation systems

## Defense

1. **Data provenance** — Track every document in training corpus
2. **Statistical analysis** — Detect distribution shifts
3. **Canary tokens** — Plant known-good test cases
4. **Multi-source verification** — Cross-reference data
5. **Continuous evaluation** — Test model behavior against benchmarks
6. **Fine-tuning guardrails** — Restrict what fine-tuning can modify

## References

- [Anthropic: Small Samples Can Poison LLMs](https://www.anthropic.com/research/small-samples-poison)
- [CSOnline: Democratization of AI Data Poisoning](https://csoonline.com/article/4131517/the-democratization-of-ai-data-poisoning-and-how-to-protect-your-organization.html)
- [ZDNet: 4 Critical AI Vulnerabilities](https://www.zdnet.com/article/ai-security-threats-2026-overview/)
- [Arxiv: Scaling Trends for Data Poisoning](https://arxiv.org/html/2408.02946)
- [IBM: What Is Data Poisoning](https://ibm.com/think/topics/data-poisoning)
