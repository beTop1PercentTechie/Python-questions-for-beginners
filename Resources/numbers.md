# Numbers

---

###### ` Question 1: Convert String to Number `  

Write a function `convert_string_to_number` that takes a string representation of a number and converts it into an **integer** or **float**.

`Example:`  

```python
# Input:
"42.3"

# Output:
42.3
```

`Topics Covered:`  
Type conversion using `int()`, `float()`.  

**Hints:**  
- [Python int() function](https://docs.python.org/3/library/functions.html#int)  
- [Python float() function](https://docs.python.org/3/library/functions.html#float)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def convert_string_to_number(s):
    try:
        # Try converting to an integer first
        result = int(s)
    except ValueError:
        # If conversion to integer fails, convert to a float
        result = float(s)
    return result

# Example usage
print(convert_string_to_number("42"))    # Output: 42 (int)
print(convert_string_to_number("42.3"))  # Output: 42.3 (float)
```

**Explanation:**  

- The function attempts to convert a string into an **integer** using `int()`.
- If the conversion fails (due to decimals), it falls back to converting into a **float** using `float()`.  
- This ensures handling of both **integer** and **floating-point** numbers.

</details>

---

###### ` Question 2: Round a Number `  

Write a function `round_number` that rounds a number to the nearest integer or a specified number of decimal places.

`Example:`  

```python
# Input:
3.14159 to 2 decimal places

# Output:
3.14
```

`Topics Covered:`  
Rounding numbers using `round()`.  

**Hints:**  
- [Python round() function](https://docs.python.org/3/library/functions.html#round)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def round_number(num, decimals=0):
    return round(num, decimals)

# Example usage
print(round_number(3.14159))     # Output: 3
print(round_number(3.14159, 2))  # Output: 3.14
```

**Explanation:**  

- `round(number, decimals)` rounds a number to the given **decimal places**.  
- Default decimal places are **0**, meaning it rounds to the nearest **integer**.  

</details>

---

###### ` Question 3: Generate a Random Number in a Range `  

Write a function `generate_random_number` that generates a **random number** between two specified values.

`Example:`  

```python
# Input:
Random number between 1 and 10

# Output:
5 (Example Output)
```

`Topics Covered:`  
Generating random numbers using the `random` module.  

**Hints:**  
- [Python random module](https://docs.python.org/3/library/random.html)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
import random

def generate_random_number(start, end):
    return random.randint(start, end)

# Example usage
print(generate_random_number(1, 10))  # Output: Random integer between 1 and 10
```

**Explanation:**  

- Import the `random` module.
- Use `random.randint(start, end)` to get a **random integer** in the specified range.

</details>

---

###### ` Question 4: Calculate Factorial `  

Write a function `factorial` to find the **factorial** of a number using **both recursion and iteration**.

`Example:`  

```python
# Input:
5

# Output:
120
```

`Topics Covered:`  
Factorial calculation using recursion, iteration, and the `math` module.  

**Hints:**  
- [Python math.factorial() function](https://docs.python.org/3/library/math.html#math.factorial)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

✅ **Solution 1: Using `math.factorial()`**
```python
import math

def factorial_using_math(num):
    return math.factorial(num)

# Example usage
print(factorial_using_math(5))  # Output: 120
```

✅ **Solution 2: Using Iteration**
```python
def factorial_iterative(num):
    result = 1
    for i in range(1, num + 1):
        result *= i
    return result

# Example usage
print(factorial_iterative(5))  # Output: 120
```

✅ **Solution 3: Using Recursion**
```python
def factorial_recursive(num):
    if num == 0 or num == 1:
        return 1
    return num * factorial_recursive(num - 1)

# Example usage
print(factorial_recursive(5))  # Output: 120
```

**Explanation:**  

- **Using `math.factorial(n)`**: Directly computes the factorial.  
- **Using iteration**: Loop from `1` to `n`, multiplying each value.  
- **Using recursion**: The base case is `1`, otherwise, it multiplies `num * factorial(num-1)`.  

</details>

---

###### ` Question 5: Find GCD of Two Numbers `  

Write a function `find_gcd` to compute the **greatest common divisor (GCD)** of two numbers.

`Example:`  

```python
# Input:
54, 24

# Output:
6
```

`Topics Covered:`  
Finding GCD using `math.gcd()` and the Euclidean algorithm.  

**Hints:**  
- [Python math.gcd() function](https://docs.python.org/3/library/math.html#math.gcd)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

✅ **Solution 1: Using `math.gcd()`**
```python
import math

def gcd_using_math(a, b):
    return math.gcd(a, b)

# Example usage
print(gcd_using_math(54, 24))  # Output: 6
```

✅ **Solution 2: Using the Euclidean Algorithm**
```python
def gcd_euclidean(a, b):
    while b != 0:
        a, b = b, a % b
    return a

# Example usage
print(gcd_euclidean(54, 24))  # Output: 6
```

✅ **Solution 3: Using Recursion (Euclidean Algorithm)**
```python
def gcd_recursive(a, b):
    if b == 0:
        return a
    return gcd_recursive(b, a % b)

# Example usage
print(gcd_recursive(54, 24))  # Output: 6
```

**Explanation:**  

- **Using `math.gcd()`**: The simplest approach, using Python’s built-in function.  
- **Using iteration (Euclidean Algorithm)**:  
  - Replace `a` with `b`, and `b` with `a % b`.
  - Repeat until `b == 0`, at which point `a` is the **GCD**.  
- **Using recursion**:  
  - Base case: Return `a` if `b == 0`.  
  - Recursive step: Call `gcd_recursive(b, a % b)`.  

</details>

---
