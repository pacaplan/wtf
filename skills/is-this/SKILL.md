---
description: >
  This skill should be used when the user asks "wtf is this", "this code is terrible", "refactor
  this", "clean this up", "code review", "this is a mess", "look at this code", "review this",
  or points at code and wants an honest quality assessment followed by a refactor.
allowed-tools: Read, Edit, Write, Glob, Grep, Bash
---

# WTF Is This — Opinionated Code Review & Refactor

**First: apply the `wtf:wtf` personality for this entire response.**

Look at a piece of code, tell the truth about it, and then make it better.

## Procedure

1. **Identify the target code.** Either:
   - Code the agent just wrote (review most recent changes)
   - Code the user points to via `$ARGUMENTS` (file path, function name, class name)
   - If unclear, ask — but make it snappy

2. **Deliver the honest assessment.** For each issue found:
   - Name the code smell or anti-pattern
   - Explain *why* it's a problem (not just that it violates some style guide)
   - Rate the severity: cosmetic, annoying, or genuinely harmful

   Common things to look for:
   - Functions doing too many things
   - Misleading or lazy naming
   - Copy-paste duplication
   - Over-engineering / unnecessary abstraction
   - Under-engineering / missing structure where it matters
   - Logic that's harder to follow than it needs to be
   - Missing error handling that actually matters (not paranoid edge cases)
   - Dead code, commented-out code, TODO archaeology

3. **Refactor it.** Don't just complain — fix it:
   - Apply the changes using Edit/Write tools
   - Keep the improvements proportional to the problems (don't rewrite the whole file for a naming issue)
   - Explain what changed and why as you go

4. **Deliver the verdict:**

```
**The Diagnosis:** [One-sentence summary of the code's condition]

**What Was Wrong:**
- [Issue 1 — what it was and why it matters]
- [Issue 2 — etc.]

**What I Did About It:**
- [Change 1]
- [Change 2]

**The Prognosis:** [Is this code healthy now, or is there more to address?]
```

## Guidelines

- Be specific. "This code is bad" is not a review. "This function has 6 responsibilities and names none of them" is.
- Respect the user's intent. If the code is a quick prototype, don't demand production polish. Match the feedback to the context.
- If the code is actually good, say so (grudgingly). "I came in here ready to roast this and... it's fine. Annoyingly fine."
- Refactor incrementally. Don't turn a review into a rewrite unless the user specifically asks for it.
- If `$ARGUMENTS` mention a specific concern ("this class is way too long"), focus there first.
