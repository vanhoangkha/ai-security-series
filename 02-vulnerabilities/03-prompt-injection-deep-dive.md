# Bài 3: Prompt Injection Deep Dive — Tấn Công và Phòng Thủ

## Prompt Injection là gì?

> "Prompt injection is the XSS of the AI era." — Arxiv Research 2025

Giống như XSS khai thác trust boundary giữa data và code trong web, prompt injection khai thác việc LLM không phân biệt được trusted instructions và adversarial input.

## Phân loại

**Direct Prompt Injection:**
- User trực tiếp gửi malicious prompt
- Mục tiêu: instruction hijacking, data exfiltration

**Indirect Prompt Injection:**
- Malicious text ẩn trong external content (web pages, documents, emails)
- Khi AI xử lý content đó → text biến thành instructions

**Multimodal Prompt Injection:**
- Ẩn instructions trong images, audio, hoặc other modalities

## Research Findings 2026

Theo arxiv research (2026):
- Inference-time defenses (filters không cần retraining) **bị bypass bởi long, reasoning-heavy prompts**
- Các model khác nhau có behavioral variation đáng kể
- Một số model có "silent non-responsiveness" — internal safety mechanisms trigger nhưng không có output

## Defense Patterns (Arxiv — Design Patterns for Securing LLM Agents)

1. **Privilege Separation** — Tách LLM reasoning khỏi action execution
2. **Dual LLM Pattern** — Một model xử lý untrusted input, model khác thực hiện actions
3. **Input/Output Monitoring** — Detect injection patterns trước/sau processing
4. **Capability-based Access Control** — Giới hạn tools mà agent có thể gọi dựa trên context

## Novel Defense: "Inverting the Attack"

Dùng chính kỹ thuật tấn công làm defense — repeat attack process nhưng với original instruction thay vì injected instruction, essentially "re-injecting" the legitimate prompt.

## Adaptive Attackers

Nghiên cứu mới nhất test 20,000+ attacks với adaptive attacker evolve strategies qua hàng trăm rounds. Kết quả: **không có defense nào là bullet-proof** — cần defense-in-depth approach.

## References

- [Arxiv: Securing AI Agents Against Prompt Injection](https://arxiv.org/html/2511.15759)
- [Arxiv: Evaluation of Prompt Injection Defenses](https://arxiv.org/html/2604.23887v1)
- [Arxiv: Defense Against Prompt Injection by Leveraging Attack Techniques](https://arxiv.org/html/2411.00459v5)
- [Arxiv: Design Patterns for Securing LLM Agents](https://arxiv.org/html/2506.08837)
- [BeyondScale: Prompt Injection Detection & Defense](https://beyondscale.tech/blog/prompt-injection-attacks-defense-guide)
