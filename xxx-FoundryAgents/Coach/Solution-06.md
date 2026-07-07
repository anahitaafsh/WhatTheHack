# Challenge 06 - Agent Harness Fundamentals: From Agent to Production Agent - Coach's Guide 

[< Previous Solution](./Solution-05.md) - **[Home](./README.md)** - [Next Solution >](./Solution-07.md)

## Notes & Guidance

Challenge 06 is the conceptual bridge from "I can build an agent" to "I can run and govern an agent in production." Students already used agents in Challenges 01-05; now they explicitly implement the harness layer that enables production behavior.

The key message to repeat throughout coaching is:

**Agent = Model + Harness**

The model generates language. The harness manages runtime concerns: looping, tools, memory, context limits, planning, delegation, human approvals, and observability.

### What Students Are Learning

- Why a single LLM call is insufficient for production workflows
- How to structure an agent loop that can reason, act, and continue
- How tool use, memory, and context controls are harness responsibilities
- How to decompose complex work through planning and sub-agents
- Why human approval gates are required for sensitive enterprise actions
- How observability makes agent behavior diagnosable and governable

### How This Connects to Earlier Challenges

- **Challenge 01 (Portal Agent):** Students wrote persona and behavior instructions. In CH06 they learn those instructions still need runtime control to become reliable operations.
- **Challenge 02 (Code Agent):** Students used SDK calls and threads. In CH06 they wrap these interactions in an explicit loop and workflow logic.
- **Challenge 03 (Tools):** Students saw tool calling. In CH06 they implement deterministic tool registration/execution as a harness capability.
- **Challenge 04 (Hosted Agent):** Students deployed hosted agents. In CH06 they identify what the runtime must do inside that hosted environment.
- **Challenge 05 (Observability):** Students consumed observability signals. In CH06 they instrument harness-level signals as part of the design.

### Coach Review Checklist

- Student can clearly explain the difference between model-only and harness-based behavior
- Student implemented an agent loop (not just one-shot completion)
- Student registered and invoked at least one tool in the workflow
- Student implemented persistent memory methods and demonstrated retrieval in a new run
- Student implemented context compaction when conversation size exceeds a limit
- Student generated a plan before executing a complex task
- Student orchestrated specialized sub-agents for at least three responsibilities
- Student added human approval logic before a high-impact action
- Student captured observability metrics (tool calls, token estimate, latency, duration, cost estimate)
- Student completed capstone output with all required sections and execution summary

### Common Blockers

- **Students confuse LLM capabilities with harness capabilities:** Keep redirecting to ownership boundaries.
- **No loop control:** Students may produce one-shot code that cannot recover after tool calls.
- **Memory implementation too local:** Students overwrite memory in-process and cannot explain persistence semantics.
- **Context management skipped:** Students treat long context as infinite and miss truncation/summarization risks.
- **Sub-agent orchestration unclear:** Students create helper functions but do not separate responsibilities.
- **Approval path not tested:** Require demonstration of both approved and denied branches.
- **Observability only logs final output:** Remind them to instrument intermediate steps, not just end state.

### Coaching Tips

- Use the architecture statement often: user -> harness -> LLM, where harness components mediate execution.
- Ask students to label each code block: "model behavior" or "harness behavior." If they cannot label it, they may not understand ownership.
- In capstone demos, ask "what would fail in production if we removed this harness component?" for each capability.
- Push students to treat reflections as engineering reasoning, not generic opinions.

### Coach Reference Notebook (CH06)

Use this completed notebook as the answer key and walkthrough reference:

- `Coach/Solutions/CH-06-AgentHarness-Solution.ipynb`

Paired student notebook:

- `Student/Resources/CH-06-AgentHarness.ipynb`

The two notebooks are intentionally aligned section-by-section so you can quickly compare student work to expected outcomes.
