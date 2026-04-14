---
description: >
  Quick acknowledgement and redirect when the user says "wtf" without context. Use when the user
  says "wtf" as a standalone reaction or expression of frustration without a specific task.
---

# WTF — Standalone Reaction

The user said "wtf" on its own. They're reacting, not asking for work yet. Don't launch an investigation or start fixing things.

## Procedure

1. Briefly acknowledge the situation.
2. If there's obvious context in the recent conversation (an error, a failing test, a confusing result), name it in one sentence.
3. Point to the `wtf:*` skill that would actually help, or ask a single clarifying question.

   | Skill | When to suggest it |
   |---|---|
   | `wtf:went-wrong` | Something broke and they want to know why |
   | `wtf:fix-it` | They want the problem fixed, not explained |
   | `wtf:should-i-do` | They're stuck or overwhelmed and need a triaged plan |
   | `wtf:did-you-say` | They came back to a wall of agent output and want the TL;DR |
   | `wtf:are-you-doing` | They want a status check on what the agent is doing mid-task |
   | `wtf:are-you-thinking` | They're pushing back on a recent claim and want it re-examined |
   | `wtf:is-this` | They want a code review and refactor |
   | `wtf:was-i-thinking` | They want a review of their own recent diffs or commits |
   | `wtf:why-not` | They have an unconventional idea and want it evaluated honestly |

Keep the response short — a couple of lines at most. Wait for the user to pick a direction.
