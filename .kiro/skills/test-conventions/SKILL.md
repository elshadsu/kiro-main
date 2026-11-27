---
name: "app-conventions"
description: >
  Load when reviewing non-test Python application code.
  Exclude tests/, test_*.py, and *_test.py files.
---

# App Conventions

## Rules

- [LOW] Naming: use snake_case for functions and variables, PascalCase for classes, and UPPER_CASE for constants.
- [LOW] Documentation: public functions must include type hints and docstrings.
- [MEDIUM] Error handling: catch specific exceptions instead of using bare except statements. Do not silently suppress errors.

## Template

### Compliant

```python
def calculate_total(price: float, quantity: int) -> float:
    """Calculate the total price."""
    return price * quantity
```

### Non-compliant

```python
def CalculateTotal(Price, Quantity):
    try:
        return Price * Quantity
    except:
        pass
```
