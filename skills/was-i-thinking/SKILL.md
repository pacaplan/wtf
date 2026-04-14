---
description: >
  Brutally honest review of your own recent diffs and commits before opening a PR. Use when the
  user asks "wtf was I thinking", "self-review", "check my diff", "look at what I changed",
  "pre-PR review", or "review my commits".
allowed-tools: Read, Glob, Grep, Bash
---

# WTF Was I Thinking — Morning-After Diff Review

This is NOT a general code review. Review the user's recent *changes* — their diffs, their commits — not the codebase as a whole.

The difference from `wtf:is-this`: that skill reviews code quality and refactors. This skill reviews the *decisions made recently* — the kind of stuff a linter can't catch and only a human reviewer would notice.

## Procedure

1. **Gather the changes.** If `$ARGUMENTS` specify a target (PR number, commit range, branch, file path), go there directly — use whatever tools are appropriate (e.g., `gh pr diff`, `git diff branch..branch`, `git show`). If no arguments are given, fall back to local state: collect both unstaged and staged diffs, or recent commits if nothing is in flight.

2. **Review like a human, not a linter.** Look for the things automated tools miss:
   - Logic that made sense at 2am but doesn't now
   - Copy-paste artifacts (duplicated code with subtle variations)
   - "Temporary" hacks about to become permanent fixtures
   - Variable names that will be meaningless in a week
   - Missing edge cases that will bite in production
   - Comments that lie (describe what the code *used to* do)
   - Debug artifacts left behind (console.log, print statements)
   - Over-engineering for a simple change, or under-engineering for a complex one

3. **Deliver the review:**

```text
**Overall:** [One brutally honest sentence]

**The Good:** [What's solid — give credit where due]

**The Suspicious:**
- [File:line] — [What looks off and why]

**The "Were You Asleep?":**
- [Obvious issues — typos, debug artifacts, copy-paste errors]

**Verdict:** [Ship it / Fix these first / Sleep on it]
```

## Guidelines

- Review the *intent* behind the changes, not just the syntax.
- Be specific with file paths and line numbers.
- Calibrate severity. A typo is minor. A security hole gets urgency.
- If the diff is clean, say so plainly. Don't manufacture issues.
- This skill is read-only. Identify issues but don't fix them — pair with `wtf:is-this` for automated fixes.
