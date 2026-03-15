# Build Your Own AIOps Agent Using MCP

**Speaker:** [Shiv Kumar Sah](https://www.linkedin.com/in/shivkumarsah)
**Duration:** 2:30 PM – 3:00 PM IST

## Key takeaways

- **MCP turns passive chatbots into active agents** — structured JSON-RPC over stdio gives LLMs deterministic, auditable access to tools
- **Privacy-first is achievable** — run Ollama locally and never send infrastructure data to the cloud
- **psutil is your data layer** — a single Python library covers CPU, memory, disk, network, and process metrics for most monitoring needs
- **Mock mode unblocks development** — test the full agent loop without real infrastructure or production credentials
- **MCP is extensible by design** — add a new tool by defining one function; the LLM discovers it automatically at runtime
- **Natural language ops is the end goal** — "What's consuming the most CPU right now?" should be a valid ops query, not a dashboard click

## About this session

A practical session on building a privacy-first AIOps agent using the Model Context Protocol (MCP). Covers MCP architecture, running local LLMs via Ollama, and real-world use cases including log analysis, system health scoring, and performance monitoring — all without any cloud dependency.

## Key concepts

### Why AIOps with MCP?

Traditional infrastructure monitoring has three core problems:
- **Manual monitoring** — prone to human error and slow response times
- **Fragmented tools and scattered logs** — multiple systems complicate analysis
- **Lack of intelligence** — reactive rather than proactive

MCP solves this by turning passive chatbots into active agents, enabling structured and safe LLM-to-tool communication via JSON-RPC over stdio. Think of it as a universal connector — like USB-C for AI tools.

### Understanding MCP (Model Context Protocol)

| Concept | Description |
|---------|-------------|
| **Protocol** | Standard for LLM-to-tool interactions using JSON-RPC over stdio |
| **Before MCP** | Every AI client needed custom integrations with every tool — a tangled web |
| **After MCP** | One standard protocol connects any LLM client to any tool server |
| **Key benefit** | Deterministic, auditable, and secure tool usage — reduces hallucinations |

**How it works (5 steps):**
1. User sends a request to the LLM
2. AI identifies the needed tools
3. AI queries MCP servers via JSON-RPC
4. Servers return results
5. AI composes the final response

### InfraGPT-MCP — The Demo Project

The session's hands-on project is **InfraGPT-MCP**, a local AIOps agent with:

**Architecture layers:**
- **LLM Client** (Claude Desktop or any MCP-compatible client) — sends requests
- **MCP Server as middleware** — receives requests, calls system tools via JSON-RPC
- **System tools** — `psutil` for metrics, log readers for analysis
- **Optional local AI** — Gemini or Ollama for on-prem analysis (zero cloud dependency)

**Built-in tools:**
- System info
- Service status
- Log analysis
- Network monitoring
- User info
- Health check

**Key features:**
- **Conversational monitoring** — query your infrastructure in natural language
- **Privacy-first** — 100% local data handling, mock mode for testing
- **Open & extensible** — add your own tools, supports any on-prem LLM

### Real-world use cases

| Use case | What it does |
|----------|--------------|
| **System health scoring** | Generates health scores and actionable optimization recommendations |
| **Security log analysis** | Analyzes login events, detects threats, summarizes for incident response |
| **Performance monitoring** | Identifies top CPU-consuming processes, delivers real-time resource insights |

## Further reading & tools

| Resource | What it is |
|----------|------------|
| [InfraGPT-MCP](https://github.com/shivkumarsah/InfraGPT-MCP) | The demo project from this session — fully local AIOps agent with MCP |
| [MCP Specification](https://modelcontextprotocol.io/) | Official MCP protocol docs and server/client implementation guides |
| [FastMCP](https://github.com/jlowin/fastmcp) | Build MCP servers easily in Python with minimal boilerplate |
| [Ollama](https://ollama.com/) | Run LLMs locally — Llama 3, Mistral, Gemma, and more |
| [psutil](https://github.com/giampaolo/psutil) | Python library for system metrics: CPU, memory, disk, network, processes |
| [Claude Desktop](https://claude.ai/download) | MCP-compatible LLM client for testing your MCP servers locally |

## Slides

[Shiv_BuildYourOwnAIOpsAgentUsingMCP-latest.pdf](Shiv_BuildYourOwnAIOpsAgentUsingMCP-latest.pdf)

## Resources

- **GitHub (code + slides):** [shivkumarsah/InfraGPT-MCP](https://github.com/shivkumarsah/InfraGPT-MCP)
- **Speaker on LinkedIn:** [Shiv Kumar Sah](https://www.linkedin.com/in/shivkumarsah)

## About the speaker

**[Shiv Kumar Sah](https://www.linkedin.com/in/shivkumarsah)** — DevOps/Platform Engineer at Adobe. M.Tech in Cloud Computing from IIT Patna, 10+ years in software engineering and cloud. Designs and operates high-availability Kubernetes and OpenShift platforms, builds automation frameworks, and develops AI-driven incident remediation systems.
