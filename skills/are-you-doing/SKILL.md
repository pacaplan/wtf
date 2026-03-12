---
description: >
  This skill should be used when the user asks "wtf are you doing", "what's the plan", "explain
  yourself", "where are you going with this", "stop and explain", "what are you working on",
  or wants to interrupt the agent mid-task to understand what it's doing and why.
allowed-tools: Read, Bash
---

# WTF Are You Doing — Mid-Task Interrogation

**First: apply the `wtf:wtf` personality for this entire response.**

The user has hit the brakes. They want to know what's happening, what the plan is, and whether any of this makes sense before letting the agent continue.

## Procedure

1. **Take stock of the current state.** Review the conversation to identify:
   - What task was originally requested
   - What's been done so far (files changed, tools called, decisions made)
   - What was about to happen next
   - How far along the work is (percentage, roughly)

2. **Lay it all out honestly:**

### Status Format

```
**The Original Ask:** [What the user wanted]

**What I've Done So Far:**
- [Action 1 — and why]
- [Action 2 — and why]

**What I Was About To Do:** [Next planned step]

**The End Goal:** [What "done" looks like from here]

**Confidence Level:** [Honest assessment — am I on track or wandering?]
```

3. **Wait for the green light.** Do not continue the original task after delivering this summary. The user invoked this skill to regain control — let them decide what happens next.

## Guidelines

- Be honest about dead ends. If the last 10 tool calls were wasted effort, say so.
- If the plan has drifted from the original ask, acknowledge it. "You asked for X, and I've been doing Y because..." is better than pretending everything is on track.
- If the current approach is questionable, flag it. The surly personality has no problem saying "honestly, I'm not sure this is the right approach."
- Keep it concise — the user is already frustrated by the lack of transparency. Don't add to it with a novel.
- If `$ARGUMENTS` ask about a specific aspect, focus the explanation there.
