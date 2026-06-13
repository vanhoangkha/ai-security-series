# Bài 11: RAG Security — Khi Knowledge Base Trở Thành Attack Vector

## RAG-Specific Threat Model

RAG systems inherit LLM vulnerabilities PLUS new attack surfaces:
- Retrieval pipeline
- Vector databases
- External knowledge sources
- Document ingestion pipeline

## Knowledge Base Poisoning

**Research finding:** Chỉ cần **10 adversarial passages** (0.04% of corpus) → **98.2% retrieval success rate**

Attack flow:
1. Attacker inject malicious documents vào knowledge base
2. RAG retrieves poisoned content
3. LLM generates response based on poisoned context
4. User receives manipulated output

## Attack Types

| Type | Description |
|------|-------------|
| Corpus poisoning | Inject documents vào shared/public knowledge base |
| Indirect prompt injection via docs | Ẩn instructions trong documents được index |
| Visual document poisoning | Poison single image trong PDF pipeline |
| Word-level poisoning | Subtle text modifications mà human khó detect |
| Data exfiltration via RAG | Extract sensitive data through crafted queries |

## Stealthy Attacks

- Attention-aware poisoning — target specific attention patterns
- Corpus-dependent attacks — adapt theo target corpus
- Word-level refinement — minimal, hard-to-detect modifications

## Defense Strategies

1. **Provenance tracking** — Biết source của mọi document
2. **Access control cho ingestion** — Không phải ai cũng được add documents
3. **Anomaly detection** — Monitor retrieval patterns
4. **Content signing** — Verify document integrity
5. **Attention-aware filtering** — Detect poisoned passages
6. **Sandboxed RAG** — Separate sensitive data vào isolated indices

## References

- [Arxiv: Corpus-Dependent Poisoning in RAG](https://arxiv.org/html/2603.18034v1)
- [Arxiv: Provenance-Verified Defense for Government RAG](https://arxiv.org/html/2604.00387)
- [Arxiv: RAG Security Taxonomy](https://arxiv.org/html/2604.08304)
- [Arxiv: Knowledge Poisoning Attack on RAG](https://arxiv.org/html/2505.11548v4)
- [Arxiv: Attention-Aware Defenses Against Poisoning](https://arxiv.org/html/2506.04390v2)
