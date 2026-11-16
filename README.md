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

### 🚀 Flagship Open Source Projects

| Repository | Focus & Architecture | Highlights |
| :--- | :--- | :--- |
| [**`agent-eval-harness`**](https://github.com/driasim/agent-eval-harness) | **Regression & Trajectory Evaluation Framework** | Deterministic trajectory assertions, tool-call schema diffs, semantic LLM judges, token/cost drift benchmarks. |
| [**`monoagent-runtime`**](https://github.com/driasim/monoagent-runtime) | **Production Enterprise Agent Kernel** | Long-running task queue, shared hierarchical memory (Postgres/pgvector), MCP client/server tooling, OpenTelemetry tracing. |

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
* **Evaluations & Testing:** DeepEval, Ragas, Trajectory Replay, Pytest, Deterministic State Assertions
* **Memory & Storage:** PostgreSQL + `pgvector`, Redis (session buffers), ChromaDB, SQLite durable logs
* **Observability & Ops:** OpenTelemetry, Prometheus, Langfuse, Grafana, Docker/Cloud Sandboxes
* **Languages:** Python (FastAPI, Pydantic, AsyncIO), TypeScript / Node.js, Go

---

### 📬 Connect
* **GitHub:** [github.com/driasim](https://github.com/driasim)
* **Email:** [ibraheemaliyu32@gmail.com](mailto:ibraheemaliyu32@gmail.com)
