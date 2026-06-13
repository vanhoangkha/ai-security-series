# Bài 27: LLM API & Inference Endpoint Security

## The Economics

> "A single prompt to an agent on a frontier model can cost $2, making AI a million times more expensive than traditional API calls." — Vercel

## Key Differences from Traditional APIs

| Aspect | Traditional API | LLM API |
|--------|----------------|---------|
| Output | Deterministic | Non-deterministic |
| Rate limiting | Request count | Must be **token-aware** |
| Cost per request | Predictable | Highly variable |
| Abuse detection | Pattern-based | Needs semantic analysis |

## LLMjacking Attack Pattern

1. Steal cloud credentials
2. Call expensive model services
3. Turn victim's account into compute backend
4. Cost: $46K-$100K+ per day

## Self-Hosted Risks

- **vLLM and Ollama** ship with authentication gaps
- Require explicit remediation
- Default configs often expose inference endpoints

## Defense Architecture

```python
# Token-aware rate limiting
class TokenRateLimiter:
    def check(self, user_id, estimated_tokens):
        usage = get_usage(user_id, window="1h")
        if usage + estimated_tokens > user_limit:
            raise RateLimitExceeded(retry_after=calculate_backoff())

# Spend controls
class SpendGuard:
    def check(self, org_id, estimated_cost):
        daily_spend = get_daily_spend(org_id)
        if daily_spend + estimated_cost > daily_budget:
            alert_security_team(org_id, daily_spend)
            raise BudgetExceeded()
```

## References

- [Vercel: Protecting Against Inference Theft](https://vercel.com/blog/protecting-against-inference-theft)
- [BeyondScale: LLM Inference API Security](https://beyondscale.tech/blog/llm-inference-api-security)
- [Zuplo: Token-Based Rate Limiting for AI Agents](https://zuplo.com/learning-center/token-based-rate-limiting-ai-agents)
- [GMI Cloud: Inference Security for Production AI](https://www.gmicloud.ai/blog/inference-security-how-to-protect-apis-in-production-ai-systems)
