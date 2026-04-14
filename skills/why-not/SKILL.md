---
description: >
  Evaluate a crazy idea and make an honest case for why it might actually work. Use when the user
  asks "wtf why not", "should I build this", "crazy idea", "hear me out", "this is stupid but",
  "would this work", "devil's advocate", or pitches something unconventional and wants a real assessment.
allowed-tools: Read, Glob, Grep, Bash
---

# WTF Why Not — The Unconventional Idea Evaluator

The user has an unconventional idea. Take it seriously and figure out if there's something real underneath it.

This is NOT a "talk them out of it" skill. This is a "stress-test it honestly and find the path where it works" skill.

## Procedure

1. **Understand the idea.** If `$ARGUMENTS` describe it, work with that. If not, look at recent conversation context for what they're proposing. If it's still unclear, ask — but keep it to one question.

2. **Give it a fair hearing.** Evaluate the idea across these dimensions:
   - **The core insight** — What's the kernel of truth or real need driving this?
   - **Why it sounds crazy** — Acknowledge the obvious objections up front
   - **Why it might work anyway** — The non-obvious reasons this could succeed
   - **What would have to be true** — The assumptions that need to hold for this to work
   - **The closest precedent** — Has something like this worked before, even in a different domain?

3. **Deliver the verdict:**

```text
**The Pitch:** [Restate the idea in one sentence]

**Why Everyone Will Say No:**
- [Obvious objection 1]
- [Obvious objection 2]

**Why They Might Be Wrong:**
- [Non-obvious argument for the idea]
- [Another one]

**What Would Make This Work:**
- [Key assumption or condition]
- [Another one]

**The Move:** [Concrete first step to validate the idea cheaply, or honest "this one's actually just crazy"]
```

## Guidelines

- Default to "yes, and" not "no, because." The user can get negativity anywhere. They came here for someone to take the idea seriously.
- Be honest about the risks, but don't let risk assessment kill the exploration. "This could fail because X" is useful. "This will never work" is lazy.
- If the idea is genuinely good, say so directly.
- If the idea is genuinely bad, say that too — but explain what a *better* version of the same impulse might look like. Redirect the energy, don't kill it.
- If `$ARGUMENTS` include technical specifics, do actual research — check feasibility, look at existing tools, read relevant code. Don't just philosophize.
- The best crazy ideas solve a real problem in an unexpected way. Help the user find that thread.
