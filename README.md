# Agent Coding Guardrails

Skills addressing common failure modes in LLM-assisted coding, based on [Andrej Karpathy's observations](https://x.com/karpathy/status/2015883857489522876) from extensive agent-based development.

## The Problem

LLMs have crossed a threshold where agent-based coding is the primary mode for many engineers. But they exhibit predictable failure patterns:

> "The models make wrong assumptions on your behalf and just run along with them without checking. They don't manage their confusion, they don't seek clarifications, they don't surface inconsistencies, they don't present tradeoffs, they don't push back when they should... They really like to overcomplicate code and APIs, they bloat abstractions, they don't clean up dead code after themselves... They will implement an inefficient, bloated, brittle construction over 1000 lines of code and it's up to you to be like 'umm couldn't you just do this instead?' and they will be like 'of course!' and immediately cut it down to 100 lines."

These skills provide guardrails for each failure mode.

## Skills

### surfacing-assumptions
**Use when:** About to implement anything

Forces explicit assumption checking before writing code. Instead of silently deciding and running with it, the agent must list assumptions, categorize them (verified vs uncertain vs unasked), and resolve uncertainties before proceeding.

### minimal-implementation
**Use when:** Implementing any feature or fix

Prevents over-engineering by enforcing a "simplest thing that works" approach. Includes a gate check for scope creep, unnecessary abstractions, and proportional code size. If you can do it in 100 lines, don't write 1000.

### scope-discipline
**Use when:** Modifying existing code

Prevents drive-by changes to code outside the task scope. Comments you didn't write are sacred. Adjacent code is off-limits. Mention issues you notice, but don't fix them without asking.

### success-criteria-driven
**Use when:** Starting any implementation task

Shifts from imperative instructions ("do X then Y") to declarative goals ("achieve state S"). Define observable success criteria, then iterate until achieved. This is where LLM agents excel - they never get tired or demoralized, they just keep working toward the goal.

## Installation

### Via Marketplace (Recommended)

```bash
# Add this repo as a marketplace
/plugin marketplace add dmallory42/agent-coding-guardrails

# Install the plugin
/plugin install agent-coding-guardrails@dmallory42-agent-coding-guardrails
```

### Manual (All Projects)

```bash
cp -r skills/* ~/.claude/skills/
```

### Manual (Single Project)

```bash
cp -r skills/ .claude/skills/
```

## License

MIT
