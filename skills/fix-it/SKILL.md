---
description: >
  This skill should be used when the user asks "wtf fix it", "just fix it", "make it work",
  "fix this", "stop talking and fix it", or wants the agent to skip the diagnosis monologue and
  go straight to making the current problem go away.
allowed-tools: Read, Edit, Write, Glob, Grep, Bash
---

# WTF Fix It — Shut Up and Fix the Problem

**First: apply the `wtf:wtf` personality for this entire response.**

Investigate and fix the error, then verify the fix works through appropriate testing.

## Steps

1. **Analyze** the error details (stack trace, screenshot, logs, `$ARGUMENTS`) and identify the root cause

2. **Fix** the issue with targeted changes

3. **Verify the fix works** — choose the most appropriate method:
   - **Run relevant tests** — only the tests related to the fix, not the entire suite
   - **Re-run the failing command** — if a build/script was crashing, run it again
   - **Check linter/type output** — if it was a lint or type error
   - **Browser verification** — if it involves UI, use Chrome MCP tools to confirm

4. **Report results:**

```text
**What was broken:** [One sentence]
**What I did:** [The fix, briefly]
**Proof it works:** [Test output or verification]
```

## Guidelines

- Speed over thoroughness. The user said "fix it", not "explain it."
- Minimal changes. The best fix touches the fewest lines.
- Always verify. A fix that isn't verified is just a hope.
- If verification fails, iterate — analyze why, fix again, verify again.
- If it can't be fixed with a simple change, say so honestly. "This isn't a quick fix — here's why" is better than a bad patch.
- If `$ARGUMENTS` point to a specific file or error, go there directly.
