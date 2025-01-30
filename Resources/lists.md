# Lists  

---

###### ` Question 26: Find Max and Min in a List `  

Write a function `find_max_min` to **identify the maximum and minimum values** in a list of numbers.

`Example:`  

```python
# Input:
[4, 7, 1, 9]

# Output:
"Max=9, Min=1"
```

`Topics Covered:`  
List operations, built-in functions.  

**Hints:**  
- [Python max() function](https://docs.python.org/3/library/functions.html#max)  
- [Python min() function](https://docs.python.org/3/library/functions.html#min)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def find_max_min(lst):
    max_value = max(lst)
    min_value = min(lst)
    return f"Max={max_value}, Min={min_value}"

# Example usage
print(find_max_min([4, 7, 1, 9]))  # Output: "Max=9, Min=1"
```

**Explanation:**  

- **`max(lst)`** returns the largest number in the list.  
- **`min(lst)`** returns the smallest number in the list.  
- The result is formatted as a string `"Max=..., Min=..."`.  

</details>

---

###### ` Question 27: Remove Duplicates `  

Write a function `remove_duplicates` to **eliminate duplicate elements** from a list while **preserving the order**.

`Example:`  

```python
# Input:
[1, 2, 2, 3, 3, 4]

# Output:
[1, 2, 3, 4]
```

`Topics Covered:`  
Loops, list operations.  

**Hints:**  
- [Python lists](https://docs.python.org/3/tutorial/datastructures.html#more-on-lists)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def remove_duplicates(lst):
    result = []
    for item in lst:
        if item not in result:
            result.append(item)
    return result

# Example usage
print(remove_duplicates([1, 2, 2, 3, 3, 4]))  # Output: [1, 2, 3, 4]
```

**Explanation:**  

- **Loop through List:** Iterate over the original list.  
- **Check for Duplicates:** If an element **is not already** in `result`, add it.  
- **Preserve Order:** Unlike using `set()`, this method **keeps the original order**.  

</details>

---

###### ` Question 28: Split List into Chunks `  

Write a function `split_into_chunks` to **divide a list into smaller sublists** of a given size.

`Example:`  

```python
# Input:
[1, 2, 3, 4, 5], 2

# Output:
[[1, 2], [3, 4], [5]]
```

`Topics Covered:`  
List slicing, list comprehension.  

**Hints:**  
- [Python list slicing](https://docs.python.org/3/library/stdtypes.html#common-sequence-operations)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def split_into_chunks(lst, size):
    return [lst[i:i + size] for i in range(0, len(lst), size)]

# Example usage
print(split_into_chunks([1, 2, 3, 4, 5], 2))  # Output: [[1, 2], [3, 4], [5]]
```

**Explanation:**  

- **List Comprehension:** Creates sublists by slicing the list at every `size` interval.  
- **Slicing:** `lst[i:i + size]` extracts a chunk of `size`.  
- **Looping Stepwise:** The `range(0, len(lst), size)` ensures proper segmentation.  

</details>

---

###### ` Question 29: Find Common Elements in Two Lists `  

Write a function `find_common_elements` to **identify elements that exist in both lists**.

`Example:`  

```python
# Input:
[1, 2, 3], [2, 3, 4]

# Output:
[2, 3]
```

`Topics Covered:`  
Set operations, list conversions.  

**Hints:**  
- [Python set operations](https://docs.python.org/3/library/stdtypes.html#set-types-set-frozenset)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def find_common_elements(list1, list2):
    return list(set(list1) & set(list2))

# Example usage
print(find_common_elements([1, 2, 3], [2, 3, 4]))  # Output: [2, 3]
```

**Explanation:**  

- **Set Conversion:** Convert both lists into sets.  
- **Set Intersection:** Use `&` operator to find common elements.  
- **Convert Back to List:** The result is returned as a list.  

</details>

---

###### ` Question 30: Sort a List by Custom Criteria `  

Write a function `sort_by_custom_key` to **sort a list of dictionaries based on a specific key**.

`Example:`  

```python
# Input:
[{'age': 30}, {'age': 25}], 'age'

# Output:
[{'age': 25}, {'age': 30}]
```

`Topics Covered:`  
Sorting, lambda functions.  

**Hints:**  
- [Python sorted() function](https://docs.python.org/3/library/functions.html#sorted)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def sort_by_custom_key(lst, key):
    return sorted(lst, key=lambda x: x[key])

# Example usage
print(sort_by_custom_key([{'age': 30}, {'age': 25}], 'age'))  # Output: [{'age': 25}, {'age': 30}]
```

**Explanation:**  

- **`sorted()` Function:** Used to sort a list.  
- **Key Argument:** A lambda function extracts the key's value from each dictionary.  
- **Sorting:** The list is sorted based on the extracted values.  

</details>

---
