## **Artifacts & Rubric**
### **Required Submission Artifacts**

* **Code repo** with one-command setup (README quickstart), .env.sample, and seed/test data or fixtures.

* **Architecture & threat model one-pager**: boundaries, data flows, risks → mitigations.

* **Observability proof**: one trace screenshot or link; sample logs/metrics.

* **Demo video (≤3 min) or live demo** hitting the happy path \+ 1 failure path.

* **Short post-mortem note**: what broke during hacking and how you fixed it.

### **1\) Business Value & User Impact — 20 pts**

**What this means:** You’re solving a real B2B/B2C problem, not just showing model tricks. We want a credible path to adoption.  
**What good looks like:**

* Clear target user and pain (jobs-to-be-done, measurable outcome).

* Real system integration (APIs, data, workflow), not toy data only.

* Sensible “next steps to production” (what’s left, what risks remain).

* Short, convincing live demo focused on outcomes, not slides.

### **2\) Production Readiness: Reliability & Maintainability — 20 pts**

**What this means:** Your agent/app can be owned, extended, and kept stable by a team.  
**What good looks like:**

* Clean boundaries, typed I/O, config/env separation, versioned prompts.

* Deterministic where it must be; LLM-driven where it’s most useful.

* Tests/evals or fixtures that catch regressions; CI-runnable setup.

* Good documentation with at least a README describing the project architecture and usage. 

### **3\) Security & Safety by Design — 20 pts**

**What this means:** Safe from agent-specific attacks and good enterprise hygiene.  
**What good looks like:**

* Threat model covering prompt injection, data exfiltration, tool abuse, privilege escalation, and broken access control—and concrete mitigations.

* Least-privilege credentials, scoped tokens, policy checks before tool calls.

* Output constraints/validation (schemas, allow/deny lists, function guards).

* Red-team/adversarial test examples; safe failure modes and auditability.

### **4\) Observability & Operability — 20 pts**

**What this means:** You can see what’s happening and fix it fast.  
**What good looks like (Manifesto: “Deep & Intuitive Observability”):**

* End-to-end traces of Reason → Action → Eval loops; step timing/latency.

* Captured LLM inputs/outputs (with secrets scrubbed) and tool I/O.

* Metrics for success/error, retries, hallucination/guardrail triggers, SLIs/SLOs.

* Minimal runbook: how to debug, reproduce, and roll back.

### **5\) Knowledge Layer & Verifiable Reasoning — 15 pts**

**What this means:** Agents maintain an explicit, explainable “world view.”  
**What good looks like (Manifesto: “Knowledge layer for explainable, verifiable, provable reasoning”):**

* Memory/knowledge abstraction (e.g., knowledge graph, structured store, durable memory) that agents read/write.

* Context engineering that is **explainable** (why this evidence?) and **verifiable** (can we trace to sources?). RAG, GraphRAG, etc.

* Evidence-linked answers; where applicable, constraints or proofs/checks.

### **6\) Bonus: Multi-Agent & Validation Tooling — up to \+5 pts**

**Encouraged, not required.**

* **Multi-agent excellence (+0–3):** Clear roles, coordination (A2A/ACP/MCP style), isolation, failure containment, or concurrent actors where it helps.

* **Validation tooling (+0–2):** Reliability harnesses, fuzzers/chaos tests, policy scanners, or LLM-as-a-Judge loops that improve outcomes.

### **7\) Redpanda (+10 extra credit points)**

Integrates **Redpanda** as a key component of the solution.  
Demonstrates a clear understanding of **event streaming concepts**, such as:

* Real-time data processing  
* Event-driven architecture  
* Stream analytics

Shows that Redpanda integration **enhances** one or more of the following in a measurable way:

* Functionality  
* Performance  
* Scalability

### **8\) Akka (+10 extra credit points)**

The Akka SDK provides the essential capabilities to build a fully agentic system that meets the hackathon requirements. All development can be local to your machine. A key component of the SDK, the Akka Agent, a purpose-built, stateful component designed to encapsulate a single AI task with built-in session memory, declarative model orchestration, and robust error handling.

By using the Akka SDK, you’ll get the following out of the box:

* [Agent](https://akka.io/akka-agents), [orchestration](https://akka.io/akka-orchestration), [memory](https://akka.io/akka-memory), and [streaming](https://akka.io/akka-streaming) data support  
* Creation and management of both APIs and endpoints development  
* Dynamic orchestration (workflows where decisions are made by agents)  
* Immutable audit trail, traceable reasoning, interaction logs  
* Vector DB integration  
* Evaluations implemented as LLM-as-a-judge  
* End-to-End Encryption, customizable guardrails that enforce prompt input/output, PII and data sanitizers  
* Runtime properties, including clustering, local development, and management without cloud dependencies

[Docs](https://doc.akka.io/?_gl=1*1ngo3v7*_gcl_au*MTMzNDAyMDAyMS4xNzU4ODU5MTQ3)  
[AI Samples](https://doc.akka.io/getting-started/samples.html?_gl=1*1ngo3v7*_gcl_au*MTMzNDAyMDAyMS4xNzU4ODU5MTQ3)


| Category | What judges look for (quick cues) | Max | Score |
| ----- | ----- | ----- | ----- |
| **1\) Business Value & User Impact** | Clear user & pain; credible B2B/B2C value; real integration; live demo focused on outcome and next steps. | **20** |  |
| **2\) Production Readiness (Reliability & Maintainability)** | Clean boundaries, typed/validated I/O; config/env separation; tests/evals or fixtures; deterministic where needed; CI-runnable. | **20** |  |
| **3\) Security & Safety by Design** | Threat model \+ mitigations for injection/exfiltration/priv-esc/ACL; least privilege; output constraints; adversarial tests; auditability. | **20** |  |
| **4\) Observability & Operability** | Reason→Action→Eval traces; logs/metrics; SLIs/SLOs; scrubbed payload capture; minimal runbook for RCA. | **20** |  |
| **5\) Knowledge Layer & Verifiable Reasoning** | Explicit memory/graph/store; explainable context; evidence-linked answers; verification/consistency checks where applicable. | **15** |  |
| **BONUS) Multi-Agent & Validation Tooling** | Multi-agent done right (roles, A2A/ACP/MCP, isolation, concurrency) **(+0–3)**; Reliability/scan/fuzz/eval tooling **(+0–2)**.  | **\+5** |  |
| **BONUS) Redpanda** | Integrates Redpanda as a component of the solution, demonstrating clear understanding of event streaming concepts (e.g., real-time data processing, event-driven architecture, or stream analytics). The use of Redpanda should enhance the functionality, performance, or scalability of the project in a measurable way. | **\+10** |  |
| **BONUS) Akka** | Use the Akka SDK components to create your agentic system, that includes agents, memory and orchestration. Streaming is optional based on your use case, but included as a native component of the SDK, as well. | **\+10** |  |
|  | **TOTAL** | **120** |  |



### **Additional Judging Rules & Criteria**
### **Disqualifiers / Zeroing conditions**

* No working demo (video or live) or can’t run from README.

* Obvious IP/policy violations or unsafe handling of sensitive data (e.g., hard-coded secrets).

* Misrepresentation of results.

### **Tie-breakers (in order)**

1. Strongest threat model with **enforced** mitigations.

2. Best end-to-end trace which explains what the agent did.

3. Cleanest path to “day-2” ops (runbook \+ performance goals/Service Level Objectives (SLOs)).

### **Demo format that keeps judging crisp**

* **3 minutes live or recorded**: outcome first, then architecture.

* Show **one observability trace** and **one safety control** actually firing.

* Trigger **one failure path** and show graceful handling.

* End with **what’s left for prod** (top 2 risks \+ mitigation plan).

### **Common pitfalls (so judges can be consistent)**

* Slide-only demos (no running system) → low scores across the board.

* “We log stuff” without a **trace linking steps** → weak Observability.

* “We use RAG” with no **explainable evidence or memory abstraction** → weak Knowledge Layer.

* “We sanitized prompts” but no **threat model or enforced policy** → weak Security.

* “Cool model accuracy” but **no user value** or integration → weak Business Impact.

### **The Reliable Agentic AI Manifesto**

[https://github.com/reasonable/reliable-ai/blob/main/reliable-ai-manifesto.md](https://github.com/reasonable/reliable-ai/blob/main/reliable-ai-manifesto.md)
