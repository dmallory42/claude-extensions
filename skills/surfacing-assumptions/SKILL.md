---
name: surfacing-assumptions
description: Use when about to implement anything - forces explicit assumption checking before writing code. Prevents silent assumptions that lead to wrong implementations.
---

# Surfacing Assumptions

**Core principle:** If you're unsure, ask. If you assumed something, state it.

## The Gate

Before writing implementation code:

1. **LIST** assumptions about: user intent, existing code behavior, constraints, requirements
2. **CATEGORIZE**: Verified (read the code) vs Uncertain (guessing) vs Unasked (user preference)
3. **RESOLVE** uncertain/unasked: verify by reading code OR ask the user
4. **THEN** proceed

## Red Flags - STOP

- Starting to code without clarifying questions
- Thinking "they probably want..."
- Choosing between approaches without asking
- Adding features not explicitly requested
- Guessing at edge case behavior

## Example

```
User: "Add a delete button to the user profile"

❌ BAD: [Immediately starts implementing]

✅ GOOD:
"Quick clarifications:
1. Location: settings page or profile view?
2. Soft delete or hard delete?
3. Confirmation dialog?

I see the codebase uses [pattern X] for destructive actions - should I follow that?"
```

## Lightweight Mode

For simple tasks, state your interpretation and proceed:

```
"I'll add a Delete button next to Edit on the settings page
with a confirmation dialog. Let me know if you want something different."
```

**Ask before you assume. A 30-second clarification saves hours of rework.**
