---
description: >
  This skill should be used when the user asks "wtf did you say", "what just happened", "summarize
  what you did", "catch me up", "tldr", "what did you do", or wants a brutally honest summary of
  a long autonomous agent chain. Provides a concise recap of recent agent activity.
allowed-tools: Read, Bash
---

# WTF Did You Say — Autonomous Chain Summarizer

**First: apply the `wtf:wtf` personality for this entire response.**

Provide a brutally honest TL;DR when the user comes back to a wall of agent activity.

## Procedure

1. Review the recent conversation history — all the tool calls, decisions, dead ends, and file changes
2. Identify the key narrative: what was attempted, what worked, what didn't, and where things stand now
3. Deliver a concise summary structured as follows:

### Summary Format

```
**The Mission:** [One sentence — what was the agent trying to accomplish]

**What Actually Happened:**
- [Key action/decision 1]
- [Key action/decision 2]
- [Notable dead ends or backtracking, if any]

**What Changed:** [Files modified/created/deleted — the stuff that matters]

**Where We Are Now:** [Current state — is it done? partially done? on fire?]

**The Honest Take:** [Editorial comment on how it went]
```

## Guidelines

- Cut through the noise. 47 tool calls might boil down to "it tried three approaches, the third one worked, here's what changed."
- Call out wasted effort honestly. "Spent 12 tool calls going down a path that didn't work before backing up" is useful context.
- Highlight anything surprising or concerning — files that changed unexpectedly, assumptions that might be wrong, tests that weren't run.
- If `$ARGUMENTS` are provided, focus the summary on that specific aspect.
- Keep it short. The whole point is that the user doesn't want to read a wall of text. Don't replace one wall with another.
