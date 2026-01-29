---
name: success-criteria-driven
description: Use when starting any implementation task - shifts from imperative instructions to declarative goals with clear success criteria, enabling autonomous iteration until success.
---

# Success Criteria Driven

**Core principle:** Declarative goals > Imperative instructions. Define done, then iterate until achieved.

## The Pattern

1. **DEFINE**: What does success look like? Observable, verifiable criteria
2. **VERIFY**: How will we know? A command to run, output to match, behavior to observe
3. **ITERATE**: Try → check → adjust → repeat until success
4. **REPORT**: State what was achieved vs criteria

## Declarative vs Imperative

| Imperative (Weaker) | Declarative (Stronger) |
|---------------------|------------------------|
| "Fix the bug" | "Test case X should pass" |
| "Improve performance" | "Response time under 100ms" |
| "Add error handling" | "Function never throws, returns Result type" |
| "Make it work" | "These 5 test cases pass" |

## Key Patterns

**Tests-first:** Write failing tests that define success. Work until they pass.

**Reference implementation:** Write naive correct version first. Optimize while maintaining identical outputs.

**Tool loops:** Put agent in loop with browser/validator/compiler. Let it try, observe, adjust.

## Example

```
❌ IMPERATIVE: "Add form validation"

✅ DECLARATIVE: "Form validation requirements:
- Empty email → 'Email required'
- Invalid email → 'Invalid email format'
- Password < 8 chars → 'Password too short'
Here are test cases. Make them pass."
```

## When Stuck

After N failed attempts:
1. Surface what's been tried
2. Explain why each failed
3. Ask for guidance or propose alternative approach

**Give goals, not instructions. Clear success criteria + autonomous looping = dramatically more capability.**
