# Research and Validation Kit

## Evidence status

**Desk research completed; primary research pending.** Public Pucho product pages and official competitor documentation were reviewed on 27 October 2026. Those sources describe product capabilities and positioning; they do not establish user behaviour or unmet needs. Nisha is a proto-persona. All experience claims about non-technical operators are hypotheses until tested.

## Discovery question

How might a non-technical operations lead turn a repetitive lead-triage job into an automation they can understand, scope, test, and safely run?

## Evidence register

| ID | Evidence | What it supports | What it does not support |
|---|---|---|---|
| E1 | Pucho public product overview and documentation describe agents, workflows, tools, knowledge, integrations, run visibility, and human-in-the-loop controls. | Frame the concept around intent, plan, access, action, and run review. | Whether users understand these concepts, need this order, or trust it. |
| E2 | Make describes scenarios as connected modules and distinguishes fixed workflows from AI-assisted and agent scenarios. | Visual workflow is a relevant category convention; users may need help choosing the level of AI autonomy. | That every beginner finds visual builders hard. |
| E3 | Zapier documents AI steps inside workflows and approval patterns for consequential actions. | Approval checkpoints are a plausible interaction pattern. | That a particular approval UI is usable or sufficient. |
| E4 | n8n describes inspectable steps, inputs/outputs, replay, logs, tool limits, and human review. | Traceability and recovery are category patterns worth exploring. | That a novice can interpret technical traces. |

## Hypotheses to validate

- H1: Users can describe the desired business outcome more easily than trigger/action/model configuration.
- H2: A concise plan with named data sources and action verbs is easier to judge than a node canvas at first run.
- H3: Users need permission scope and write effects before granting access, not after a run starts.
- H4: Inline labels help users distinguish AI recommendations, deterministic rules, and actions.
- H5: A low-confidence result should pause for human review rather than silently route or discard a lead.

## Proto-persona: Nisha, operations lead

**Context:** Runs recurring processes for a small services team. Comfortable with spreadsheets, Slack, and CRM records; has not built an automation. Knows what outcome she wants and what “high intent” means to her team, but not how integrations, models, or workflow nodes fit together.

**Goal:** Start each sales day with a useful summary of new leads.

**Current workaround (hypothesis):** Checks the CRM manually, scans lead messages, then posts selected details in a sales channel.

**Tension:** Wants time back while retaining accountability for what the AI reads, decides, and posts.

**Need statement:** “Help me set up the routine in my own words, then show me what the system will read and do before it acts.”

This is a scenario-based proto-persona, not a recruited participant or claim about a real Pucho customer.

## JTBD

**When** new leads arrive during the work week, **I want to** see a concise, prioritized summary in our sales channel, **so I can** follow up promptly without manually checking every record, while staying confident that the system uses approved data and pauses when judgment is uncertain.

- Functional: collect new leads, summarize relevant fields, apply team criteria, and prepare a digest.
- Emotional: feel informed rather than surprised by automation.
- Control: inspect data scope, edit criteria, approve consequential posting, pause, and recover.

## Problem statement and HMW

AI automation builders can ask for technical choices before users understand the outcome, data access, or consequences. An operator needs a useful first workflow without guessing at system architecture or surrendering control of actions that affect teammates.

**How might we** help an operations lead express a routine in plain language, inspect the AI plan and access, and safely test it before it posts anything?

## Interview guide: five open questions

Use a 25-30 minute semi-structured interview. Ask for recent examples; do not pitch the solution before hearing the workflow.

1. Tell me about the last time you checked new leads and decided which needed attention. What happened from start to finish?
2. Which parts repeat, and which parts require your judgment? Can you walk me through a recent example?
3. What tools or information do you look at, and how do you decide what is safe or relevant to share?
4. Have you tried automating a work task? What did you expect, what happened, and what made you trust or stop it?
5. If a system prepared a lead summary, what would you need to see before letting it post? What should make it stop and ask you?

**Neutral probes:** “What happened next?”, “How did you know?”, “Can you show me an example?”, “What would make that feel risky?” Avoid leading users toward AI, approval, or a preferred screen.

## Competitor audit method

Desk review of official public pages only; no account-based hands-on evaluation. Compare interaction models, not feature counts or overall quality.

| Product | Publicly described pattern | Design signal |
|---|---|---|
| Pucho | Agents, workflows, integrations, knowledge, and human-in-the-loop checkpoints are presented together. | Connect the goal to a plan, tools, and a visible control point. |
| Zapier | AI steps can sit inside structured workflows; approval can gate consequential continuation. | Make the write action and approval moment explicit. |
| Make | Scenario modules form a visual workflow; docs distinguish fixed, AI-assisted, and agent scenarios. | Show a plain-language route first; reveal visual logic when useful. |
| n8n | Step inputs/outputs, logs, replay, tool limits, and human review are emphasized. | Offer concise explanations before technical traces. |

**Interpretation:** The opportunity is to make the user predict the next action, understand its scope, and recover without needing a workflow engineer. This is a design hypothesis, not a comparative usability finding.

## Information architecture

- **Build:** describe outcome, review plan, test it.
- **Workflows:** saved drafts, active automations, schedules, versions.
- **Approvals:** items waiting for a human decision.
- **Connections:** connected apps and exact access granted.
- **Knowledge:** business rules and reference material the AI may use.
- **Runs:** status, step inputs/outputs, errors, retries, and history.

## Core user flow

1. Describe a repetitive job and desired destination.
2. Pucho drafts a plan and highlights assumptions that need confirmation.
3. User edits the trigger, qualification criteria, and low-confidence behaviour.
4. User inspects each data source and action permission.
5. User previews a sample, including expected output and what will not happen.
6. User saves a draft and runs a test with sample or selected records.
7. Routine, reversible actions may run automatically only after explicit activation.
8. A consequential write or low-confidence result waits in Approvals.
9. User approves, edits, rejects, pauses, or retries; the run log records the decision.

## Task flow and exception branches

- **Missing connection:** show app, requested scope, reason, and connect action; keep workflow in draft.
- **Broader-than-needed scope:** flag before consent and offer a narrower permission choice.
- **Low confidence or missing context:** pause; show the uncertain field and why it matters; request clarification or human review.
- **Duplicate record:** skip it and explain the match, with an option to inspect.
- **Tool timeout or expired connection:** preserve completed work, name the failed step, offer retry after reconnection, prevent duplicate writes.
- **Wrong output:** edit draft, rerun with a test record, or roll back an eligible action.
- **User rejects a pending post:** mark it rejected; do not silently retry or post later.

## Low-fidelity wireframe checklist

1. **Build:** outcome prompt, examples, trigger summary, one clear next action.
2. **Plan:** ordered steps, AI vs rule labels, assumptions, edit affordance.
3. **Access review:** data read, action written, reason for each permission, approval requirement.
4. **Run:** status, what happened, what is waiting, failure explanation, next safe action.

## Prototype notes

The included clickthrough uses synthetic data and demonstrates Build -> Plan -> Access -> Preview -> Run/Approval. It does not call a live integration. Intended interactions: edit qualification criteria, inspect read/write scope, preview an example, enter a run state, inspect an approval, and choose approve/reject. It shows evidence, criteria, confidence, and next action instead of hidden model chain-of-thought.

## Moderated usability study

**Status: not run.** Recruit five operations or sales-ops practitioners who use CRM and team chat, have little or no automation-builder experience, and are not involved in this concept. Plan 30-minute sessions; obtain consent for note-taking; do not record without separate consent. Use fictional lead data.

### Task 1 - Build from an outcome

“Your team checks new leads every morning. You want a short summary in the sales channel, and anything uncertain should wait for you. Set up a first version.”

Observe whether the participant starts in outcome language, notices trigger/schedule, identifies a missing decision, and reaches a reviewable plan without facilitator instruction.

### Task 2 - Inspect plan and access

“Before you let this run, tell me what information it will read, what it will write, and what still needs your approval. Change anything you would not allow.”

Observe correct recall of source fields, destination, AI-vs-rule decision, permission scope, and approval state. Watch for the assumption that preview has already posted data.

### Task 3 - Handle uncertainty or failure

“A new lead is missing a company and qualification confidence is low. The Slack connection also needs attention. What would you do next?”

Observe whether the participant finds the pause, understands why it stopped, avoids an unsafe post, reconnects or edits, and can retry without a duplicate.

### Moderator prompts

- “What do you think will happen if you choose that?”
- “What information do you expect this step to use?”
- “What would you do if the result is wrong?”
- “How certain are you, and what on screen led you there?”

Do not teach the interface during a task. If a participant gets stuck, note time and recovery; offer the same neutral prompt to everyone.

## Measures and proposed thresholds

These are proposed decision thresholds, not results or product commitments.

- **Task completion:** completes each task without moderator intervention; target 4/5 participants per task.
- **Plan comprehension:** correctly explains trigger, data source, AI judgment, destination, and approval; target 4/5 on all five items.
- **Permission comprehension:** identifies every read/write permission and its reason; target 5/5 before consent.
- **Unsafe assumption:** believes the system posted or can post without explicit approval; target zero participants.
- **Recovery:** finds a safe next step after uncertainty or connection failure; target 4/5.
- **Efficiency:** record time from landing to first understandable plan and hesitation points; do not use time alone as success.
- **Confidence:** 1-5 post-task rating plus “what led you to that rating?” Do not equate stated trust with safe understanding.

## Observation and iteration log template

| Participant / task | Observable action or quote | Expected behaviour | Confusion / risk | Severity (1-3) | Design change | Retest? |
|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |

Separate direct observation from interpretation. Record failures and near-misses, not only successful completions. After round one, fix unsafe assumptions first, comprehension blockers second, efficiency issues third. Retest changed trust-critical moments with new participants.

## Proposed post-launch measures

- Time to first testable workflow, segmented by prior automation experience.
- Plan comprehension and permission-scope recall before activation.
- Approval acceptance, rejection, edit, and timeout rates by action risk and confidence band.
- Run success, duplicate-write prevention, pause/resume, and recovery completion.
- Disablement and rollback rates, investigated qualitatively rather than interpreted as failure alone.

Do not optimise for approval rate or autonomous runs alone. A lower approval rate may mean the guardrail is working.

## References (official public sources reviewed 27 October 2026)

- Pucho, Product overview: https://www.pucho.ai/product-overview
- Pucho, AI Agents: https://www.pucho.ai/ai-agents
- Pucho, AI Workflows: https://www.pucho.ai/ai-workflows
- Pucho, product documentation: https://www.pucho.ai/documentation/product-overview/pucho-platform
- Zapier Help, Add approval steps: https://help.zapier.com/hc/en-us/articles/41776074420493-Add-approval-steps-to-your-agent-s-instructions
- Make Help, Scenario types: https://help.make.com/whats-a-scenario-and-which-type-should-you-use
- n8n, AI agents: https://n8n.io/ai-agents/
- n8n, Workflow features: https://n8n.io/features/

Public product pages can change. Re-check claims before presenting this work later.
