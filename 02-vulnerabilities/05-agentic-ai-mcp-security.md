# Bài 5: Agentic AI & MCP Security — Attack Surface Mới Nhất

## MCP (Model Context Protocol) — Fastest-Growing Attack Surface

Trong 2 tháng đầu 2026, security researchers filed **~30 CVEs** chống lại MCP servers, clients, và infrastructure. So sánh: cả năm 2025 chỉ có ~15 CVEs.

## 7 MCP Security Risks

| Risk | Impact |
|------|--------|
| Prompt Injection through tool outputs | Agent bị manipulate qua kết quả tool trả về |
| Tool Poisoning | Malicious tool masquerade as legitimate |
| Over-permissioned tool surfaces | Tools có quyền hơn cần thiết |
| Data exfiltration via context window | Dữ liệu nhạy cảm leak qua model context |
| Supply-chain attacks on MCP packages | Giống npm/pypi attacks nhưng cho AI tools |
| Weak authentication & token sprawl | MCP servers thiếu auth cơ bản |
| Unredacted sensitive data in context | PII/secrets flow vào model context |

## Case Study: Anthropic Git MCP Server (Jan 2026)

- Reference implementation mà cả ecosystem copy
- Bugs: **path traversal** và **argument injection**
- Impact: Mọi project copy code đều vulnerable

## RCE by Design

Anthropic's reference MCP implementation có **unsafe defaults** trong STDIO interface:
- Config cho phép remote code execution
- Architectural decision ảnh hưởng toàn bộ agent ecosystem

## Trend Micro Research: 19,000 MCP Servers Scanned

- **4.1%** có vulnerabilities genuinely exploitable
- Top vulnerabilities: SQL injection, RCE, path traversal
- Cloud Security Alliance: 1,862 servers exposed, **100%** cho unauthenticated access

## Defense Recommendations

```yaml
# MCP Server Security Checklist
authentication:
  - Require auth for ALL endpoints
  - Use short-lived tokens, not long-lived API keys
  - Implement mutual TLS where possible

authorization:
  - Principle of least privilege per tool
  - Define explicit capability boundaries
  - Audit all tool invocations

input_validation:
  - Treat ALL tool outputs as untrusted
  - Schema validation for structured responses
  - Sanitize before passing to LLM context

monitoring:
  - Log all tool calls with full context
  - Alert on unusual patterns
  - Rate limiting per agent session
```

## References

- [Trend Micro: 19,000 MCP Servers Scanned](https://www.trendmicro.com/vinfo/us/security/news/vulnerabilities-and-exploits/hunt-them-all-an-ai-powered-vulnerability-sweep-of-19-000-mcp-servers)
- [Strac.io: 7 MCP Security Risks](https://www.strac.io/blog/mcp-security)
- [CSOnline: RCE by Design in MCP](https://www.csoonline.com/article/4159889/rce-by-design-mcp-architectural-choice-haunts-ai-agent-ecosystem.html)
- [Amino RJ: MCP's First Year Analysis](https://aminrj.com/posts/mcp-security-after-1year/)
- [Cloud Security Alliance: MCP Authentication Vacuum](https://cloudsecurityalliance.org/articles/the-agentic-trust-deficit-why-mcp-s-authentication-vacuum-demands-a-new-security-paradigm)
