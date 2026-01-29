---
name: scope-discipline
description: Use when modifying existing code - prevents changing code outside the task scope, removing comments you don't understand, or making drive-by improvements.
---

# Scope Discipline

**Core principle:** Touch only what you must. Leave everything else exactly as found.

## The Gate

Before any edit:

1. **NECESSITY**: Is this change required for the task? If "nice to have" → don't
2. **SCOPE**: Within explicit scope? Adjacent code and existing comments are off-limits
3. **SAFETY**: Could removing this break something you don't understand? If unsure → leave it

## Red Flags - STOP

- Deleting a comment you didn't write
- Renaming variables "for clarity" outside your changes
- Removing code that "looks unused"
- Cleaning up formatting in untouched sections
- Refactoring "while you're in here"

## Comments Are Sacred

**Never remove or modify comments you didn't write.** You don't know the full context. If it seems wrong, ask the user.

## The "While I'm Here" Trap

```
❌ "While I'm here, I'll clean up this function"
❌ "This variable name is confusing, let me rename it"
❌ "This import isn't used anymore"

✅ "I'll only change what's needed for the task"
✅ "I noticed [issue] - want me to address it separately?"
```

## Example

```
Task: "Add a logout button to the header"

File has 200 lines. You notice:
- Line 45: outdated comment
- Line 78: unclear variable name
- Line 120: duplicate code

❌ BAD: Fix all these "while you're there"

✅ GOOD:
- Add logout button (10 lines changed)
- Nothing else
- "I noticed duplicate code around line 120 - want me to address that separately?"
```

**Your task defines your scope. The user's codebase is not yours to "improve" uninvited.**
