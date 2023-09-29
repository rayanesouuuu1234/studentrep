---
toc: True
comments: True
layout: post
title: Identyfing and Correct Errors
description: A divder calculator function that locates, and fixes the error of division by 0
courses: {'csp': {'week': 4}}
type: hacks
---

```python
# Using if/else for error handling
def divide_if_else(a, b):
    # Check if the denominator is zero
    if b == 0:
        # Return an appropriate error message or value
        return "undefined!"
    else:
        return a / b

# Using try/catch for error handling
def divide_try_catch(a, b):
    try:
        return a / b
    except ZeroDivisionError:  # Catching division by zero error
        return "undefined!"

# Tester function
def test_divide(divide_function):
    test_cases = [
        (5, 2, 2.5),                # regular division
        (5, 0, "undefined!"),   # division by zero
        (0, 5, 0),                 # zero numerator
    ]
    
    for i, (a, b, expected) in enumerate(test_cases):
        result = divide_function(a, b)
        assert result == expected, f"Test case {i+1} failed: expected {expected} but got {result}"
        print(f"Test case {i+1} passed!")

# Testing both implementations
print("Testing divide_if_else:")
test_divide(divide_if_else)
print("\nTesting divide_try_catch:")
test_divide(divide_try_catch)
```

    Testing divide_if_else:
    Test case 1 passed!
    Test case 2 passed!
    Test case 3 passed!
    
    Testing divide_try_catch:
    Test case 1 passed!
    Test case 2 passed!
    Test case 3 passed!

