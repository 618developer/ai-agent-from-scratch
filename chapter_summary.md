Here's your markdown summary of Chapter 1:

```markdown
# Chapter 1: What is an AI Agent? — Summary

## 1.1 The Age of AI Agents
AI agents span a wide spectrum of applications today. The chapter identifies three categories:
- **Personal AI agents** — Tools like ChatGPT, Claude, and Gemini that evolved from simple chatbots. Modern personal agents can analyze uploaded documents, search the web for current information, generate images, write and execute code, and even help with shopping decisions, serving as general-purpose assistants that adapt to whatever task users bring them.[^1]
- **Customer-facing agents** — These agents operate on behalf of businesses, interacting directly with customers in real time, accessing company policies, retrieving customer data, processing transactions, and making decisions based on business rules.[^2]
- **Specialized agents** — These tackle domain-specific tasks requiring deep expertise, such as coding agents (Claude Code, Cursor, Codex CLI) that can navigate codebases, implement features, fix bugs, and refactor code.[^3]

All these agents share one foundation: they're powered by LLMs.[^4]

## 1.2 Understanding LLM Agents
**What is an LLM?** The core principle of LLMs is simple: learning to predict the next word by processing massive amounts of text data.[^5]

**What is an LLM agent?** The defining feature is **autonomous control flow**: an LLM agent is a program that hands part of its control flow to an LLM, letting the model decide what actions to take and when to stop based on its current context and goals.[^6]

Three structural elements enable this autonomy:
- The LLM serves as the agent's brain—it understands the current situation and decides what to do next.[^7]
- Tools extend the agent's action space into the external world, including web search, code execution, and database access.[^8]
- The loop is the execution structure that lets these decisions happen repeatedly until the goal is achieved.[^9]

The agent loop works by having the LLM evaluate context, decide on tool use, execute, observe results, and repeat until it determines that sufficient information has been gathered to answer the user's question comprehensively, at which point it generates the final report.[^10]

## 1.3 Workflow vs. Agent
- **Workflow**: A system in which developers explicitly design the sequence of operations, with LLMs executing specific steps within that predefined structure. The key characteristic is predictability.[^11] Patterns include single LLM calls, chains, and routers.
- **Agent**: A system in which the LLM dynamically directs its own processes and tool use, maintaining control of how it accomplishes tasks, rather than following a predetermined path.[^12]

In practice, the most effective architectures often combine both approaches, using workflows to provide structure and predictability, and embedding agents at specific points where flexibility is needed.[^13]

## 1.4 Tasks That Require Agents
Two gating questions: Does this task require an LLM? If an LLM is needed, does it require an agent, or will a workflow suffice?[^14]

Three criteria for choosing agents:
1. Task complexity—If it's difficult to predict how many steps a task will require, agents have the advantage.[^15]
2. Task value—Because agents require multiple calls and dynamic decision-making, they cost more and respond more slowly, so the value of completing the task should outweigh the additional cost and latency.[^16]
3. Error cost and detectability—LLMs are prone to make incorrect decisions, and if errors lead to critical consequences, an agent may not be the best choice.[^17]

**GAIA benchmark**: A dataset that systematically collects tasks requiring agents, consisting of question-and-answer pairs where each question requires multistep reasoning, web searches, calculations, and more.[^18] This book uses GAIA throughout to measure progress.

## 1.5 Context Engineering
**Context** is broader than a prompt: it encompasses all the information an LLM references when generating a response, including the system prompt, user messages, conversation history, tool execution results, and retrieved documents.[^19]

**Why agents fail**: Either insufficient model intelligence, or lack of necessary information—even if a model is intelligent enough, it can't produce correct answers if the information needed to complete the task isn't in the context.[^20][^21] Notably, a significant portion of real-world agent failures stems from information deficiency.[^22]

**Bigger context isn't always better**: Recent research has reported that model performance degrades as context length increases, a phenomenon sometimes called context rot.[^23] This relates to the "lost in the middle" effect, in which models tend to miss important information located in the middle of long contexts.[^24]

**Five context-engineering strategies**:
1. **Generate** – Using LLM-generated outputs within the context, which includes generating plans for complex tasks or reflecting on completed work to revise strategies.[^25]
