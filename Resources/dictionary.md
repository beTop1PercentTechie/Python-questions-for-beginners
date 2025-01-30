# Dictionaries  

---

###### ` Question 31: Word Frequency Counter `  

Write a function `word_frequency` to **count the frequency of each word** in a given text.

`Example:`  

```python
# Input:
"hello world hello"

# Output:
{'hello': 2, 'world': 1}
```

`Topics Covered:`  
String operations, dictionary manipulation.  

**Hints:**  
- [Python split() method](https://docs.python.org/3/library/stdtypes.html#str.split)  
- [Python dictionary get() method](https://docs.python.org/3/library/stdtypes.html#dict.get)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def word_frequency(text):
    words = text.split()
    frequency = {}
    for word in words:
        frequency[word] = frequency.get(word, 0) + 1
    return frequency

# Example usage
print(word_frequency("hello world hello"))  # Output: {'hello': 2, 'world': 1}
```

**Explanation:**  

- **Splitting the Text:** `split()` breaks the text into individual words.  
- **Using `get()` for Counting:** The `get()` method retrieves the current count (defaulting to 0 if not found) and increments it.  
- **Return Dictionary:** The function returns a dictionary mapping words to their frequency.  

</details>

---

###### ` Question 32: Merge Two Dictionaries `  

Write a function `merge_dicts` to **combine two dictionaries** into one, resolving key conflicts.

`Example:`  

```python
# Input:
{'a': 1}, {'b': 2}

# Output:
{'a': 1, 'b': 2}
```

`Topics Covered:`  
Dictionary operations, merging.  

**Hints:**  
- [Python dictionary update() method](https://docs.python.org/3/library/stdtypes.html#dict.update)  
- [Python dictionary unpacking](https://peps.python.org/pep-0448/)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def merge_dicts(dict1, dict2):
    dict1.update(dict2)
    return dict1

# Alternative using dictionary unpacking:
def merge_dicts(dict1, dict2):
    return {**dict1, **dict2}

# Example usage
print(merge_dicts({'a': 1}, {'b': 2}))  # Output: {'a': 1, 'b': 2}
```

**Explanation:**  

- **Using `update()`:** Updates `dict1` with `dict2`'s key-value pairs. Conflicting keys are overwritten.  
- **Using Unpacking `{**dict1, **dict2}`:** Creates a new dictionary by merging both.  

</details>

---

###### ` Question 33: Group Data by Key `  

Write a function `group_by_key` to **group items in a list of dictionaries** based on a common key.

`Example:`  

```python
# Input:
[{'id': 1, 'val': 10}, {'id': 1, 'val': 20}], 'id'

# Output:
{1: [10, 20]}
```

`Topics Covered:`  
Dictionary operations, grouping.  

**Hints:**  
- [Python dictionary setdefault() method](https://docs.python.org/3/library/stdtypes.html#dict.setdefault)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def group_by_key(lst, key):
    result = {}
    for item in lst:
        result.setdefault(item[key], []).append(item['val'])
    return result

# Example usage
print(group_by_key([{'id': 1, 'val': 10}, {'id': 1, 'val': 20}], 'id'))  # Output: {1: [10, 20]}
```

**Explanation:**  

- **Using `setdefault()`:** If `key` is missing in `result`, initialize it with an empty list.  
- **Appending Values:** Append `val` of each dictionary under its corresponding `key`.  

</details>

---

###### ` Question 34: Invert a Dictionary `  

Write a function `invert_dict` to **swap keys and values** in a dictionary.

`Example:`  

```python
# Input:
{'a': 1, 'b': 2}

# Output:
{1: 'a', 2: 'b'}
```

`Topics Covered:`  
Dictionary comprehension, key-value swapping.  

**Hints:**  
- [Python dictionary items() method](https://docs.python.org/3/library/stdtypes.html#dict.items)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def invert_dict(d):
    return {v: k for k, v in d.items()}

# Example usage
print(invert_dict({'a': 1, 'b': 2}))  # Output: {1: 'a', 2: 'b'}
```

**Explanation:**  

- **Dictionary Comprehension:** `{v: k for k, v in d.items()}` iterates over key-value pairs, swapping them.  
- **Return Swapped Dictionary:** The new dictionary has **values as keys** and **keys as values**.  

</details>

---

###### ` Question 35: Nested Dictionary Operations `  

Write a function `update_nested_dict` to **access and update values** in a **nested dictionary**.

`Example:`  

```python
# Input:
{'a': {'b': 2}}, 'a', 'b', 3

# Output:
{'a': {'b': 3}}
```

`Topics Covered:`  
Nested dictionary operations.  

**Hints:**  
- [Python dictionary key access](https://docs.python.org/3/tutorial/datastructures.html#dictionaries)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def update_nested_dict(d, key1, key2, new_value):
    d[key1][key2] = new_value
    return d

# Example usage
print(update_nested_dict({'a': {'b': 2}}, 'a', 'b', 3))  # Output: {'a': {'b': 3}}
```

**Explanation:**  

- **Key Chaining:** Access the nested dictionary using `d[key1][key2]`.  
- **Update Value:** Assign `new_value` to `key2`.  

</details>

---

