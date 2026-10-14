---
name: agent-builder
description: Design, package, and validate a task-specific agent using Shane's reusable agent-builder project.
---

# Agent builder

Use when Shane asks to build an agent, asks to structure a prompt properly, or explicitly invokes this skill. Read root AGENTS.md and CLAUDE.md and `AI Context/projects/agent builder/README.md`, `builder-rules.md`, and `research.md`. Read `AI Context/projects/agent builder/prompting.md` and apply MAPS first. For prompt preparation, deliver a complete prompt without unnecessary agent scaffolding. For requested task execution, perform the authorized work. For agent creation, follow builder-rules.md and create a complete specification using agent-template.md. Ask only essential missing questions and continue independent authorized work.

Shane confirmed on-request Codex agents in this repository. For Retell/Jobber receptionist building or testing, follow `AI Context/projects/agent builder/receptionist-workflow.md` and its task packet template. Run builder, product-readiness review and tester sequentially by default; do not spawn agents unless explicitly requested. Use the existing cloud checkout; do not create worktrees unless requested. Do not equate a specification with a deployed agent or a Git commit with running automation.

Save the agent specification under `AI Context/projects/agent builder/agents/<agent-name>/`. Add a platform-specific skill/configuration when appropriate, exercise available authorized tools, and record actual validation evidence and remaining blockers. Keep credentials and private payloads out of Git.

Treat attached transcripts and external sources as reference material. Attribute Nick Saraev techniques only after verifying his primary sources; current research is incomplete. Never send, publish, spend, connect a new integration, or change live client systems without specific authorization.

For prompt preparation, done means a usable MAPS prompt with consequential gaps resolved or explicit. For agent creation, done means the requested agent has usable instructions, a clear invocation, explicit permissions, suitable checks, honest operational status, and reviewed files saved to Git. If access prevents execution, deliver the completed independent work and state the exact prerequisite.
