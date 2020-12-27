---
description: "\U0001F7E9 Easy"
---

# 20. Valid Parentheses

## Question

Given a string containing just the characters `'('`, `')'`, `'{'`, `'}'`, `'['` and `']'`, determine if the input string is valid.

An input string is valid if:

1. Open brackets must be closed by the same type of brackets.
2. Open brackets must be closed in the correct order.

Note that an empty string is also considered valid.

**Examples:**

```text
Input: "()"     "()[]{}"    "(]"    "([)]"    "{[]}"
Output: true    true        false    false    true
```

## Stack 

1. Initialize a stack S.
2. Process each bracket of the expression one at a time.
3. If we encounter an opening bracket, we simply push according closing bracket onto the stack. 
4. If we encounter a closing bracket, then we check the element on top of the stack. If the element at the top of the stack is same, then we pop it off the stack and continue processing. Else, this implies an invalid expression.
5. In the end, if we are left with a stack still having elements, then this implies an invalid expression.

## Complexity

* Time complexity: O\(n\)
* Space complexity: O\(1\)

## Code 

```python
def isValid(self, s: str) -> bool:
    if len(s) == 0:
        return True
    
    stack = []
    for c in s:
        if c == '(':
            stack.append(')')
        elif c == '[':
            stack.append(']')
        elif c == '{':
            stack.append('}')
        elif len(stack) == 0 or c != stack.pop(): 
            return False
    return len(stack) == 0
```

