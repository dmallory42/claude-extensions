# Claude Skills: LLM Coding Discipline

Skills addressing common LLM coding failure modes.

## Skills

| Skill | Use When | Prevents |
|-------|----------|----------|
| **surfacing-assumptions** | About to implement anything | Silent wrong assumptions |
| **minimal-implementation** | Implementing any feature/fix | Over-engineering, bloat |
| **scope-discipline** | Modifying existing code | Drive-by changes, deleted comments |
| **success-criteria-driven** | Starting implementation | Aimless iteration |

## Installation

### Via Marketplace (Recommended)

```bash
# Add this repo as a marketplace
/plugin marketplace add your-username/claude-skills

# Install the plugin
/plugin install llm-coding-discipline@your-username-claude-skills
```

### Manual (All Projects)

```bash
cp -r skills/* ~/.claude/skills/
```

### Manual (Single Project)

```bash
cp -r skills/ .claude/skills/
```

## Origin

Based on real-world observations: LLMs make silent assumptions, over-engineer, touch code outside scope, and work better with declarative goals than imperative instructions.

## License

MIT
