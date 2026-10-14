# Conversation handoff — 2026-10-14

## Purpose and decisions

Shane wants one reusable builder for preparing good prompts and creating task-specific agents. MAPS from the supplied AI Prompting.txt transcript means Mission, Ask, Parameters, Shape. Nick Saraev research remains incomplete; do not attribute MAPS or other methods to him without primary evidence. The earlier Agent Builder.txt was an unrelated self-sabotage excerpt.

Confirmed agent platform: Codex with Git-backed context. Use a one-off prompt where sufficient; recurring jobs can become skills. The Retell/Jobber workflow uses sequential Builder → Product-readiness reviewer → Tester → repair/retest, with shared revisioned task packets. Original role prompts from other chats were not supplied. Offline, mock conversation, real backend, voice, delivery and production results must remain distinct.

The reusable files were saved on the agent-builder branch of shanehiscock/hiscock-automations before this standalone extraction. They were not merged into main during this chat. Do not assume subsequent remote changes are covered by this snapshot.

## Other requested specialists

- Retell adjustments: inventory actual agents/versions/tools/routing, inspect current documentation, preserve prior settings and rollback, verify readback and behavior separately. Backend changes go to the builder. No specialist deployment or integration was performed here.
- Website editor: source is website-building/ in the business repository. Read its project instructions, preserve design, verify syntax/build/affected interactions and mobile behavior. Git sync does not prove the laptop has no unpushed work. Publishing requires authorization.
- Sales assistant: prioritize setter-booked sales appointments, Calendar/Meet setup, prospect context, meeting preparation and follow-up. Notion holds business notes, Google Calendar commitments, Sunsama daily tasks under existing business rules. Tool access must be verified. Mo's booking handoff remained unconfirmed; recommend a booking link with automatic Meet and test the full invitation flow.

## Mo follow-ups and proposals

Call notes were pasted because Notion access was blocked. Follow-ups: package/pricing design, a subcontractor agreement, 300 leads (corrected from “beats”), and a start-to-finish receptionist demo video. “Tonight” was an October 12 note, not a current deadline or sending authorization. Completion of these follow-ups has not been verified.

Package ideas: basic scheduling-only with first month free; higher tier ideas include texting, lead follow-up/re-engagement and review requests. Discussed numbers: 650 standard and 250 first month. Currency, billing period, final inclusions and three-month advance terms remain unconfirmed. Treat these as proposals; verify current offer and technical readiness before quoting.

Mo cold calls and books sales appointments. Shane stated pay of 70 for prospects showing up on his calendar; currency, qualification, payment schedule, no-show/reschedule/duplicate rules, legal identities and jurisdiction remain unresolved. A contract drafting prompt was provided, not a signed agreement.

Video goal: show the test Jobber account before the call, Shane speaking to the receptionist with both sides audible, then the resulting job/visit in Jobber with matching details and time. Use synthetic data, hide private information, verify real booking/readback and obtain scoped authorization for live writes. No video was recorded here.

## Next action

Create the private GitHub repository agent-builder, push this prepared project, select it for a cloud environment, and publish through the product. Confirm laptop access after cloning/opening. Continue prompt/agent work from these files; attach the business repository when its source or policies are needed.
