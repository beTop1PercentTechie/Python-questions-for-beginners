# Sets  

---

###### ` Question 36: Union and Intersection of Sets `  

Write a function `set_operations` to **compute the union and intersection** of two sets.

`Example:`  

```python
# Input:
{1, 2}, {2, 3}

# Output:
Union={1, 2, 3}, Intersection={2}
```

`Topics Covered:`  
Set operations, union, intersection.  

**Hints:**  
- [Python set union() method](https://docs.python.org/3/library/stdtypes.html#set.union)  
- [Python set intersection() method](https://docs.python.org/3/library/stdtypes.html#set.intersection)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def set_operations(set1, set2):
    union = set1 | set2  # Union using the | operator
    intersection = set1 & set2  # Intersection using the & operator
    return union, intersection

# Example usage
print(set_operations({1, 2}, {2, 3}))  # Output: ({1, 2, 3}, {2})
```

**Explanation:**  

- **Union (`|` operator):** Combines elements from both sets, removing duplicates.  
- **Intersection (`&` operator):** Returns only the common elements between the two sets.  

</details>

---

###### ` Question 37: Check Subset and Superset `  

Write a function `check_subset_superset` to **verify if one set is a subset or superset** of another.

`Example:`  

```python
# Input:
{1, 2}, {1}

# Output:
(False, True)  # Set1 is not a subset, but it is a superset.
```

`Topics Covered:`  
Subset, superset operations.  

**Hints:**  
- [Python set issubset() method](https://docs.python.org/3/library/stdtypes.html#set.issubset)  
- [Python set issuperset() method](https://docs.python.org/3/library/stdtypes.html#set.issuperset)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def check_subset_superset(set1, set2):
    is_subset = set1.issubset(set2)  # Check if set1 is a subset of set2
    is_superset = set1.issuperset(set2)  # Check if set1 is a superset of set2
    return is_subset, is_superset

# Example usage
print(check_subset_superset({1, 2}, {1}))  # Output: (False, True)
```

**Explanation:**  

- **Subset (`issubset()`):** Returns `True` if all elements of `set1` exist in `set2`.  
- **Superset (`issuperset()`):** Returns `True` if `set1` contains all elements of `set2`.  

</details>

---

###### ` Question 38: Find Symmetric Difference `  

Write a function `symmetric_difference` to **compute the symmetric difference** between two sets.

`Example:`  

```python
# Input:
{1, 2}, {2, 3}

# Output:
{1, 3}
```

`Topics Covered:`  
Set operations, symmetric difference.  

**Hints:**  
- [Python set symmetric_difference() method](https://docs.python.org/3/library/stdtypes.html#set.symmetric_difference)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def symmetric_difference(set1, set2):
    return set1 ^ set2  # Symmetric difference using ^ operator

# Example usage
print(symmetric_difference({1, 2}, {2, 3}))  # Output: {1, 3}
```

**Explanation:**  

- **Symmetric Difference (`^` operator):** Returns elements present in either set, but not in both.  

</details>

---

###### ` Question 39: Remove Elements from a Set `  

Write a function `remove_elements` to **remove multiple elements** from a set.  
Write another function `remove_element` to **remove a single element** safely.

`Example:`  

```python
# Input:
({1, 2, 3}, {2})

# Output:
{1, 3}
```

`Topics Covered:`  
Set modification, element removal.  

**Hints:**  
- [Python set difference_update() method](https://docs.python.org/3/library/stdtypes.html#set.difference_update)  
- [Python set discard() method](https://docs.python.org/3/library/stdtypes.html#set.discard)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def remove_elements(set1, elements_to_remove):
    set1.difference_update(elements_to_remove)  # Remove multiple elements
    return set1

def remove_element(set1, element):
    set1.discard(element)  # Remove a single element safely
    return set1

# Example usage
print(remove_elements({1, 2, 3}, {2}))  # Output: {1, 3}
print(remove_element({1, 2, 3}, 2))  # Output: {1, 3}
```

**Explanation:**  

- **`difference_update()`:** Removes all specified elements from `set1`.  
- **`discard()`:** Removes a single element if present; does nothing if the element is missing.  

</details>

---

###### ` Question 40: Convert Set to List `  

Write a function `set_to_sorted_list` to **convert a set into a sorted list**.

`Example:`  

```python
# Input:
{3, 1, 2}

# Output:
[1, 2, 3]
```

`Topics Covered:`  
Set to list conversion, sorting.  

**Hints:**  
- [Python sorted() function](https://docs.python.org/3/library/functions.html#sorted)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def set_to_sorted_list(set1):
    return sorted(set1)  # Convert the set to a sorted list

# Example usage
print(set_to_sorted_list({3, 1, 2}))  # Output: [1, 2, 3]
```

**Explanation:**  

- **`sorted()` function:** Converts the set into a sorted list.  

</details>

---

