# Pucho.ai — Prototype Validation Report

**Review method:** Static source review of the prototype and README. This is not a claim that browser automation or user testing was performed.

## What the current prototype does

- Shows a five-stage flow: describe, plan, review access, preview, and result.
- Blocks empty or very short requests.
- Provides demo controls for Google Sheets, AI summarisation, and Slack.
- Shows permission warnings when access is disabled.
- Requires confirmation before the demo run.
- Simulates results based on selected settings.
- States that the prototype has no live app integrations or real records.
- Includes responsive CSS for narrower screens.

## Issues identified

### 1. Fixed plan — High priority
The displayed plan does not adapt to the text entered by the user.

**Suggested fix:** Make the sample plan adapt to predefined example scenarios, or clearly label it as a fixed sample. Do not claim it uses live AI unless it actually does.

### 2. Uncertain-match setting — High priority
The uncertain-match checkbox stores a setting, but the preview and result do not visibly use it.

**Suggested fix:** Show how the selected setting changes the preview or result, or remove the control.

### 3. Sidebar links — Medium priority
Some sidebar links use placeholder destinations and do not open working screens.

**Suggested fix:** Add simple demo screens or clearly indicate that these sections are not available in the prototype.

### 4. Missing error recovery — Medium priority
The prototype primarily demonstrates a successful run and does not show a clear simulated failure-and-retry path.

**Suggested fix:** Add a demo-only error state with options to review details, edit the plan, or try again.

### 5. Plan transparency — Low priority
The user may not know whether the proposed steps are generated or fixed examples.

**Suggested fix:** Display the user's request and label fixed steps as a sample plan.

## Manual validation checklist

Record the actual outcome after trying each check. Do not mark a check as passed before testing it.

| Check | Expected result | Status |
|---|---|---|
| Open prototype on desktop | Initial screen displays correctly | Not yet verified |
| Enter a very short request | Clear validation message appears | Verify manually |
| Enter a normal request | Flow advances correctly | Verify manually |
| Disable a required integration | Demo run is blocked clearly | Verify manually |
| Leave a confirmation unchecked | Demo run is blocked | Verify manually |
| Disable Slack | Result reflects the disabled setting | Verify manually |
| Change uncertain-match setting | Preview or result reflects the choice | Source review indicates this needs fixing |
| Change request text | Plan adapts or is clearly labelled as a sample | Source review indicates this needs fixing |
| Click sidebar links | Working destination or clear inactive state | Source review indicates this needs fixing |
| Test a narrow viewport | Content remains readable | Verify manually |

## Recommended next steps

1. Fix or label the fixed plan.
2. Make the uncertain-match control affect the preview or result.
3. Fix or disable placeholder sidebar links.
4. Add a simulated error-recovery flow if it is part of the project requirements.
5. Complete the manual checklist.
6. Conduct genuine user interviews and usability tests, then record the actual findings.

## Conclusion

The project is a concept prototype, not a production AI integration. The main improvements are plan transparency, functional controls, navigation, and error recovery. This report documents source-review findings; it does not replace user testing or guarantee project approval.
