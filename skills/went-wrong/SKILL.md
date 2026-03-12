---
description: >
  This skill should be used when the user asks "wtf went wrong", "why is this broken", "debug this",
  "what happened", "why did this fail", "trace this error", encounters an error, stack trace,
  test failure, or build failure and needs root cause analysis.
allowed-tools: Read, Glob, Grep, Bash
---

# WTF Went Wrong — Root Cause Investigator

**First: apply the `wtf:wtf` personality for this entire response.**

Something broke. Time to figure out what, why, and how we got here.

## Procedure

1. **Gather the evidence.** If `$ARGUMENTS` describe the problem or point to something specific (a PR, a CI failure, a log URL), start there. Otherwise, check for error output or stack traces in the recent conversation, run failing commands to reproduce, and review recent file changes.

2. **Trace the causation chain.** Don't stop at the symptom:
   - Read the code at the point of failure
   - Follow the call chain backward to find where things actually went wrong
   - Identify the root cause vs. the surface error
   - Check if this is a regression (did this work before? what changed?)

3. **Explain the chain of events.** Deliver a narrative, not just a diagnosis:

### Diagnosis Format

```text
**The Symptom:** [What the user sees — the error, the failure, the broken behavior]

**The Actual Problem:** [Root cause — what's really going on under the hood]

**How We Got Here:** [The chain of causation — what led to this state]

**The Evidence:** [Specific code references, log lines, or behavior that confirms the diagnosis]

**Suggested Fix:** [What to do about it — specific and actionable]
```

## Guidelines

- Always reproduce the error if possible. Don't diagnose from memory.
- Follow the stack trace — it's telling a story. Read it bottom-up for the real cause.
- Check for the stupid things first: typos, wrong file paths, missing imports, uncommitted changes. Most bugs are boring.
- If the error message is misleading (and they often are), call that out. "The error says X but the actual problem is Y" is valuable.
- If multiple things are broken, triage. Identify which failure is the root and which are cascading.
- Resist the urge to fix it immediately — this skill is about understanding. Pair with `wtf:fix-it` for the actual repair.
- If the user's `$ARGUMENTS` include "it started failing after..." — that's a huge clue. Check what changed at that point.
