# Retell / Jobber receptionist workflow

Confirmed by Shane on 2026-10-12: run in Codex in this repository. Keep the existing builder, builder product-readiness, and tester concept; make the handoffs consistent. This workflow defines their shared contract. Existing role prompts in other chats remain unavailable until supplied.

## Invoke it

“Use the receptionist workflow to build and verify [specific feature or broken behavior].”

If the feature is unspecified, inspect project state and recommend one bounded next task. Ask about consequential product choices only when they cannot be inferred. Do not treat this reusable workflow as permission to start the entire onboarding roadmap or activate live integrations.

Run the roles sequentially in one Codex chat by default. Separate role reviews do not imply independent reviewers. If Shane requests separate chats, each must read the same saved task packet and revision. Use one writer per file set; do not spawn parallel agents or competing builds merely to assign roles.

## Shared task packet

Before implementation, create `AI Context/projects/agent builder/agents/receptionist/tasks/<task-name>.md` from task-packet-template.md. Record:

- The user-visible problem, concrete expected behavior, and exclusions.
- Checkout branch and commit, relevant Retell agent/config version when available, target backend and test account/business identity, and evidence dates. Inspect live state before claiming historical connections still work.
- Scope of authorized operations, required access by name, synthetic fixtures, and approved recipients if sends are authorized. Past bounded test windows and write permissions are not automatically reusable.
- Acceptance cases with expected results; identify which require offline tests, mocked LLM/tool tests, real backend reads, synthetic provider writes, voice/audio inspection, notification delivery, or deployment/recovery.
- Current stage, findings, commands/results, evidence locations, blockers, and the next action.

Keep secrets and private call/customer payloads out of this packet. Use sanitized evidence references. Update the packet at every handoff so another chat can resume from Git rather than reconstructing the conversation.

## 1. Builder

Read root AGENTS.md and CLAUDE.md, and the Jobber project's README.md, current-state.md, implementation-plan.md, operating-rules.md, and applicable roadmap sections. Inspect the code, existing tests and Git state before changing files. Reuse the current integration and preserve test-account and booking guards.

Implement the bounded feature or fix. Add or update meaningful regression coverage for changed behavior. Run affected checks, diagnose failures, and record the diff and verification. Do not silently expand into unrelated CRMs or replace the frontend.

Handoff: exact revision/configuration, files changed, intended behavior, checks run, known gaps, and a reproducible test plan. A successful build is not product acceptance.

## 2. Product-readiness reviewer

Compare the implementation and evidence against the task packet. Review caller wording, business rules, missing fields, timezone/duration handling, tenant isolation, provider identity, failure states, duplicate-write handling, and recovery as relevant to this change. Check whether an unscheduled request, queued notification, or available slot is being misrepresented as a confirmed booking or delivery.

Return concrete findings with severity, affected behavior, evidence, and required correction. Distinguish required task acceptance from wider production gates. Send implementation defects back to Builder; rerun affected checks after repairs. Record a task-level decision: ready for testing, needs repair, or blocked by a named prerequisite.

The repository's readiness inspector is private state/configuration inspection, not live provider verification. It deliberately reports production_ready=false and includes mapping, offsite recovery, pilot approval and full live acceptance gates. Never remove these gates merely to obtain a passing readiness result.

## 3. Tester

Run the agreed tests against the exact handed-off revision/configuration. Verify expected outcomes directly, including appropriate failure and replay cases; retain useful failures. Report passed, failed, skipped and unrun separately. If code/config changes after testing, identify and rerun affected cases.

Offline baseline: from `/workspace/hiscock-automations/jobber-integration`, run `PYTHONDONTWRITEBYTECODE=1 /workspace/.onboarding/hiscock-venv/bin/python -m unittest discover -s tests -q`. Use the saved environment installation instructions if the interpreter is unavailable. On 2026-10-12 the existing baseline ran 229 tests: 228 passed and one Windows vault test skipped. That historical result is not evidence for a later change.

Where live checks are authorized and access exists, prepare the exact fixture and expected result first. For booking, verify the actual Jobber account/customer/property/job/visit, intended time and timezone, independent readback, and replay without another booking. Verify real voice-to-tool behavior separately from text mocks; audio quality needs listening evidence. Treat queued, submitted, delivered and uncertain notifications as separate outcomes. Follow existing reconciliation rather than blindly retrying ambiguous writes.

Check available bindings and required read-only access before requesting new credentials. Missing live access blocks only the relevant gate; continue useful offline work. Do not call, send, spend, deploy, arm writes, publish a Retell agent, or change phone routing outside explicit authorized scope.

Handoff: scenario results, actual test counts and exit status, revision, sanitized evidence, unresolved defects, and precise missing access/authorization.

## Finish or loop

Tester failures return to Builder, then the reviewer checks the correction and the tester reruns affected cases. Stop when the task criteria pass or all useful independent work is exhausted behind a concrete prerequisite. Do not run unchanged failing checks repeatedly.

Report separate statuses: implemented; offline verified; mocked conversation verified; live backend verified; real voice verified; notification delivery verified; deployment verified; production activation approved. Use verified / failed / blocked / unrun / not applicable. A partial status does not become “ready for production.”

Review the diff and preserve unrelated work. Update the task packet and applicable project state/session log with evidence. Commit only reviewed task files, push to the selected private working branch, and verify the remote SHA under the project's sync rules. Check deployment automation before pushing runtime changes. A Git push does not authorize deployment.

## Current workflow status

This contract is saved. No receptionist source code, Retell settings, Jobber records, deployment, or routing changed while defining it. Original role prompts and the intended agent-builder transcript are still needed for source-specific reconciliation. Nick Saraev attribution remains unverified.
