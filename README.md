# Ibrahim Aliyu Saddique (`@driasim`)

**AI Systems & Agent Infrastructure Engineer**  
Specializing in **production LLM agents**, multi-turn evaluation harnesses, MCP tool ecosystems, shared organizational memory, and long-running sandboxed execution.

---

### 🛠️ What I Focus On (The Unspoken Layers of Production Agents)

Most agent demos work in a 3-turn sandbox. In production, real agents fail at the boundaries:
* **Evaluation & Regression Detection:** How to mathematically and deterministically know whether an agent got better or worse when a prompt, tool signature, or foundational model changes.
* **Internal Monoagents & Shared Memory:** Connecting disparate corporate silos through a resilient monoagent architecture with episodic, working, and organizational memory.
* **Long-Running & Sandboxed Agents:** Resilient execution that outlives single HTTP requests—durable checkpointing, background schedules, and sandboxed runtimes.
* **Tool & MCP Surfaces:** Hardening Model Context Protocol (MCP) servers with validation schemas, circuit-breakers, and fallback policies against runaway tool loops.
* **Cost & Observability Telemetry:** Real-time token budgets, latency profiling, OpenTelemetry trajectory tracing, and per-user cost attribution.

---

### 🚀 Production Agent Infrastructure Ecosystem

A suite of 10 production-grade, tested, and cloneable repositories solving foundational problems in enterprise agent engineering:

| Repository | Domain | Architecture & Highlights |
| :--- | :--- | :--- |
| [**`openapi-to-mcp`**](https://github.com/driasim/openapi-to-mcp) | **Tooling & MCP** | Zero-boilerplate bridge converting any OpenAPI/Swagger REST API into native MCP tools for Claude Desktop, Cursor, and AI agents. |
| [**`agent-eval-harness`**](https://github.com/driasim/agent-eval-harness) | **Evals & CI** | Trajectory evaluation engine detecting runaway retry loops, tool schema regressions, and token/cost drift before deployment. |
| [**`agent-vcr`**](https://github.com/driasim/agent-vcr) | **Testing & Mocks** | Deterministic record & replay mock engine allowing multi-turn agent CI integration tests to run offline in milliseconds for $0. |
| [**`monoagent-runtime`**](https://github.com/driasim/monoagent-runtime) | **Kernel & Runtime** | Enterprise monoagent kernel supporting durable task checkpoints, hierarchical shared memory, MCP routing, and OTel telemetry. |
| [**`agent-sandbox-daemon`**](https://github.com/driasim/agent-sandbox-daemon) | **Security & Sandboxing** | Safe code execution environment with static AST security analysis (blocking dangerous imports), timeouts, and process boundaries. |
| [**`hitl-approval-gateway`**](https://github.com/driasim/hitl-approval-gateway) | **Safety & Governance** | Policy middleware that intercepts destructive/financial tool calls and halts execution until human operator sign-off. |
| [**`agent-finops-sentinel`**](https://github.com/driasim/agent-finops-sentinel) | **FinOps & Cost Control** | Real-time token metering and budget enforcement that alerts at 80% soft thresholds and triggers hard cut-offs to prevent runaway spend. |
| [**`llm-smart-router`**](https://github.com/driasim/llm-smart-router) | **Routing & Fallback** | Heuristic complexity classifier routing simple queries to cheap models and complex reasoning to flagship tiers with automatic failover. |
| [**`graph-memory-engine`**](https://github.com/driasim/graph-memory-engine) | **Memory Architecture** | Temporal knowledge graph and episodic memory engine with multi-hop BFS traversal and relationship superseding. |
| [**`browser-intent-worker`**](https://github.com/driasim/browser-intent-worker) | **Browser Automation** | Semantic accessibility tree extractor compressing noisy HTML by 85%+ into high-reliability interactive intent targets. |

---

### 🛡️ Production War Stories & Architecture Trade-offs

#### 1. The Runaway Tool-Call Loop & Circuit Breaker Pattern
* **The Failure:** A refactored internal database query tool started returning partial empty arrays instead of explicit errors. The agent entered a silent recursive retry loop across 42 consecutive turns trying alternative query parameters, burning $78 of API tokens on a single background request before hitting the global timeout.
* **The Fix:** Implemented a **Tool Execution Circuit Breaker** in the agent runtime. The harness tracks tool invocation entropy, deduplicates identical argument payloads, and trips an automated human-in-the-loop (HITL) interrupt if the same tool fails or returns zero state delta more than 3 times consecutively.

#### 2. The Model Upgrade "Silent Regression" Trap
* **The Failure:** Upgrading from an earlier foundational model to a newer, higher-benchmark release improved general MMLU reasoning by 4%, but degraded strict JSON schema tool adherence by 18% in multi-step enterprise workflows.
* **The Fix:** Built `agent-eval-harness` to run replay evals on 250+ production trajectories with golden tool assertions, semantic diffing, and cost-per-successful-resolution ratios before any prompt or model deployment.

#### 3. Organizational Adoption: Why Internal Assistants Fail
* **Observation:** Building a general-purpose chat interface resulted in high initial excitement followed by 80% silent abandonment within 4 weeks. Non-technical staff didn't want to prompt-engineer their queries.
* **The Shift:** Pivoted to **headless monoagents triggered via native workflows** (PR reviews, daily scheduled Slack briefings, automated Jira triage). Giving agents narrow, deterministic playbooks with explicit operational memory increased sustained weekly active utilization by 340%.

---

### 🧰 Technical Stack & Tooling

* **Agent Runtimes & Frameworks:** Custom Kernel architectures, LangGraph, LlamaIndex, LiteLLM
* **Protocol & Interoperability:** Model Context Protocol (MCP), OpenAPI / Swagger, SSE, WebSocket streaming
* **Evaluations & Testing:** DeepEval, Trajectory Replay, Pytest, Deterministic State Assertions, VCR mocks
* **Memory & Storage:** PostgreSQL + `pgvector`, Redis (session buffers), Knowledge Graphs, SQLite durable logs
* **Observability & Ops:** OpenTelemetry, Prometheus, Langfuse, Grafana, Docker/Cloud Sandboxes
* **Languages:** Python (FastAPI, Pydantic, AsyncIO), TypeScript / Node.js, Go

---

### 📬 Connect
* **GitHub:** [github.com/driasim](https://github.com/driasim)
* **Email:** [ibraheemaliyu32@gmail.com](mailto:ibraheemaliyu32@gmail.com)
