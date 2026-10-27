# Research Findings and Early UX Synthesis

**Project:** Pucho.ai — Trust-first automation concept  
**Status:** Early synthesis from the material currently available; not a completed target-user research study.  
**Prepared:** 27 October 2026

## 1. Why this research matters

The concept is aimed at people who want to automate a repeated task but do not want to learn technical workflow terminology before getting started. The research question is whether a person can understand what an automation will do, decide what it may access, check the expected output, and stay in control before an external action happens.

## 2. Evidence reviewed

- The current project interview log contains one proxy response: the participant identified **studying** as a repeated task. The remaining interview questions have not been answered in the available notes.
- The competitor desk audit reviews the public product/help pages for Pucho.ai, Zapier, Make, and n8n. It records advertised product positioning and features, not measured usability or customer satisfaction.
- The current HTML prototype demonstrates a five-step flow: describe a task, review a suggested plan, review permissions, preview the result, and inspect a simulated run.

These sources are useful for shaping the next research round, but they do not yet establish the needs of business operations users. No participant quote has been invented or added here.

## 3. Early themes to validate

### Theme 1 — Start with the task, not technical vocabulary

**Current signal:** The prototype begins with a plain-language prompt and example task suggestions.

**Design hypothesis:** A first-time user may find it easier to explain the result they need than to select triggers, actions, or agents before understanding the workflow.

**What to check with users:** Can they describe a realistic recurring task without coaching? Which words or examples help them get started?

### Theme 2 — Make the plan understandable before access is granted

**Current signal:** The prototype shows the proposed steps and gives a short reason for the plan.

**Design hypothesis:** Users may feel more confident when every step explains its purpose and the data it needs.

**What to check with users:** Can they explain the proposed steps in their own words? Can they identify which information is read and what the system prepares?

### Theme 3 — Permissions and approval should be visible

**Current signal:** The concept provides app-access toggles and a separate approval checkbox for the outgoing Slack digest.

**Design hypothesis:** Clear, task-specific permissions and a visible approval checkpoint may help users spot unwanted access or external actions.

**What to check with users:** Can they tell the difference between reading information, preparing a draft, and sending a message? Do they notice when approval is turned off?

### Theme 4 — Preview and recovery need plain explanations

**Current signal:** The prototype uses fictional preview data and shows a simulated result screen.

**Design hypothesis:** A preview and a clear status summary may help users catch misunderstandings before relying on an automation.

**What to check with users:** Do they understand that preview data is fictional? After a problem is described, can they identify a safe next step?

## 4. Current problem framing

**Working problem statement:** People who are new to automation may struggle to predict what a workflow will do, what information it will access, and whether it will take an external action. The concept explores how a step-by-step review flow could make those decisions easier to understand.

**How might we:** How might we help a first-time user describe a repeated task in everyday language, inspect a proposed workflow, and approve consequential actions with confidence?

**Important limitation:** This is a problem hypothesis, not a conclusion validated by target-user interviews.

## 5. Design implications

1. Use plain language for the first prompt and for each workflow step.
2. Show the data source, intended action, and reason for each permission.
3. Keep preview and approval separate so users can inspect the output before an external action.
4. Flag uncertain matches for human review instead of presenting every AI suggestion as certain.
5. Explain simulated results clearly and avoid implying that real accounts were connected.

## 6. Next research round

Recruit 3–5 people who regularly handle repetitive administrative or operations work. Examples include an office coordinator, operations assistant, small-business owner, or team lead. With their consent, ask them to describe one recent repeated task and walk through the prototype without coaching.

For each session, record:

- Participant code only (P01, P02, and so on; no names or confidential work data)
- Role and task context, at a high level
- The participant's actual steps and pain points
- What they checked before trusting the proposed automation
- Any misunderstanding, hesitation, or recovery need
- Exact quotes only when captured accurately and with consent
- The designer's interpretation, kept separate from what the participant said

## 7. Current conclusion

The prototype has a coherent trust-first direction, but its key assumptions still need validation with target users. The strongest next step is to run short interviews and usability sessions, record the actual evidence, and update the design based on what participants do and say.
