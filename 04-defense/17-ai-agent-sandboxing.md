# Bài 17: AI Agent Sandboxing — Isolation Architecture 2026

## Core Principle

> "Agents don't have values or boundaries — they'll call whatever tools you give them." — Bitloops

> "Container isolation alone is insufficient for untrusted AI-generated code execution." — Ikangai

## 3 Dominant Isolation Technologies (2026)

| Technology | Strength | Use Case |
|-----------|----------|----------|
| **Firecracker microVMs** | Strongest isolation | Regulated data, financial services |
| **gVisor** | Syscall-level filtering | Compute-heavy multi-tenant |
| **V8 Isolates** | JS-only, minimal overhead | Latency-critical lightweight tasks |

## 5 Isolation Tiers in Production

1. **OS process level** (Seatbelt, bubblewrap)
2. **Container with restricted syscalls**
3. **gVisor (user-space kernel)**
4. **Firecracker microVM**
5. **Dedicated hardware VM with full kernel separation**

## Sandbox Architecture Must Control

- What the agent can **see**
- What it can **write**
- What it can **call**
- Which **secrets** it can touch
- How **files move** in and out
- How **long** work can run
- How **humans review** risky actions

## NVIDIA Security Guidance

- Block writes to **configuration files** — prevents exploitation of hooks, skills, MCP configs
- MCP configurations often run **outside sandbox context**

## Common Mistake

> "Most teams ship their first code-executing agent with exactly one security control: API key scoping. This is wrong." — Tianpan.co

## References

- [BeyondScale: AI Agent Sandboxing Enterprise Guide](https://beyondscale.tech/blog/ai-agent-sandboxing-enterprise-security-guide)
- [NVIDIA: Sandboxing Agentic Workflows](https://developer.nvidia.com/blog/practical-security-guidance-for-sandboxing-agentic-workflows-and-managing-execution-risk)
- [Northflank: How to Sandbox AI Agents 2026](https://northflank.com/blog/how-to-sandbox-ai-agents)
- [Pillar Security: AI Agent Untrusted Code](https://www.pillar.security/blog/your-ai-agent-will-run-untrusted-code-now-what)
