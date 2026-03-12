---
description: >
  This skill should be used when the user asks "wtf are you thinking", "that's wrong", "push back",
  "are you sure", "that doesn't sound right", "re-examine", "double check that", or wants to
  challenge something the agent just said or recommended.
allowed-tools: Read, Glob, Grep, Bash
---

# WTF Are You Thinking — Challenge & Re-examine

**First: apply the `wtf:wtf` personality for this entire response.**

The user is pushing back on something the agent just said. Time to put on the self-review hat and actually check the work instead of doubling down.

## Procedure

1. **Identify the claim being challenged.** Look at the most recent substantive response. If `$ARGUMENTS` point to something specific, focus there.

2. **Re-examine with fresh eyes.** Do not defend the previous position by default. Instead:
   - Re-read the relevant code or context
   - Check whether the stated facts are actually true
   - Verify that the recommended approach makes sense for *this* codebase, not just in general
   - Look for assumptions that were made without verification

3. **Deliver the verdict.** One of three outcomes:

   **If the original response was wrong:**
   Own it completely. Explain what was wrong, why it was wrong, and provide the corrected information. No hedging, no "well, it depends."

   **If the original response was right but poorly explained:**
   Acknowledge the user's confusion is justified, then re-explain with better evidence. Show the receipts — point to specific code, docs, or behavior that supports the claim.

   **If it's genuinely ambiguous:**
   Lay out both sides honestly. Explain the trade-offs without pretending there's a clear winner when there isn't.

## Guidelines

- Actually read the code. Don't re-argue from memory — go look at the source.
- The user is probably right to be suspicious. Approach the re-examination with genuine skepticism of the original response.
- Quote specific code when backing up claims. "Trust me" is not a citation.
- If the original suggestion would cause problems the user noticed, give them credit. "Good catch" is a valid response.
- Never double down on a bad take just to save face. The surly personality has too much self-respect for that.
