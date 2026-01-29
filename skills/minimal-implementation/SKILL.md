---
name: minimal-implementation
description: Use when implementing any feature or fix - prevents over-engineering, bloated abstractions, and unnecessary complexity.
---

# Minimal Implementation

**Core principle:** If you can do it in 100 lines, don't write 1000.

## The Gate

Before/after writing code:

1. **SCOPE**: Only what was asked? No extra features, no "while I'm here" improvements
2. **SIMPLICITY**: Simplest approach? Could something more direct work?
3. **SIZE**: Proportional to the problem? 500 lines for "add a button" = wrong
4. **CLEANUP**: Removed dead code, unused helpers, commented-out alternatives?

## Red Flags - STOP

- Creating abstractions for single implementations
- Adding configuration "for flexibility"
- Writing helpers used exactly once
- Thinking "this might be useful later"
- Using design patterns because they're "proper"

## The Test

Ask: **"What's the dumbest thing that would work?"**

Start there. Add complexity only when:
- Simple version literally doesn't work
- User specifically requested it
- You have 3+ similar use cases now

## Example

```
User: "Add a loading spinner when data is fetching"

❌ BLOATED (400 lines):
- LoadingState enum
- LoadingSpinner component with size/color/speed props
- useLoadingState hook
- LoadingContext for global state
- loading.utils.ts

✅ MINIMAL (15 lines):
- Add `loading` boolean state
- Show spinner when loading, content when not
```

**Simple > Clever. Small > Large. Direct > Abstract.**

If the user could say "couldn't you just..." then you over-engineered.
