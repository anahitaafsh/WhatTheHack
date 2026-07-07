# Challenge 06 - Agent Harness Fundamentals: From Agent to Production Agent

[< Previous Challenge](./Challenge-05.md) - **[Home](../README.md)** - [Next Challenge >](./Challenge-07.md)

## Pre-requisites

- Complete [Challenge 02](./Challenge-02.md), [Challenge 03](./Challenge-03.md), [Challenge 04](./Challenge-04.md), and [Challenge 05](./Challenge-05.md).
- Have Python and Jupyter available in your development environment.
- Ensure you have the Resource.zip package provided by your coach, including the Challenge 06 notebook.

## Introduction

In earlier challenges, you built agents, connected tools, deployed hosted runtimes, and added observability. In this challenge, you make an important conceptual leap:

**Agent = Model + Harness**

A model can generate text. An agent can take actions. An agent harness provides the runtime capabilities that make those actions reliable and safe in production.

You will build a fictional **AI Workshop Assistant** that helps a Microsoft PSA prepare customer workshops. As you progress, you will implement the harness capabilities that production agents require:

- Agent loop
- Tool execution
- Memory
- Context management
- Planning
- Sub-agents
- Human-in-the-loop controls
- Observability

## Description

Use the Challenge 06 notebook from the Resource.zip package: **CH-06-AgentHarness.ipynb**.

In this notebook lab, you will implement and test each harness capability in sequence, starting from a model-only baseline and ending with a production-style capstone harness.

You will complete code blanks and short reflection prompts in each section:

- Section 0: Introduction and architecture diagram
- Section 1: A model is not an agent
- Section 2: Build your first agent loop
- Section 3: Tools
- Section 4: Memory
- Section 5: Context management
- Section 6: Planning
- Section 7: Sub-agents
- Section 8: Human in the loop
- Section 9: Observability
- Section 10: Capstone implementation
- Final reflection table and written explanation
- Bonus challenge: reusable `AgentHarness` Python class

For the capstone, your harness must generate a one-day Azure AI Foundry workshop output for Fabrikam, including:

- Research summary
- Workshop agenda
- Recommended demos
- Architecture recommendations
- Follow-up actions
- Execution summary

## Success Criteria

To complete this challenge successfully, you should be able to:

- Demonstrate the difference between a model-only invocation and a harness-based agent workflow.
- Verify your implementation includes an explicit agent loop rather than a single completion call.
- Verify your harness can execute at least one tool and incorporate tool output into a final response.
- Show that memory can persist and be retrieved across separate runs.
- Demonstrate context compaction/summarization when simulated context exceeds a token limit.
- Show a generated plan before execution for a workshop preparation request.
- Demonstrate task delegation using specialized sub-agents.
- Verify a human-approval gate is required before a high-impact action (for example, sending email).
- Show observability outputs for tool usage, token counts, latency, and run duration.
- Demonstrate a complete capstone response that includes all required deliverables.
- Explain, in your own words, why production-grade agents require a harness.

## Learning Resources

- [Azure AI Foundry documentation](https://learn.microsoft.com/azure/ai-foundry/)
- [Azure AI Agent Service overview](https://learn.microsoft.com/azure/ai-foundry/agents/overview)
- [Prompt flow in Azure AI Foundry](https://learn.microsoft.com/azure/ai-foundry/how-to/prompt-flow)
- [Model Context Protocol (MCP) overview](https://modelcontextprotocol.io/introduction)
- [OpenTelemetry concepts](https://opentelemetry.io/docs/concepts/)

## Tips

- Keep each harness capability simple and testable before combining them in the capstone.
- If something fails in the capstone, test each component independently: tool call, memory load/save, planner, and approval gate.
- Treat observability as part of your implementation, not an optional add-on.
- In your reflections, focus on operational implications: reliability, safety, and maintainability.

## Advanced Challenges (Optional)

Too comfortable? Eager to do more? Try these additional challenges!

- Extend your harness with retries and fallback behavior when a tool fails.
- Add confidence scores or quality checks before allowing final output delivery.
- Add per-step cost estimation to your observability summary.
- Package your `AgentHarness` class into a reusable module and use it for a second scenario.
