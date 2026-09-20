---
name: python-standard
description: Baseline cross-project Python coding standards for naming, readability, immutability, and code-quality.
license: Complete terms in LICENSE.txt
metadata:
  author: Deep Dive Security
  version: 1.0.0
---

# Coding Standards & Best Practices

## When to Use
- Reviewing code for quality and maintainability
- Refactoring existing code to improve readability, reduce technical debt, follow coding standards, improve performance, ensure immutability, or enhance security
- Setting up linting, formatting, or type-checking rules

## Scope Boundaries
Invoke this skill for: 
- Descriptive naming
- Immutability defaults
- Readability, KISS, DRY, and YAGNI principle enforcement
- Error-handling expectations and code review

Do not use this skill for: 
- API design
- Frontend architecture
- Backend architecture
- Database design

## Code Quality Principles
### 1. Readability First
- Code is read more than written
- Clear variable and function names that follow consistent naming conventions
- Self-documenting code with minimal comments
- Consistent formatting and style

### 2. KISS (Keep It Simple, Stupid)
- Avoid unnecessary complexity
- Break down complex problems into simpler, smaller functions or modules
- Avoid over-engineering or premature optimization
- Easy to understand code preferred over clever or complex solution

### 3. DRY (Don't Repeat Yourself)
- Avoid code duplication by abstracting common functionality into reusable functions, classes, or modules
- Use libraries or frameworks to avoid reinventing the wheel
- Refactor duplicated code when identified

### 4. YAGNI (You Aren't Gonna Need It)
- Focus on current requirements and avoid speculative features
- Refactor and add features as needed based on actual use cases
- Start simple, only refactor when necessary
- Avoid speculative generality

## Common Anti-Patterns

```python
# Bad: Bare except
try:
    ...
except:
    pass

# Good: Specific exception E722
try:
    ...
except ValueError as e:
    handle_error(e)
```

```python
# Bad: Compound statement
if foo == "blah": do_blah_thing()

# Good: Multi-line E701
if foo == "blah":
    do_blah_thing()
```

```python
# Bad: Using equality operator for None comparison
if arg != None:
    pass
if None == arg:
    pass

# Good: Using is or is not for None comparison E711
if arg is not None:
    pass
```

```python
# Bad: Assigning a lambda function to a variable
f = lambda x: 2 * x

# Good: Using a regular function E731
def f(x):
    return 2 * x
```