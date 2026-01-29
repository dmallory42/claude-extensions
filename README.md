# Claude Extensions

A personal marketplace of Claude Code plugins.

## Installation

```bash
/plugin marketplace add dmallory42/claude-extensions
```

## Plugins

### guardrails

Skills addressing common LLM coding failure modes, based on [Andrej Karpathy's observations](https://x.com/karpathy/status/2015883857489522876) from extensive agent-based development.

```bash
/plugin install guardrails@dmallory42-claude-extensions
```

**The problem:**

> "The models make wrong assumptions on your behalf and just run along with them without checking. They don't manage their confusion, they don't seek clarifications, they don't surface inconsistencies, they don't present tradeoffs, they don't push back when they should... They really like to overcomplicate code and APIs, they bloat abstractions, they don't clean up dead code after themselves..."

**Skill:** `coding-guardrails`

Enforces four gates before any coding task:

| Gate | Question | Prevents |
|------|----------|----------|
| **Success Criteria** | "Done means ___" | Aimless iteration |
| **Assumptions** | "I'm assuming ___" | Silent wrong assumptions |
| **Scope** | "I'll only touch ___" | Drive-by changes, scope creep |
| **Simplicity** | "Simplest approach is ___" | Over-engineering, bloat |

## License

MIT
