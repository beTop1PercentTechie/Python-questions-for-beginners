# Operators

---

###### ` Question 11: Calculate Total Price with Tax `  

Write a function `calculate_total_price` to compute the total price after applying a **tax percentage** to a base price.

`Example:`  

```python
# Input:
100, 5

# Output:
105.0
```

`Topics Covered:`  
Arithmetic operators, percentage calculations  

**Hints:**  
- [Python round() function](https://docs.python.org/3/library/functions.html#round)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def calculate_total_price(price, tax_rate):
    total_price = price * (1 + tax_rate / 100)
    return round(total_price, 2)  # Rounded to 2 decimal places

# Example usage
print(calculate_total_price(100, 5))  # Output: 105.0
```

**Explanation:**  

- `tax_rate / 100` converts the **percentage to a decimal**.  
- Multiply `price` by `(1 + tax_rate / 100)` to **apply the tax**.  
- Use `round()` to limit the result to **2 decimal places**.  

</details>

---

###### ` Question 12: Convert Temperature `  

Write functions `fahrenheit_to_celsius` and `celsius_to_fahrenheit` to **convert between Fahrenheit (°F) and Celsius (°C)**.

`Example:`  

```python
# Input:
100°F to Celsius

# Output:
37.78
```

`Topics Covered:`  
Temperature conversion formulas  

**Hints:**  
- [Python arithmetic operators](https://docs.python.org/3/tutorial/introduction.html#numbers)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def fahrenheit_to_celsius(f):
    c = (f - 32) * 5 / 9
    return round(c, 2)

def celsius_to_fahrenheit(c):
    f = c * 9 / 5 + 32
    return round(f, 2)

# Example usage
print(fahrenheit_to_celsius(100))  # Output: 37.78
print(celsius_to_fahrenheit(37.78))  # Output: 100.0
```

**Explanation:**  

- **°C to °F**: Multiply by **9/5** and **add 32**.  
- **°F to °C**: Subtract **32**, then **multiply by 5/9**.  
- `round()` is used for **better readability**.  

</details>

---

###### ` Question 13: Simple Interest Calculation `  

Write a function `calculate_simple_interest` to compute **simple interest** using the standard formula.

`Example:`  

```python
# Input:
Principal = 1000, Rate = 5%, Time = 2 years

# Output:
100.0
```

`Topics Covered:`  
Arithmetic operators, percentage calculations  

**Hints:**  
- [Python arithmetic operators](https://docs.python.org/3/tutorial/introduction.html#numbers)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def calculate_simple_interest(principal, rate, time):
    si = (principal * rate * time) / 100
    return si

# Example usage
print(calculate_simple_interest(1000, 5, 2))  # Output: 100.0
```

**Explanation:**  

- Formula: **SI = (P * R * T) / 100**  
  - **P** → Principal amount  
  - **R** → Rate of interest per year  
  - **T** → Time in years  

</details>

---

###### ` Question 14: Calculate Age `  

Write a function `calculate_age` to **calculate age** based on a given birthdate.

`Example:`  

```python
# Input:
"2000-01-01"

# Output:
23 (if current year is 2023)
```

`Topics Covered:`  
Datetime module, date calculations  

**Hints:**  
- [Python datetime module](https://docs.python.org/3/library/datetime.html)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
from datetime import datetime

def calculate_age(birthdate):
    today = datetime.now()
    birth_date = datetime.strptime(birthdate, "%Y-%m-%d")
    age = today.year - birth_date.year

    # Adjust if the birthday hasn't occurred yet this year
    if (today.month, today.day) < (birth_date.month, birth_date.day):
        age -= 1
    return age

# Example usage
print(calculate_age("2000-01-01"))  # Output: 23 (if current year is 2023)
```

**Explanation:**  

- `datetime.strptime()` converts the **birthdate string** into a **datetime object**.  
- Calculate the **difference in years** between today and the birthdate.  
- **Adjust for birthdays** that haven't occurred yet this year.  

</details>

---

###### ` Question 15: Find Average Speed `  

Write a function `calculate_average_speed` to compute the **average speed** given distance and time.

`Example:`  

```python
# Input:
Distance = 100 km, Time = 2 hours

# Output:
50.0 km/h
```

`Topics Covered:`  
Arithmetic operations, division  

**Hints:**  
- [Python arithmetic operators](https://docs.python.org/3/tutorial/introduction.html#numbers)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def calculate_average_speed(distance, time):
    if time == 0:
        return "Time cannot be zero."
    return round(distance / time, 2)

# Example usage
print(calculate_average_speed(100, 2))  # Output: 50.0
```

**Explanation:**  

- Formula: **Speed = Distance / Time**  
- Handle the case where **time is zero** to **avoid division by zero**.  
- Use `round()` for **better readability**.  

</details>

---