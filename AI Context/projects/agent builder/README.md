# Agent builder

Bring a rough request here: “Help me prompt this properly” or “Build me an agent that [task].” This project starts with MAPS prompting, then builds a reusable agent when the task calls for one. A chat can use these files when they are available; it does not automatically remember or inherit another chat.

Confirmed target: Codex in this repository. Other targets need a platform-specific version; a repository skill does not automatically create a custom GPT or deploy an automation.

## Start here

Read [prompting.md](prompting.md) first: Mission, Ask, Parameters, Shape. Use the request and established context to decide whether a prompt, reusable agent, or build/test workflow fits. Read builder-rules.md when building an agent, then ask only for essential missing information. Use agent-template.md to create the agent's instructions and acceptance checks. The callable repository skill is `.claude/skills/agent-builder/SKILL.md`; Codex can follow it when asked to use this project.

## What an agent is

An agent combines a clear job, instructions, tools or accessible information, permission boundaries, and checks for a useful result. Instructions alone can produce a useful drafting or research assistant. Repeated unattended work also needs a runtime, trigger, credentials, logging, and failure handling. Git stores the instructions and code; it does not schedule or run the agent.

Start with one bounded real task. Define the result, give the agent the relevant materials, let it work, review its output, then refine the rules from observed failures. Add automation only when the manual workflow has proved useful.

## First workflow: AI receptionist

Shane selected a consistent build-and-test workflow for the existing Retell/Jobber receptionist. Read [receptionist-workflow.md](receptionist-workflow.md). It preserves the builder, product-readiness reviewer, and tester roles as sequential stages with explicit handoffs. Their original chat instructions have not yet been supplied; the workflow below is a repository-based contract, not a claim to have imported them.

## Research status

The supplied AI Prompting.txt transcript was inspected and its MAPS framework incorporated. Its speaker is unidentified. Nick Saraev's primary materials remain unverified. See research.md. These builder rules are a provisional working design, not a claimed reproduction of his method.

## Using a new chat

Open this repository and say: “Use AI Context/projects/agent builder to build me an agent that [task].” For a chat without repository access, attach the builder rules and relevant agent instructions. Do not assume Git files are available in every product.

Generated human-readable agent specifications belong in `AI Context/projects/agent builder/agents/<agent-name>/`. Reusable repository skills belong in `.claude/skills/<agent-name>/SKILL.md`. Executable software should follow the repository's applicable project layout rules. Building a specification does not establish that its tool integrations work.
