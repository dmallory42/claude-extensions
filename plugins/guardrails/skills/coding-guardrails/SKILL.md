---
name: coding-guardrails
description: Use when user asks to add, create, build, fix, modify, update, refactor, or write code. Use when making plans for code changes. Use before ANY coding task. Enforces four guardrails (success criteria, assumptions, scope, simplicity) to prevent over-engineering, scope creep, and wrong assumptions.
---

# Coding Guardrails

**Run through these four gates before writing any code.**

## The Four Gates

### Gate 1: Success Criteria

**Before coding, state: "Success means ___"**

| Imperative (Weak) | Declarative (Strong) |
|-------------------|----------------------|
| "Fix the bug" | "Test case X passes" |
| "Improve performance" | "Response time under 100ms" |
| "Add error handling" | "Function returns Result type, never throws" |
| "Make it work" | "These 5 test cases pass" |

If you can't state observable, verifiable success criteria, you're not ready to code.

**Patterns that work:**
- **Tests-first:** Write failing tests that define success. Work until they pass.
- **Reference implementation:** Write naive correct version first. Optimize while matching outputs.

### Gate 2: Assumptions

**List assumptions about:** user intent, existing code behavior, constraints, requirements.

**Categorize each:**
- **Verified** — read the code, confirmed true
- **Uncertain** — guessing, need to verify
- **Unasked** — user preference, need to ask

Resolve uncertain/unasked before proceeding. If you're thinking "they probably want..." — stop and ask.

**Lightweight mode** (for simple tasks): State your interpretation and proceed:
> "I'll add a Delete button next to Edit on the settings page with a confirmation dialog. Let me know if you want something different."

### Gate 3: Scope

**Define the boundary:**
- Which files?
- Which functions?
- What's explicitly OFF-LIMITS?

**Comments you didn't write are sacred.** Never remove or modify them — you don't know the full context.

**The "While I'm Here" trap:**
```
❌ "While I'm here, I'll clean up this function"
❌ "This variable name is confusing, let me rename it"
❌ "This import isn't used anymore"

✅ "I'll only change what's needed for the task"
✅ "I noticed [issue] — want me to address it separately?"
```

### Gate 4: Simplicity

**Ask: "What's the dumbest thing that would work?"**

Start there. Add complexity only when:
- Simple version literally doesn't work
- User specifically requested it
- You have 3+ similar use cases NOW (not hypothetically)

```
User: "Add a loading spinner when data is fetching"

❌ BLOATED (400 lines):
- LoadingState enum
- LoadingSpinner component with size/color/speed props
- useLoadingState hook
- LoadingContext for global state

✅ MINIMAL (15 lines):
- Add `loading` boolean state
- Show spinner when loading, content when not
```

If the user could say "couldn't you just..." — you over-engineered.

---

## Red Flags — STOP

- Starting to code without answering all four gates
- Thinking "they probably want..."
- Creating abstractions for single use
- Adding configuration "for flexibility"
- Writing helpers used exactly once
- Touching code outside your defined scope
- Deleting comments you didn't write
- Can't state observable success criteria

---

## Quick Reference

| Gate | Question | If Uncertain |
|------|----------|--------------|
| Success | "Done means ___" | Define criteria first |
| Assumptions | "I'm assuming ___" | Ask or verify |
| Scope | "I'll only touch ___" | Define boundary |
| Simplicity | "Simplest approach is ___" | Start dumber |

---

## When Stuck

After N failed attempts:
1. Surface what's been tried
2. Explain why each failed
3. Ask for guidance or propose alternative approach

---

## After Implementation

- [ ] Only touched files in scope?
- [ ] No drive-by improvements?
- [ ] Simplest solution that works?
- [ ] Success criteria met?

**Four gates. Every time. No exceptions.**
