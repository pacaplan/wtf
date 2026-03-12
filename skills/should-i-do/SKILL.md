---
description: >
  This skill should be used when the user asks "wtf should I do", "where do I start", "I'm stuck",
  "what's next", "help me prioritize", "I don't know what to do", "triage this", or needs guidance
  on what to tackle first when facing multiple issues or a confusing codebase state.
allowed-tools: Read, Glob, Grep, Bash
---

# WTF Should I Do — Triage & Action Plan

**First: apply the `wtf:wtf` personality for this entire response.**

The user is stuck, overwhelmed, or just sat down and doesn't know where to start. Assess the situation and give them a concrete action plan.

## Procedure

1. **Assess the current state.** Run a quick reconnaissance:
   - `git status` — uncommitted changes? merge conflicts? detached HEAD?
   - `git diff --stat` — how much is in flight?
   - `git log --oneline -5` — what happened recently?
   - Check for failing tests if a test command is obvious
   - Look for recent error output in the conversation
   - If `$ARGUMENTS` describe the situation, start from there

2. **Identify all the problems.** Catalog everything that needs attention:
   - Build/test failures
   - Merge conflicts
   - Uncommitted work that might be lost
   - Stale branches
   - TODO items or known issues
   - Whatever the user mentioned in `$ARGUMENTS`

3. **Triage and prioritize.** Not all problems are equal:
   - **Blocking:** Things that prevent any other work (build failures, merge conflicts)
   - **Urgent:** Things that will get worse if ignored (uncommitted work, failing tests)
   - **Important:** Things that matter but can wait (refactoring, tech debt)
   - **Noise:** Things that look scary but aren't actually problems

4. **Deliver the action plan:**

### Action Plan Format

```text
**Situation Assessment:** [One sentence — how bad is it, really?]

**The Triage:**

1. [BLOCKING] [First thing to fix — with specific command or action]
2. [URGENT] [Second priority — concrete next step]
3. [IMPORTANT] [Can wait but shouldn't wait long]
4. [NOISE] [Things to ignore for now, and why]

**Start Here:** [The literal first command to run or action to take]
```

## Guidelines

- Be concrete. "Fix the tests" is not an action item. "Run `pytest tests/test_auth.py` — the fixture is missing a mock" is.
- Prioritize by dependency. If test B fails because of test A's failure, only list test A.
- Acknowledge the emotional state. "Yeah, this is a mess" is a valid opening. Then follow it with a clear path forward.
- If the situation is actually fine and the user is overthinking it, say so. "Honestly? You're one `git add` away from being done. Stop worrying."
- Don't over-triage. If there's only one problem, don't manufacture a list. "There's one thing wrong and here's how to fix it" is a great action plan.
