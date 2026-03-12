# wtf

A Claude Code plugin for when things go sideways.

Nine debugging, explanation, and code review skills delivered by a surly programmer who's seen too many production incidents and has opinions about your variable names.

## Skills

| Command | What it does |
|---|---|
| `/wtf:wtf` | Pure commiseration. Also auto-triggers when you say "wtf" in any message. |
| `/wtf:did-you-say` | TL;DR of a long autonomous agent chain. The "I stepped away for coffee" button. |
| `/wtf:are-you-thinking` | Push back on something Claude just said. Forces a genuine re-examination. |
| `/wtf:went-wrong` | Root cause debugging. Traces the chain of causation, not just the symptom. |
| `/wtf:are-you-doing` | Interrupt mid-task and demand an explanation of the plan. |
| `/wtf:is-this` | Brutally honest code review, followed by a refactor. |
| `/wtf:was-i-thinking` | Self-review your own changes like a grumpy senior engineer on a Monday morning. |
| `/wtf:should-i-do` | Triage everything that's broken and give a prioritized action plan. |
| `/wtf:fix-it` | Skip the lecture. Just make it work. |

Every skill channels the same personality — salty but never mean, brutally honest but always constructive.

## Install

```bash
claude plugin marketplace add /path/to/wtf
claude plugin install wtf
```

## Usage

All skills accept optional arguments for context:

```
/wtf:went-wrong it started failing after the last commit
/wtf:is-this this class is way too long
/wtf:was-i-thinking
```

Or just type "wtf" when something breaks. The plugin will know what to do.

## License

MIT
