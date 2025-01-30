# Loops  

---

###### ` Question 21: Fibonacci Sequence `  

Write a function `fibonacci_sequence` to generate the first `n` numbers in the Fibonacci sequence.  
The Fibonacci sequence starts with **0** and **1**, and each subsequent number is the **sum of the two preceding ones**.

`Example:`  

```python
# Input:
6

# Output:
[0, 1, 1, 2, 3, 5]
```

`Topics Covered:`  
Loops, list manipulation.  

**Hints:**  
- [Python range() function](https://docs.python.org/3/library/functions.html#func-range)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def fibonacci_sequence(n):
    if n <= 0:
        return []
    if n == 1:
        return [0]
    
    fib_sequence = [0, 1]
    for _ in range(2, n):
        fib_sequence.append(fib_sequence[-1] + fib_sequence[-2])
    
    return fib_sequence

# Example usage
print(fibonacci_sequence(6))  # Output: [0, 1, 1, 2, 3, 5]
```

**Explanation:**  

- **Edge Cases:** If `n` is **0** or negative, return an **empty list**. If `n` is **1**, return **[0]**.  
- **Starting Sequence:** We initialize the sequence with **[0, 1]**.  
- **Loop:** We loop **from index 2 to n-1**, calculating the next number as the **sum of the last two numbers**.  

</details>

---

###### ` Question 22: Multiplication Table `  

Write a function `multiplication_table` to generate a **multiplication table** for a given number.

`Example:`  

```python
# Input:
5

# Output:
"5 x 1 = 5"
"5 x 2 = 10"
...
"5 x 10 = 50"
```

`Topics Covered:`  
Loops, string formatting.  

**Hints:**  
- [Python f-strings](https://docs.python.org/3/reference/lexical_analysis.html#f-strings)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def multiplication_table(number):
    for i in range(1, 11):
        print(f"{number} x {i} = {number * i}")

# Example usage
multiplication_table(5)
```

**Explanation:**  

- **Loop:** Iterate from **1 to 10**.  
- **Multiplication:** Multiply the given number by `i`.  
- **Output Formatting:** Print in the format `"number x i = result"`.  

</details>

---

###### ` Question 23: Count Frequency of Elements `  

Write a function `count_frequency` to count how many times each element appears in a list.

`Example:`  

```python
# Input:
[1, 2, 2, 3, 3, 3, 4, 4, 4, 4]

# Output:
{1: 1, 2: 2, 3: 3, 4: 4}
```

`Topics Covered:`  
Dictionaries, loops.  

**Hints:**  
- [Python dictionary get() method](https://docs.python.org/3/library/stdtypes.html#dict.get)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def count_frequency(lst):
    frequency = {}
    for item in lst:
        frequency[item] = frequency.get(item, 0) + 1
    return frequency

# Example usage
print(count_frequency([1, 2, 2, 3, 3, 3, 4, 4, 4, 4]))  
# Output: {1: 1, 2: 2, 3: 3, 4: 4}
```

**Explanation:**  

- **Dictionary Initialization:** Create an empty dictionary `frequency`.  
- **Loop through List:** For each element, use `get(item, 0) + 1` to **increment the count**.  
- **Return Dictionary:** The dictionary stores **each element as a key** and its **count as a value**.  

</details>

---

###### ` Question 24: Find Prime Numbers in a Range `  

Write a function `find_primes` to **identify all prime numbers** in a given range.

`Example:`  

```python
# Input:
10, 30

# Output:
[11, 13, 17, 19, 23, 29]
```

`Topics Covered:`  
Loops, conditional checks, optimization with square root.  

**Hints:**  
- [Python range() function](https://docs.python.org/3/library/functions.html#func-range)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def find_primes(start, end):
    primes = []
    for num in range(start, end + 1):
        if num > 1:
            for i in range(2, int(num ** 0.5) + 1):
                if num % i == 0:
                    break
            else:
                primes.append(num)
    return primes

# Example usage
print(find_primes(10, 30))
# Output: [11, 13, 17, 19, 23, 29]
```

**Explanation:**  

- **Outer Loop:** Iterate through the range **start to end**.  
- **Inner Loop:** Check divisibility **only up to the square root** of the number.  
- **Prime Check:** If **no divisors are found**, append to the `primes` list.  

</details>

---

###### ` Question 25: Simulate a Countdown Timer `  

Write a function `countdown_timer` to create a **countdown timer** that displays remaining time in seconds.

`Example:`  

```python
# Input:
5

# Output:
5
4
3
2
1
"Time's up!"
```

`Topics Covered:`  
Loops, `time.sleep()` for delays.  

**Hints:**  
- [Python time module](https://docs.python.org/3/library/time.html)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
import time

def countdown_timer(seconds):
    while seconds > 0:
        print(seconds)
        time.sleep(1)
        seconds -= 1
    print("Time's up!")

# Example usage
countdown_timer(5)
```

**Explanation:**  

- **While Loop:** Continue countdown until `seconds` reaches **0**.  
- **Print and Delay:** Print the current value and **pause for 1 second** using `time.sleep(1)`.  
- **Decrement Countdown:** Reduce `seconds` by **1** each loop iteration.  
- **Completion Message:** Print `"Time's up!"` when countdown finishes.  

</details>

---