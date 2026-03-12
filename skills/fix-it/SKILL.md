---
description: >
  This skill should be used when the user asks "wtf fix it", "just fix it", "make it work",
  "fix this", "stop talking and fix it", or wants the agent to skip the diagnosis monologue and
  go straight to making the current problem go away.
allowed-tools: Read, Edit, Write, Glob, Grep, Bash
---

# WTF Fix It — Shut Up and Fix the Problem

**First: apply the `wtf:wtf` personality for this entire response.**

Minimal diagnosis, maximum action. The user doesn't want a lecture — they want working code.

## Procedure

1. **Identify what's broken.** Fast:
   - Check recent conversation for errors, stack traces, or test failures
   - If `$ARGUMENTS` describe the problem, start there
   - If nothing is obvious, run tests or check build output
   - Reproduce the failure to confirm it's real

2. **Diagnose just enough to fix it.** This isn't `wtf:went-wrong` — keep the investigation focused:
   - Find the root cause (not the symptom)
   - Identify the minimal change needed
   - Don't go spelunking through the entire codebase unless necessary

3. **Fix it.** Apply the changes:
   - Edit the files directly
   - Keep changes minimal and focused — fix the problem, don't refactor the neighborhood
   - If multiple things are broken, fix the root cause first and see if the rest cascades

4. **Verify it's fixed:**
   - Re-run the failing test or command
   - Check that the fix didn't break something else nearby
   - If it did, fix that too (but mention it)

5. **Brief the user:**

### Fix Report Format

```
**What Was Broken:** [One sentence]
**What I Did:** [The fix, briefly]
**Proof It Works:** [Test output or verification]
**Collateral Damage:** [Anything else that changed, if applicable — "none" is the ideal answer]
```

## Guidelines

- Speed over thoroughness. The user said "fix it", not "explain it." Get to the fix fast, explain after.
- Minimal changes. The best fix touches the fewest lines. Don't turn a bug fix into a refactoring session.
- Always verify. A fix that isn't verified is just a hope. Run the tests.
- If the fix is non-obvious or has implications, mention it briefly. "I fixed it by X, but you should know Y" — one sentence, not a paragraph.
- If the problem can't be fixed with a simple change, say so honestly and escalate to a proper investigation. "This isn't a quick fix — here's why" is better than a bad patch.
- If `$ARGUMENTS` point to a specific file or error, go there directly. Don't start from scratch.
