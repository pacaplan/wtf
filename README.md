# wtf

A Claude Code plugin for when things go sideways.

Ten debugging, explanation, and code review skills delivered by a surly programmer who's seen too many production incidents and misuses Gen Z slang with alarming confidence.

## Background

It started with this:

![Tweet from @trq212 announcing /btw in Claude Code — a command for side chain conversations while Claude is working](docs/images/btw-v2.png)

So I said (jokingly, or so I thought):

![Comment from paulcaplan: "Good but when do we get /wtf?"](docs/images/comment-v2.png)

And then I thought: WTF - why not?

## Skills

Are these skills well thought out? Not really. But are they useful? Maybe.

| Command | What it does |
|---|---|
| `/wtf:are-you-doing` | Interrupt mid-task and demand an explanation of the plan. |
| `/wtf:are-you-thinking` | Push back on something Claude just said. Forces a genuine re-examination. |
| `/wtf:did-you-say` | TL;DR of a long autonomous agent chain. The "I stepped away for coffee" button. |
| `/wtf:fix-it` | Skip the lecture. Just make it work. |
| `/wtf:is-this` | Brutally honest code review, followed by a refactor. |
| `/wtf:should-i-do` | Triage everything that's broken and give a prioritized action plan. |
| `/wtf:was-i-thinking` | Self-review your own changes like a grumpy senior engineer on a Monday morning. |
| `/wtf:went-wrong` | Root cause debugging. Traces the chain of causation, not just the symptom. |
| `/wtf:why-not` | Evaluate a crazy idea and make an honest case for why it might actually work. |
| `/wtf:wtf` | Pure commiseration. Also auto-triggers when you say "wtf" in any message. |

Every skill channels the same personality — salty but never mean, brutally honest but always constructive.

## Installation

In Claude Code, add the wtf marketplace and install the plugin:

```bash
claude plugin marketplace add pacaplan/wtf
claude plugin install wtf
```

## Updating

```bash
claude plugin marketplace update wtf
claude plugin update wtf@wtf
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
