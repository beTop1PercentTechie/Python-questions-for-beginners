# Conditionals  

---

###### ` Question 16: Check if a Number is Positive, Negative, or Zero `  

Write a function `check_number_type` to determine if a number is **positive, negative, or zero**.

`Example:`  

```python
# Input:
0

# Output:
"Zero"
```

`Topics Covered:`  
Conditional statements (`if-elif-else`).  

**Hints:**  
- [Python if-else statements](https://docs.python.org/3/tutorial/controlflow.html#if-statements)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def check_number_type(num):
    if num > 0:
        return "Positive"
    elif num < 0:
        return "Negative"
    else:
        return "Zero"

# Example usage
print(check_number_type(0))   # Output: Zero
print(check_number_type(5))   # Output: Positive
print(check_number_type(-3))  # Output: Negative
```

**Explanation:**  

- If **num > 0**, return **"Positive"**.  
- If **num < 0**, return **"Negative"**.  
- Otherwise, return **"Zero"**.  

</details>

---

###### ` Question 17: Leap Year Checker `  

Write a function `is_leap_year` to determine if a given year is a **leap year**.

`Example:`  

```python
# Input:
2000

# Output:
True
```

`Topics Covered:`  
Conditional statements, modulo operator.  

**Hints:**  
- [Python modulo operator](https://docs.python.org/3/reference/expressions.html#binary-arithmetic-operations)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def is_leap_year(year):
    if (year % 4 == 0 and year % 100 != 0) or (year % 400 == 0):
        return True
    return False

# Example usage
print(is_leap_year(2000))  # Output: True
print(is_leap_year(1900))  # Output: False
print(is_leap_year(2024))  # Output: True
```

**Explanation:**  

- A leap year must be **divisible by 4**.  
- It must **not be divisible by 100**, except when also **divisible by 400**.  
- The condition `(year % 4 == 0 and year % 100 != 0) or (year % 400 == 0)` checks this.  

</details>

---

###### ` Question 18: Validate Password Strength `  

Write a function `validate_password` to check whether a password is **strong** based on specific conditions.

`Example:`  

```python
# Input:
"Password123!"

# Output:
"Strong"
```

`Topics Covered:`  
Regular expressions (`re` module).  

**Hints:**  
- [Python re module](https://docs.python.org/3/library/re.html)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
import re

def validate_password(password):
    if len(password) < 8:
        return "Weak: Password must be at least 8 characters long."
    if not re.search(r"[A-Z]", password):
        return "Weak: Password must include at least one uppercase letter."
    if not re.search(r"[a-z]", password):
        return "Weak: Password must include at least one lowercase letter."
    if not re.search(r"[0-9]", password):
        return "Weak: Password must include at least one digit."
    if not re.search(r"[!@#$%^&*(),.?\":{}|<>]", password):
        return "Weak: Password must include at least one special character."
    return "Strong"

# Example usage
print(validate_password("Password123!"))  # Output: Strong
print(validate_password("weakpass"))      # Output: Weak: Password must include at least 1 uppercase letter.
```

**Explanation:**  

- **Check password length** (`len(password) < 8`).  
- Use **regex patterns** to check for:  
  - **Uppercase letters** (`[A-Z]`)  
  - **Lowercase letters** (`[a-z]`)  
  - **Digits** (`[0-9]`)  
  - **Special characters** (`[!@#$%^&*(),.?\":{}|<>]`)  

</details>

---

###### ` Question 19: Grade Evaluation `  

Write a function `evaluate_grade` to assign a **grade** based on a numerical score.

`Example:`  

```python
# Input:
85

# Output:
"B"
```

`Topics Covered:`  
Conditional statements (`if-elif-else`).  

**Hints:**  
- [Python if-else statements](https://docs.python.org/3/tutorial/controlflow.html#if-statements)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def evaluate_grade(score):
    if score >= 90:
        return "A"
    elif score >= 80:
        return "B"
    elif score >= 70:
        return "C"
    elif score >= 60:
        return "D"
    else:
        return "F"

# Example usage
print(evaluate_grade(85))  # Output: B
print(evaluate_grade(92))  # Output: A
print(evaluate_grade(58))  # Output: F
```

**Explanation:**  

- **90+** → `"A"`  
- **80-89** → `"B"`  
- **70-79** → `"C"`  
- **60-69** → `"D"`  
- **Below 60** → `"F"`  
- The conditions are checked in **descending order** for correct evaluation.  

</details>

---

###### ` Question 20: Check Voting Eligibility `  

Write a function `check_voting_eligibility` to determine if a person is **eligible to vote** based on their age.

`Example:`  

```python
# Input:
18

# Output:
"Eligible to vote"
```

`Topics Covered:`  
Conditional statements (`if-else`).  

**Hints:**  
- [Python if-else statements](https://docs.python.org/3/tutorial/controlflow.html#if-statements)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def check_voting_eligibility(age):
    if age >= 18:
        return "Eligible to vote"
    else:
        return "Not eligible to vote"

# Example usage
print(check_voting_eligibility(18))  # Output: Eligible to vote
print(check_voting_eligibility(15))  # Output: Not eligible to vote
```

**Explanation:**  

- If **age >= 18**, return `"Eligible to vote"`.  
- Otherwise, return `"Not eligible to vote"`.  

</details>

---

