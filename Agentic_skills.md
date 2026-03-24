# Agentic Skills to Master (March 2026)

A prioritized map of skills for building, orchestrating, and leveraging agentic AI systems.

---

## 1. Prompt Engineering for Agents

Not just chat prompts — agentic prompts define behavior, constraints, and decision boundaries.

- System prompt design: personas, tool grants, scope limits
- Chain-of-thought and reasoning elicitation (e.g. `<think>` blocks, scratchpads)
- Few-shot examples for tool use and structured output
- Avoiding prompt injection from untrusted tool outputs
- Output format enforcement (JSON mode, structured schemas)

---

## 2. Tool / Function Calling

The core primitive of agentic systems. Master how models invoke external capabilities.

- Designing clean, minimal tool schemas (OpenAI function calling, Anthropic tool use)
- Idempotency and error handling for tool calls
- Tool result injection and multi-turn tool loops
- Knowing when NOT to give a model a tool (blast radius awareness)
- MCP (Model Context Protocol) — emerging standard for tool/resource/prompt exposure

---

## 3. Orchestration Patterns

How agents hand off work, spawn subagents, and manage complex task flows.

- ReAct loop (Reason + Act cycles)
- Plan-and-execute vs. reactive agents
- Multi-agent patterns: supervisor/worker, peer-to-peer, critic/generator
- Parallel fan-out with result aggregation
- Human-in-the-loop checkpoints and approval gates
- Frameworks: LangGraph, AutoGen, CrewAI, Pydantic AI, smolagents

---

## 4. Context Window Management

Agents live and die by what fits in context.

- Token budgeting across long tasks
- Summarization and memory compression strategies
- Retrieval-Augmented Generation (RAG) for grounding
- Context pruning: what to keep, evict, or externalize
- Structured vs. unstructured memory (episodic, semantic, working)

---

## 5. Memory Architecture

Giving agents useful recall beyond a single session.

- In-context memory (scratchpad, running summary)
- External memory stores: vector DBs (Chroma, pgvector, Qdrant), key-value, SQL
- Memory write/read discipline — when agents should persist vs. discard
- Avoiding stale or hallucinated memory retrieval

---

## 6. Structured Output & Data Pipelines

Reliably extracting typed data from model outputs.

- JSON schema validation (Pydantic, Zod, instructor library)
- Retry/correction loops when output fails validation
- Extraction pipelines: document → structured record → downstream action
- Integrating agent outputs into databases, APIs, and workflows

---

## 7. Evaluation & Observability

You can't improve what you can't measure.

- LLM-as-judge evaluation patterns
- Trace logging for agent steps (LangSmith, Arize Phoenix, Langfuse)
- Defining task-level success metrics, not just turn-level quality
- Regression testing agentic workflows
- Prompt versioning and experiment tracking

---

## 8. Security & Prompt Injection Defense

Agentic systems are high-value attack surfaces.

- Prompt injection via tool outputs, web content, or user data
- Sandboxing code execution (E2B, Modal, Docker)
- Least-privilege tool grants
- Input/output content filtering at system boundaries
- Treating all external data as untrusted

---

## 9. Model Selection & Routing

Not every task needs the biggest model.

- Matching model capability to task complexity (cost vs. quality tradeoff)
- Routing: fast/cheap models for classification, strong models for reasoning
- Fine-tuning vs. prompting tradeoffs for specialized tasks
- Local models (Ollama, llama.cpp) for latency-sensitive or private tasks
- Multimodal inputs: when vision, audio, or document parsing is needed

---

## 10. Agentic Coding Workflows

Using agents to write, review, and run code — the meta-skill.

- IDE agent integration (Copilot Agent Mode, Cursor, Aider)
- Iterative code generation with test feedback loops
- Agents that can run terminals, edit files, and validate their own output
- Defining scope boundaries so agents don't over-engineer
- Review discipline: always read agent-generated code before accepting

---

## Quick Priority Stack

| Priority | Skill |
|----------|-------|
| Must-have | Prompt engineering, Tool calling, Context management |
| High value | Orchestration patterns, Structured output, Eval/observability |
| Differentiating | Memory architecture, Security, Model routing |
| Multiplier | Agentic coding workflows |

---

*Last updated: March 2026*
