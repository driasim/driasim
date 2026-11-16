# Ibrahim Aliyu Saddique (`@driasim`)

**Software Systems Engineer & Distributed Architect**  
*Building resilient distributed backends, developer infrastructure, low-latency runtimes, and autonomous execution boundaries.*

---

### 🏛️ Engineering Philosophy: Beyond the AI Hype

Anyone can call an API or wrap an LLM in a prompt. Real software engineering begins when these non-deterministic systems touch production infrastructure:

* **Fault Tolerance & Circuit Breaking:** Distributed failure domains, cascading timeout protection, entropy tracking, and automated circuit breakers for unreliable external dependencies.
* **Process Sandboxing & Boundary Security:** Subprocess isolation, abstract syntax tree (AST) static inspection, resource quotas, and zero-trust execution for untrusted workloads.
* **Protocol & Systems Engineering:** Translating heterogeneous API standards (OpenAPI, Swagger, JSON-RPC 2.0, MCP, gRPC, SSE) into clean, type-safe developer interfaces.
* **Durable State Machines:** Workflows that outlive single HTTP requests—durable SQLite/Postgres checkpointing, crash recovery, and multi-tenant task isolation.
* **FinOps & Telemetry at Scale:** OpenTelemetry distributed tracing, millisecond latency profiling, and real-time budget enforcement gates.

---

### 📦 Systems & Infrastructure Open Source Projects

A suite of 10 production-tested software systems, developer tools, and distributed infrastructure packages:

| Project | Core Domain | Architectural Focus & Technical Highlights |
| :--- | :--- | :--- |
| [**`openapi-to-mcp`**](https://github.com/driasim/openapi-to-mcp) | **Protocol Engineering** | Zero-boilerplate JSON-RPC 2.0 stdio engine auto-generating Model Context Protocol tools from OpenAPI 3.x/Swagger specs. |
| [**`agent-sandbox-daemon`**](https://github.com/driasim/agent-sandbox-daemon) | **Systems & Security** | Sandboxed execution daemon with AST static security auditing (blocking socket/subprocess escapes), resource limits, and timeout guards. |
| [**`agent-eval-harness`**](https://github.com/driasim/agent-eval-harness) | **Systems Reliability** | Deterministic trajectory evaluation harness with invariant state assertion, entropy loop detection, and economic drift tracking. |
| [**`agent-vcr`**](https://github.com/driasim/agent-vcr) | **Developer Tooling** | Deterministic cassette recording and mock engine allowing non-deterministic distributed tests to run offline in <5ms for $0. |
| [**`monoagent-runtime`**](https://github.com/driasim/monoagent-runtime) | **Distributed Runtimes** | Stateful orchestration kernel with multi-step durable checkpointing, tiered shared memory, circuit breakers, and OpenTelemetry instrumentation. |
| [**`hitl-approval-gateway`**](https://github.com/driasim/hitl-approval-gateway) | **Policy & Governance** | Rule-driven authorization gateway that intercepts high-risk system/financial actions and enforces human approval workflows. |
| [**`agent-finops-sentinel`**](https://github.com/driasim/agent-finops-sentinel) | **FinOps & Cost Control** | Real-time budget enforcement service tracking multi-tenant compute burn rates with soft threshold alerts and hard circuit cut-offs. |
| [**`llm-smart-router`**](https://github.com/driasim/llm-smart-router) | **Traffic & Routing** | Structural complexity classifier and fallback proxy routing traffic across tiers with automated failover cascades. |
| [**`graph-memory-engine`**](https://github.com/driasim/graph-memory-engine) | **Graph Topologies** | Temporal knowledge graph engine with multi-hop BFS traversal, relationship invalidation, and state superseding. |
| [**`browser-intent-worker`**](https://github.com/driasim/browser-intent-worker) | **Web & Automation** | Semantic DOM tree reduction engine compressing bloated HTML by 85%+ into reliable, accessible interactive state models. |

---

### 🛡️ Production Engineering Patterns & Post-Mortems

#### 1. Circuit Breakers Over Exponential Backoff in Infinite Loops
* **The Failure:** An internal integration tool started returning empty payloads (`[]`) during a partial database partition. The upstream worker interpreted this as "query succeeded with zero results" and looped 42 consecutive times trying alternative filter arguments, burning thousands of compute units before hitting hard timeouts.
* **The Solution:** Built a **Tool Execution Circuit Breaker** tracking payload entropy and argument hashes. If a worker calls the same service 3 consecutive times with zero state delta, the circuit immediately trips and halts execution.

#### 2. The Model Upgrade "Silent Regression" Trap
* **The Failure:** Swapping foundational model versions improved general reasoning benchmarks by 4%, but broke strict JSON schema validation by 18% in multi-step enterprise workflows due to altered formatting priors.
* **The Solution:** Implemented `agent-eval-harness` to run regression diffs on 250+ production trajectories with golden schema assertions, diffing latency, cost, and tool call accuracy before releasing prompt or model updates.

#### 3. Why Internal Workflow Tools Get Abandoned
* **Observation:** Deploying free-form chat interfaces for technical workflows consistently results in a novelty spike followed by 80% abandonment within 4 weeks. Users don't want to write essays to execute repeatable work.
* **The Solution:** Shifted to **headless, event-driven monoagents embedded into existing developer pipelines** (CI webhook triggers, scheduled SRE cron jobs, Jira automation) with narrow, deterministic playbooks.

---

### 🧰 Technical Stack & Systems Competencies

* **Languages:** Python (FastAPI, Pydantic, AsyncIO), TypeScript / Node.js, Go, SQL
* **Protocols & RPC:** Model Context Protocol (MCP), JSON-RPC 2.0, OpenAPI / Swagger, REST, WebSockets, Server-Sent Events (SSE)
* **Architecture & Patterns:** State Machines, Event-Driven Architecture, Circuit Breakers, AST Static Analysis, Multi-Tenant Isolation
* **Storage & Graphs:** PostgreSQL + `pgvector`, Redis (caching / rate limiting), Knowledge Graphs (BFS/DFS), SQLite durable journals
* **Reliability & DevOps:** OpenTelemetry, Prometheus, Grafana, Docker, GitHub Actions CI/CD, Pytest

---

### 📬 Connect
* **GitHub:** [github.com/driasim](https://github.com/driasim)
* **Email:** [ibraheemaliyu32@gmail.com](mailto:ibraheemaliyu32@gmail.com)
