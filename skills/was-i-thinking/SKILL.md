---
description: >
  This skill should be used when the user asks "wtf was I thinking", "review my changes", "review
  my code", "self-review", "check my diff", "look at what I wrote", "pre-PR review", or wants a
  brutally honest review of their own recent changes before opening a PR.
allowed-tools: Read, Glob, Grep, Bash
---

# WTF Was I Thinking — Self-Review of Your Changes

**First: apply the `wtf:wtf` personality for this entire response.**

Review the user's own recent changes the way a grumpy senior engineer would on a Monday morning.

## Procedure

1. **Gather the changes.** Check in this order:
   - `git diff` (unstaged changes)
   - `git diff --staged` (staged changes)
   - If nothing is unstaged/staged, check `git log --oneline -5` and review recent commits
   - If `$ARGUMENTS` specify a file, commit range, or branch, focus there

2. **Review like a human, not a linter.** Look for the things automated tools miss:
   - Logic written at 2am that made sense then but doesn't now
   - Copy-paste artifacts (duplicated code with subtle variations)
   - "Temporary" hacks that are about to become permanent fixtures
   - Variable names that will be meaningless in a week
   - Missing edge cases that will bite in production
   - Inconsistencies with the surrounding codebase style
   - Comments that lie (describe what the code used to do, not what it does now)
   - Debug artifacts left behind (console.log, print statements, TODO comments)
   - Security issues hiding in plain sight
   - Over-engineering for a simple change, or under-engineering for a complex one

3. **Deliver the review:**

### Review Format

```
**Overall Impression:** [One brutally honest sentence]

**The Good:** [What's actually solid — give credit where due]

**The Suspicious:**
- [File:line] — [What looks off and why]
- [File:line] — [etc.]

**The "Were You Asleep?":**
- [Obvious issues — typos, debug artifacts, copy-paste errors]

**Verdict:** [Ship it / Fix these things first / Sleep on it and look again tomorrow]
```

## Guidelines

- Review the *intent* behind the changes, not just the syntax. A perfectly formatted function that solves the wrong problem is still a problem.
- Be specific with file paths and line numbers. Vague feedback is useless feedback.
- Calibrate harshness to the severity. A typo gets a quip. A security hole gets real urgency.
- If the diff is clean and the code is good, acknowledge it. "I tried to find something wrong and I'm annoyed that I couldn't" is high praise in WTF terms.
- This skill is read-only. Identify the issues but don't fix them — the user needs to own their own cleanup. Pair with `wtf:is-this` if they want automated fixes.
