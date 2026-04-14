# wtf

A Claude Code plugin for when things go sideways.

Ten debugging, explanation, and code review skills for the moments when something just broke, you can't remember what you were doing, or you need a second opinion before shipping.

## Background

It started with this:

![Tweet from @trq212 announcing /btw in Claude Code — a command for side chain conversations while Claude is working](docs/images/btw-v3.png)

So I said (jokingly, or so I thought):

![Comment from paulcaplan: "Good but when do we get /wtf?"](docs/images/comment-v3.png)

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
| `/wtf:was-i-thinking` | Self-review your own recent diffs and commits before opening a PR. |
| `/wtf:went-wrong` | Root cause debugging. Traces the chain of causation, not just the symptom. |
| `/wtf:why-not` | Evaluate an unconventional idea and make an honest case for why it might work. |
| `/wtf:wtf` | Quick acknowledgement and redirect when you just say "wtf" without context. |

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
