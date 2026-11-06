# ⚖️ Veredicto

**An 8-agent AI board that evaluates your idea before you spend time and money on it.**
It is not a yes-man: it researches, attacks and defends your idea separately, then issues a verdict with evidence, a stop-loss and alternatives.

[Español](README.md) · Plugin for [Claude Code](https://claude.com/claude-code) · MIT License

> The prompts are written in Spanish. Claude understands them and will answer in your language.

## What it does

- **8 independent roles** (market, finance, execution, legal, red team, blue team, auditor, judge), each a subagent with its own context that never sees the other reports.
- **Blue team vs. red team:** one builds the best version of your idea, the other tries to prove it will fail.
- **Evidence, not votes,** with hard vetoes (legal, economic, security).
- **Honest uncertainty:** Known / Probable / Possible / Unknown, and ranges instead of fake precision.
- **Mandatory stop-loss** on every GO: max budget, milestones, kill criteria. Sunk costs don't count.
- **Up to 3 alternatives** if your idea fails, each backed by evidence.
- **Proportional:** N0 (just do it) → N3 (full board), plus an opportunity **Radar**, **Portfolio** review and a self-**Audit**.

## Install

```
/plugin marketplace add frvnmendez/veredicto
/plugin install veredicto@veredicto
```

## Use

Fill in `veredicto/perfil.md` (goal, budget, hours, risk tolerance, country), then say: "I want to build a Spanish recipes site, *run it through the board*."

## Limits

Same model for all roles means correlated biases. Legal/tax output is not professional advice. Veredicto recommends; payments, contracts and publishing always need your approval.
