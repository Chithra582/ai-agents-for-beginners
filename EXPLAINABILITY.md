# EXPLAINABILITY — AI Agents Pedagogy Agent

> **Admissibility & Transparency Report for OpenGAP / Agent Passport**  
> *Agent Name:* AI Agents Pedagogy Agent (`ai-agents-pedagogy-agent`)  
> *Specification:* OpenGAP v0.1.0  
> *Domain:* Education / AI Agent Engineering Curriculum & Pedagogical Reference  

---

## 1. Overview & Operational Purpose

The **AI Agents Pedagogy Agent** (`ai-agents-pedagogy-agent`) is an autonomous educational mentor and reference guide built upon the comprehensive **AI Agents for Beginners** curriculum. Spanning 18 structured lesson modules—from foundational agent definitions, agentic design patterns, and tool use, to agentic RAG, metacognition, local agents, and production deployment—the agent provides interactive pedagogical guidance for developers, students, and engineers.

Through guided inquiry, hands-on code walkthroughs, and comparative architectural analyses (AutoGen, Semantic Kernel, CrewAI, LangGraph), the agent facilitates deep, practical mastery of autonomous AI agent engineering.

---

## 2. How the Agent Decides (Decision-Making Logic)

AI Agents Pedagogy Agent operates across a deterministic, multi-stage decision pipeline:

```
[Learner Query / Task] ──> [Skill Assessment & Gap Analysis] ──> [Lesson & Framework Mapping]
                                                                            │
                                                                            ▼
[Socratic Response & Tests] <── [Safety & Pattern Audit] <── [Code Sample Retrieval]
```

### 2.1 Lesson Navigation & Skill Level Scaffolding
- **Decision:** Determines the appropriate lesson module, technical depth, and conceptual explanation based on learner inquiries.
- **Rules:**
  - Evaluates student background and questions to identify prerequisite knowledge gaps.
  - Recommends structured lesson sequences from foundational concepts (`01-intro-to-ai-agents`) to advanced production topics (`16-deploying-scalable-agents`).
  - Provides Socratic guiding questions to test comprehension before advancing to complex multi-agent architectures.

### 2.2 Framework & Architecture Selection
- **Decision:** Recommends appropriate agentic frameworks (Semantic Kernel, AutoGen, CrewAI, LangGraph) based on project constraints.
- **Rules:**
  - Evaluates application requirements (enterprise C#/Python stack vs. research multi-agent conversational teams vs. deterministic state machines).
  - Outlines concrete architectural trade-offs: AutoGen for conversational multi-agent dynamics; Semantic Kernel for enterprise plugin orchestration; LangGraph for cyclical stateful graphs.
  - Supplies side-by-side comparative code implementations for identical tasks across selected frameworks.

### 2.3 RAG Retrieval & Memory Grounding
- **Decision:** Guides selection of chunking strategies, vector databases, and memory tiers for agentic retrieval-augmented generation.
- **Rules:**
  - Analyzes document modalities and query patterns to recommend fixed-size vs. semantic vs. hierarchical chunking.
  - Illustrates hybrid retrieval combining dense vector embeddings with sparse keyword search (BM25).
  - Explains short-term context window management alongside persistent external memory stores.

### 2.4 Safety Auditing & Vulnerability Gatekeeping
- **Decision:** Highlights potential security and safety vulnerabilities in proposed student agent designs.
- **Rules:**
  - Scans proposed agent tools for unsafe shell execution, arbitrary file writes, or unprotected network endpoints.
  - Mandates inclusion of human-in-the-loop approval gates for high-impact actions.
  - References OWASP Top 10 for LLM Applications and MITRE ATLAS matrices during architectural reviews.

---

## 3. Data Sources & Inputs Used

| Data Input | Source | Purpose | Data Handling & Privacy |
| :--- | :--- | :--- | :--- |
| Learner Queries & Prompts | Interactive learning session / IDE interface | Directs pedagogical explanations and code examples | Processed ephemerally, no learner PII retained |
| Course Curriculum & Lessons | Markdown lessons in `00-course-setup` to `18-securing-ai-agents` | Official pedagogical syllabus and learning objectives | Local repository source, public domain educational material |
| Code Samples & Notebooks | Python scripts and Jupyter notebooks across lessons | Practical demonstrations and test cases | Executed locally or in sandboxed devcontainers |
| Framework Documentation | Official AutoGen, Semantic Kernel, and LangGraph APIs | Up-to-date SDK references and best practices | Referenced for technical accuracy and API parity |

AI Agents Pedagogy Agent complies with operational security and privacy standards:
- **No Cloud Data Exfiltration:** All curriculum materials, student prompts, and code exercises are processed locally or within student-approved environments.
- **Epistemic Isolation:** Student query contexts are strictly isolated between sessions with no persistent learner profiling.
- **Sanitized Model Payloads:** Interactive code snippets undergo static analysis and sanitization to prevent harmful code execution.
- **Data Minimization:** Only curriculum excerpts relevant to the student's immediate inquiry are injected into reasoning prompts.

---

## 4. Known Limitations & Failure Modes

Reviewers, auditors, and users should note the following operational constraints:

1. **Rapid Framework API Evolution:**
   - *Limitation:* Fast-moving agent SDKs (AutoGen v0.4, Semantic Kernel 1.x) frequently introduce breaking API changes.
   - *Mitigation:* Focus on underlying design patterns and architectural invariants rather than framework-specific syntactic quirks.

2. **Over-Simplification of Production Constraints:**
   - *Limitation:* Educational examples may omit complex production edge cases (distributed state, token rate limiting, failure recovery).
   - *Mitigation:* Dedicated production lessons (`10-ai-agents-production`, `16-deploying-scalable-agents`) explicitly highlighting real-world failure modes.

3. **Hallucinated Library Methods in Generated Code:**
   - *Limitation:* Underlying LLMs might hallucinate non-existent parameters or methods in newer framework releases.
   - *Mitigation:* Code validation against repository test suites (`tests/`) and pre-verified notebook samples.

4. **Resource Constraints for Local Models:**
   - *Limitation:* Running local agent models (`17-creating-local-ai-agents` via Ollama/vLLM) requires substantial VRAM/RAM.
   - *Mitigation:* Sizing guidance and quantization recommendations (e.g. Q4_K_M GGUF models) for resource-constrained hardware.

---

## 5. Verification, Safety & Human Oversight

- **Real-Time Human Approval Gate:** Instructors and learners maintain full supervisory control with interactive approval steps for code generation and test execution.
- **Emergency Session Interrupt:** Students can instantly halt execution, reset lesson sessions, or terminate running agent loops.
- **Step Quota Guardrails:** Guardrails enforce strict recursion and token limits to prevent runaway loops during multi-agent simulations.
- **Structured Audit Logging:** Every pedagogical query, code generation step, and safety check is logged with clear timestamped traces for review.
