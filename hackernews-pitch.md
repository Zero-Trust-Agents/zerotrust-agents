# Hacker News Pitch

**Title**: Show HN: ZeroTrust Agents – An open-core firewall for autonomous AI agents

**URL**: https://github.com/Zero-Trust-Agents/zerotrust-agents

**Body**:
Hey HN!

As we build more autonomous AI agents (rather than just copilots), we're giving them access to our databases, APIs, and file systems. The problem is that prompt injection is effectively arbitrary code execution for agents.

Currently, most people try to secure their agents by adding "guardrails" directly into their LangChain/LlamaIndex code. But if the LLM is compromised, the guardrails running in the same context can be bypassed.

We built ZeroTrust Agents (ZTA) to decouple security from the agent framework. It acts as a dedicated API gateway (proxying OpenAI, Anthropic, Gemini).

When your agent tries to call a tool, ZTA intercepts it and enforces:
1. Semantic DLP (redacting API keys or SSNs from payloads)
2. Granular RBAC (agents only get access to specific tools)
3. Human-in-the-loop (suspending execution via WebSockets until an admin approves a destructive action in Slack/Discord)

It's open-core under BSL 1.1 (converts to Apache 2.0 after 4 years). 
Would love your feedback on the architecture or any security features you think are missing!
