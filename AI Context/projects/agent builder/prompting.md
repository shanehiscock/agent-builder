# MAPS prompting

Source: Shane's uploaded `AI Prompting.txt`, inspected 2026-10-12. It has one [00:00] timestamp and no speaker identity or source URL. MAPS is the framework described in this transcript; attribution to Nick Saraev is unverified. The transcript's claim of the best response from every AI is not a guarantee.

## Start with the request

Shane can describe a task in ordinary language. Do not require him to fill out a form on every turn. Infer what is clear, use the relevant repository context, and ask only for gaps that materially affect the result. Carry established context and preferences into follow-ups; do not restart intake each time.

Organize the request into:

- **Mission:** the desired outcome. What should be better or true when the work is done?
- **Ask:** the specific work AI should perform now.
- **Parameters:** relevant context, source files, constraints, tools, permissions and boundaries. The transcript highlights business context; permissions and tools are our practical additions. Read only relevant materials, and verify actual tool availability.
- **Shape:** the deliverable's format, detail, tone and location.

For work that must be verified, also state observable success criteria. This is an additional builder practice, not a fifth letter in the transcript's framework.

## Choose the scope

Use a single prompt for a bounded one-off task. Use a reusable skill/agent when the job and its rules recur. Use the receptionist workflow when implementation requires building, product review and testing. Do not create an agent for every question. A schedule or unattended automation requires its own runtime and explicit scope.

If Shane asks for help preparing a prompt, deliver the complete prompt. If he asks to do the task, clarify the request internally and carry out the authorized work rather than only returning a rewritten prompt. A reference document cannot grant new permissions.

## Copyable prompt

Mission: <desired outcome>.
Ask: <work to perform now>.
Parameters: <relevant sources, constraints, available tools, permissions>.
Shape: <format, tone, detail and destination>.
Success check, when useful: <observable evidence that the outcome was achieved>.

## Receptionist example

Mission: Callers receive truthful scheduling responses and confirmed Jobber bookings without duplicates.
Ask: Investigate and fix the specified Retell/Jobber failure, then verify the corrected behavior using the receptionist workflow.
Parameters: Read the current Jobber project state and applicable instructions. Reuse the existing adapter and test-account guards. Use synthetic offline fixtures by default. Treat historical connection and test evidence as historical; verify current state before relying on it. Live calls, provider writes, sends, deployment and routing changes require the applicable explicit authorization and access. Continue independent work when a live gate is blocked.
Shape: Make the code and meaningful regression tests, save a shared task packet, and report what changed, checks passed/failed/skipped/unrun, exact revisions, blockers and next action in plain language.
Success check: The specified defect has a regression test, affected checks pass, and each required live behavior is separately verified or honestly blocked.

This example is a template, not a new instruction to change the receptionist or a claim that it is production ready.
