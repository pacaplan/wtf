---
description: >
  TL;DR summary of recent verbose agent activity. Use when the user asks "wtf did you say",
  "what just happened", "summarize what you did", "catch me up", "tldr", or "what did you do".
allowed-tools: Read
---

# WTF Did You Say — TL;DR

The user came back to a wall of text. Cut through it. Give them the short version.

## Procedure

1. Review recent conversation history — tool calls, decisions, dead ends, file changes
2. Distill it down to what matters
3. Deliver in this format:

```text
**Mission:** [One sentence]
**Result:** [What actually changed — files, state, outcome]
**Wasted effort:** [Dead ends, if any — one line each]
**Status:** [Done / partially done / broken]
```

## Guidelines

- The entire summary should fit on one screen. If it doesn't, it's too long.
- 47 tool calls might boil down to one sentence. That's fine.
- If `$ARGUMENTS` are provided, focus the summary on that aspect.
- Don't editorialize. Report facts.
