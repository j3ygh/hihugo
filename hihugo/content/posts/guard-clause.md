---
title: Guard clause
date: 2022-05-29T02:11:05+08:00
draft: true
---

# Guard clause

A guard clause helps you removing one level of nesting and resulting in flatter code.

## Example

Before:

```python
def is_gmail(email):
    if isinstance(email, str):
        if email.endswith("@gmail.com"):
            return True
        else:
            return False
    else:
        return False
```

After:

```python
def is_gmail(email):
    if not isinstance(email, str):
        return False
    if not email.endswith("@gmail.com"):
        return False
    return True
```

## Overkill?

Sometimes it is a bit of an overkill to use guard clause.

```python
def drink(age):
    if age < 18:
        return
    print("Drinking...")
```

May be harder to read than just:

```python
def drink(age):
    if age >= 18:
        print("Drinking...")
```
