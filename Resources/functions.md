# Functions  

---

###### ` Question 46: Decorator for Logging Execution Time `  

Write a **decorator** `log_execution_time` to **measure and log the execution time** of a function.  

`Example:`  

```python
# Input:
factorial(5)

# Output:
Execution time of factorial: 0.0000 seconds
```

`Topics Covered:`  
Decorators, function timing.  

**Hints:**  
- [Python time module](https://docs.python.org/3/library/time.html)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
import time

def log_execution_time(func):
    def wrapper(*args, **kwargs):
        start_time = time.time()  # Record start time
        result = func(*args, **kwargs)  # Call the function
        end_time = time.time()  # Record end time
        execution_time = end_time - start_time  # Calculate execution time
        print(f"Execution time of {func.__name__}: {execution_time:.4f} seconds")
        return result
    return wrapper

# Example usage:
@log_execution_time
def factorial(n):
    if n == 1:
        return 1
    return n * factorial(n-1)

# Test the decorator
factorial(5)
```

**Explanation:**  

- The **decorator** logs the start and end times of the function execution.  
- The **execution time** is displayed after the function completes.  

</details>

---

###### ` Question 47: Lambda for Filtering Data `  

Write a **lambda function** to **filter even numbers** from a list.  

`Example:`  

```python
# Input:
numbers = [1, 2, 3, 4]

# Output:
[2, 4]
```

`Topics Covered:`  
Lambda functions, filter().  

**Hints:**  
- [Python filter() function](https://docs.python.org/3/library/functions.html#filter)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
# Using lambda and filter to get even numbers
numbers = [1, 2, 3, 4]
even_numbers = list(filter(lambda x: x % 2 == 0, numbers))  # Filter even numbers
print(even_numbers)  # Output: [2, 4]
```

**Explanation:**  

- **Lambda function** (`lambda x: x % 2 == 0`) checks if each number is even.  
- **filter()** applies this lambda function and returns even numbers.  

</details>

---

###### ` Question 48: Recursive Factorial Function `  

Write a **recursive function** `factorial` to compute **factorial of a number**.  

`Example:`  

```python
# Input:
factorial(5)

# Output:
120
```

`Topics Covered:`  
Recursion, factorial calculation.  

**Hints:**  
- [Python recursion](https://docs.python.org/3/tutorial/controlflow.html#defining-functions)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def factorial(n):
    if n == 1:
        return 1
    return n * factorial(n-1)  # Recursive call

# Example usage:
print(factorial(5))  # Output: 120
```

**Explanation:**  

- The function **calls itself recursively** with `n-1` until it reaches `1`.  
- The recursion **"unwinds"** and multiplies all numbers.  

</details>

---

###### ` Question 49: Map and Reduce Examples `  

Write functions using **map()** to square numbers and **reduce()** to sum them.  

`Example:`  

```python
# Input:
numbers = [1, 2, 3]

# Output:
14
```

`Topics Covered:`  
Higher-order functions, map(), reduce().  

**Hints:**  
- [Python map() function](https://docs.python.org/3/library/functions.html#map)  
- [Python reduce() function](https://docs.python.org/3/library/functools.html#functools.reduce)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
from functools import reduce

# List of numbers
numbers = [1, 2, 3]

# Use map to square each number
squared_numbers = list(map(lambda x: x ** 2, numbers))

# Use reduce to sum the squared numbers
sum_of_squares = reduce(lambda x, y: x + y, squared_numbers)
print(sum_of_squares)  # Output: 14
```

**Explanation:**  

- **map()** applies a lambda function to square each element.  
- **reduce()** sums all squared numbers.  

</details>

---

###### ` Question 50: Generate Random Password `  

Write a function `generate_random_password` to **generate a random password** of specified length.  

`Example:`  

```python
# Input:
generate_random_password(8)

# Output:
"aB3#d2Fg" (random example)
```

`Topics Covered:`  
Random module, password generation.  

**Hints:**  
- [Python random module](https://docs.python.org/3/library/random.html)  
- [Python string module](https://docs.python.org/3/library/string.html)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
import random
import string

def generate_random_password(length=8):
    # Define character sets for password complexity
    characters = string.ascii_letters + string.digits + string.punctuation
    # Randomly select characters from the defined set
    password = ''.join(random.choice(characters) for _ in range(length))
    return password

# Example usage:
print(generate_random_password(8))  # Output: "aB3#d2Fg" (example)
```

**Explanation:**  

- `string.ascii_letters` → Contains all lowercase and uppercase letters.  
- `string.digits` → Contains all numeric digits.  
- `string.punctuation` → Contains special characters.  
- `random.choice()` → Picks a random character for each position in the password.  

</details>

---
