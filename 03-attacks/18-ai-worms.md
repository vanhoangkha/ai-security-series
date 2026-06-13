# Bài 18: AI Worms — Self-Propagating Agent Malware

## Morris II (2024 Research → 2026 Reality)

Original PoC: Worm thiết kế cho GenAI ecosystems:
- Single poisoned email → AI assistant reads, steals, và **resends** confidential messages
- **Zero-click** — không cần user interaction
- Spreads across multiple AI platforms

## June 2026: University of Toronto Prototype

- Self-replicating AI worm powered by **local, open-weight LLM**
- OS-agnostic, self-propagating
- On 33-host network: identified **31.3 vulnerabilities**, gained elevated access on **23.1 hosts** (75%)
- Runs entirely on local models — **không cần frontier AI**

> "Attackers don't need Mythos to take over your network" — CSOnline

## Attack Mechanism

1. Worm enters via GenAI-powered application
2. Inserts adversarial prompt vào processed content
3. Model processes content → replicates prompt as output (self-replication)
4. Engages in malicious activities (payload)
5. Spreads to next connected AI application

## Self-Propagating Across Agent Ecosystems

- Long-running LLM agents form **densely interconnected multi-agent ecosystems**
- Security properties remain **largely unexplored**
- Attacks propagate through agent-to-agent communication

## Implications

- Traditional antivirus/EDR **không detect** — no file, no binary
- Propagation mechanism is **natural language**, not code
- Defense requires **semantic monitoring** của agent communications

## References

- [The Hacker News: Self-Replicating AI Worm (June 2026)](https://thehackernews.com/2026/06/researchers-build-self-replicating-ai.html)
- [CSOnline: AI Worm Prototype](https://www.csoonline.com/article/4181924/ai-worm-prototype-shows-attackers-dont-need-mythos-to-take-over-your-network.html)
- [Arxiv: Self-Propagating Attacks Across LLM Agent Ecosystems](https://arxiv.org/html/2603.15727)
- [Arxiv: Morris II — Zero-click Worms for GenAI](https://arxiv.org/html/2403.02817v2)
- [IBM: Malicious AI Worm Targeting GenAI](https://www.ibm.com/think/insights/malicious-ai-worm-targeting-generative-ai)
