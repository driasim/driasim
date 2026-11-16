# Ibrahim Aliyu Saddique

**Full-Stack & Mobile Developer**  
*Building apps people actually use and the backend services that keep them running.*

[GitHub](https://github.com/driasim) • [Email](mailto:ibraheemaliyu32@gmail.com)

---

### About Me

I’m a software developer who builds across the whole stack: user-facing web applications, cross-platform mobile apps on iOS and Android, and the backend services powering them. 

Whether I’m tuning a smooth mobile screen transition, handling offline SQLite synchronization, or writing execution sandboxes and background worker queues that don't choke under load, I focus on software that is fast, resilient, and simple to maintain.

---

### What I Work On

* **📱 Mobile (iOS & Android):** Cross-platform apps using React Native and Flutter. I pay close attention to offline resilience, optimistic UI updates, local storage (SQLite, MMKV), and keeping memory and battery draw minimal.
* **💻 Web Applications:** Production web apps using React, Next.js, and TypeScript. I care about snappy load times, clean component boundaries, and real-time WebSocket state that doesn't desync.
* **⚙️ Backends & API Services:** High-throughput APIs, background workers, and microservices in Python (FastAPI), Node.js, and Go. I design around PostgreSQL, Redis caching, event-driven task queues, and clear failure domains.
* **🛠️ Developer Tooling & Agent Runtimes:** The critical plumbing around autonomous workflows—safe code execution sandboxes, REST-to-MCP bridges, deterministic record/replay testing harnesses, and spend-guard sentinels.

---

### Open Source Projects

Here are 10 production-tested tools and systems I built, documented, and published:

| Project | What It Solves |
| :--- | :--- |
| [**`openapi-to-mcp`**](https://github.com/driasim/openapi-to-mcp) | Turns any OpenAPI/Swagger REST API into a working Model Context Protocol (MCP) server for Claude Desktop and Cursor without writing glue code. |
| [**`browser-intent-worker`**](https://github.com/driasim/browser-intent-worker) | Strips 85%+ of noisy HTML bloat into a clean, accessible interaction tree so browser agents don't blow up token budgets or click broken selectors. |
| [**`agent-sandbox-daemon`**](https://github.com/driasim/agent-sandbox-daemon) | A secure code runner that uses static AST analysis to block socket/subprocess escapes, enforcing CPU limits and timeouts on untrusted scripts. |
| [**`monoagent-runtime`**](https://github.com/driasim/monoagent-runtime) | A stateful agent kernel with durable database checkpoints, multi-tiered shared memory, tool circuit breakers, and OpenTelemetry cost tracing. |
| [**`agent-vcr`**](https://github.com/driasim/agent-vcr) | Records external API and LLM responses into version-controlled JSON cassettes so integration tests run offline in milliseconds for $0. |
| [**`agent-eval-harness`**](https://github.com/driasim/agent-eval-harness) | Catches regressions before production: tests multi-turn agent paths, verifies tool argument schemas, and flags token cost explosions. |
| [**`hitl-approval-gateway`**](https://github.com/driasim/hitl-approval-gateway) | Intercepts high-risk or financial actions (database writes, refunds, shell commands) and pauses execution until a human signs off. |
| [**`agent-finops-sentinel`**](https://github.com/driasim/agent-finops-sentinel) | Real-time token and budget monitor that warns teams at 80% usage and hard-stops runaway jobs before cloud bills get out of hand. |
| [**`llm-smart-router`**](https://github.com/driasim/llm-smart-router) | Evaluates query complexity to route simple tasks to fast/cheap models and hard reasoning to flagship models, with automatic failover. |
| [**`graph-memory-engine`**](https://github.com/driasim/graph-memory-engine) | A temporal knowledge graph that handles relationship updates and multi-hop lookups without the factual collisions common in flat vector search. |

---

### How I Think About Development

#### 1. Offline-first isn't optional on mobile
People use apps in elevators, basements, and on spotty train Wi-Fi. If an app freezes or dumps user input because a network request timed out, that’s a bug, not a user mistake. Optimistic UI with reliable local queuing makes all the difference.

#### 2. Protect your dependencies (and yourself) with circuit breakers
External services and APIs eventually slow down, return empty arrays, or fail outright. If your backend naively retries in an unbounded loop, it will lock worker threads and burn budget. Circuit breakers that track consecutive empty or failing responses prevent small glitches from becoming full outages.

#### 3. Meet users where they already spend their time
Developers and team members rarely want another separate portal or complex dashboard to check. The most adopted tools are headless—they trigger on a GitHub PR, post an update into Slack, or run as a background cron job that quietly gets work done.

---

### Technical Toolbox

* **Mobile:** React Native, Expo, Flutter, SQLite, MMKV, Push Notifications, Native Bridges
* **Frontend:** React, Next.js, TypeScript, Tailwind CSS, Vite, HTML5/CSS3
* **Backend:** Python (FastAPI, AsyncIO), Node.js, Express, Go, REST, WebSockets, GraphQL
* **Data & Storage:** PostgreSQL, Redis, SQLite, pgvector, Supabase, Firebase
* **Infrastructure & Ops:** Docker, OpenTelemetry, Linux / Bash, GitHub Actions CI/CD, Pytest, Jest
* **Protocols:** MCP (Model Context Protocol), JSON-RPC 2.0, OpenAPI / Swagger

---

### Get In Touch
* **GitHub:** [github.com/driasim](https://github.com/driasim)
* **Email:** [ibraheemaliyu32@gmail.com](mailto:ibraheemaliyu32@gmail.com)
