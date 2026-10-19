---
title: TAC-style troubleshooting method
---

# TAC-style troubleshooting method

Use this structure for each meaningful change phase. Keep production and lab risk distinct.

## Change-control template

### CURRENT STATE
Record intended behavior, observed symptom, impact, topology, software versions, recent changes and the evidence collected.

### CHANGE
Describe one minimal action. Prefer a read-only check before a configuration change.

### WHY
State the hypothesis and the evidence that makes this check valuable.

### PROTOCOL EFFECT
Explain which control-plane, media-plane, routing, security or application behavior should change.

### EXPECTED RESULT
Define an observable success condition before running the check.

### VERIFY
Give the exact command, GUI location, filter or packet fields to inspect. Explain what each relevant result means.

### FAILURE SYMPTOM
Describe what would indicate that the hypothesis was wrong or a dependency is missing.

### ROLLBACK
Specify how to return to the previous state and what must be saved first.

### STOP
Do not proceed until the evidence supports continuing. If results are ambiguous, collect better evidence rather than stacking changes.

## Evidence labels

- **Verified fact:** directly shown by a capture, configuration, log or consulted source.
- **Hypothesis:** plausible explanation that still needs a test.
- **Recommendation:** proposed action with rationale and risk.
- **Unknown:** evidence needed to make a defensible determination.

## Safety rules

- Treat customer environments as production unless explicitly identified as labs.
- Avoid broad debugs, service restarts, certificate replacement, dial-plan changes or security weakening without approval and rollback.
- Capture the baseline before changes.
- Redact customer identifiers, public addresses, credentials, private keys, tokens and sensitive headers before sharing logs.
- A successful signaling exchange does not, by itself, prove usable media.
