# Challenge 05 - Implement End-to-End Observability for Foundry Agents - Coach's Guide 

[< Previous Solution](./Solution-04.md) - **[Home](./README.md)**

## Notes & Guidance

This challenge is where students shift from "I built an agent" to "I can operate an agent in production." They should apply observability to an **existing** agent created in earlier challenges (for example TravelAgent from Challenge 01, NewsAgent from Challenge 02/03, or the hosted weather agent from Challenge 04), rather than creating a new Challenge 05-only agent.

The key idea to reinforce from the CH05 coach notebook is: **observability is an end-to-end loop, not a single dashboard.** Students should produce run evidence (`agent_id`, `thread_id`, `run_id`), generate traces, inspect monitoring signals, and then evaluate quality (continuous + batch) so they can make concrete improvement decisions.

### What Students Are Learning

- How to run a real SDK interaction on an existing agent and capture evidence for traceability (`thread_id` and `run_id`)
- How tracing, monitoring, and evaluation complement each other
- How to move from one-off testing to repeatable operational feedback loops
- How to derive actionable improvement steps from telemetry and evaluator outputs

### How This Connects to Earlier Challenges

- **Challenge 01 (Portal Agent):** Students learned persona/instruction design. In CH05, they observe whether those instructions produce reliable behavior under repeated traffic.
- **Challenge 02 (Code Agent):** Students learned SDK-based runs and threads. In CH05, those same SDK runs become traceable operational evidence.
- **Challenge 03 (Tools):** Students added tool use and more complex behavior. In CH05, they validate tool-driven latency, success/failure patterns, and quality impact.
- **Challenge 04 (Hosted Agent):** Students deployed containerized agents. In CH05, they monitor hosted-agent performance and evaluate quality at runtime.

### Key Coaching Checks

- Student is using an existing agent ID (not a throwaway CH05-only agent)
- Student can show at least one real run with captured `thread_id` and `run_id`
- Student can explain where traces are visible and how they relate to a specific run
- Student can identify monitoring signals (latency, success, usage) and what each signal means operationally
- Student can show both:
  - Continuous evaluation configured and producing results on generated traffic
  - Batch evaluation output over a dataset
- Student can state at least one concrete next improvement based on evidence (quality, reliability, or cost)

### Common Blockers

- **Missing `.env` values:** `AZURE_AI_FOUNDRY_ENDPOINT`, `AZURE_OPENAI_DEPLOYMENT_NAME`, or `CH05_AGENT_ID` not set
- **No existing agent ID:** Students may have deleted prior agents; they need to recreate one from earlier challenges or reuse an existing deployed agent
- **Auth confusion:** Azure CLI auth not active in the current shell/session
- **Telemetry delay expectations:** Students expect traces instantly; remind them ingestion can take a few minutes
- **Hard to connect metrics to behavior:** Ask students to pick one run and walk through it from run evidence -> trace/monitoring -> evaluation result

### Coaching Tips

- Start with one known-good prompt and one intentionally difficult prompt. This helps students compare observability signals across outcomes.
- If students get lost in tooling, bring them back to the sequence:
  1. Run the agent
  2. Capture run evidence
  3. Inspect traces/monitoring
  4. Evaluate quality
  5. Propose improvement
- Encourage synthetic/non-sensitive prompts and data in all traces and evaluations.
- Push for interpretation, not screenshots: students should explain what changed, why it matters, and what they would do next.

### Coach Reference Notebook (CH05)

Use this completed notebook as your reference answer key for Challenge 05:

- `Coach/Solutions/CH-05-Observability-Solution.ipynb`

Notebook highlights to reference during coaching:

- Real run against existing agent (`CH05_AGENT_ID`) and evidence capture (`agent_id`, `thread_id`, `run_id`)
- OpenTelemetry tracing simulation and span inspection patterns
- Monitoring and evaluation workflow (continuous + batch)
- End-to-end flow that maps directly to student success criteria in Challenge 05

If a squad is blocked, guide them to the matching section in the notebook rather than giving final code immediately, then have them explain the operational meaning of the output they produced.
