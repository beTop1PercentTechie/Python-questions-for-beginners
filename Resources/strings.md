# Strings

---

###### ` Question 6: Check for Palindrome `  

Write a function `is_palindrome` to check if a string is a palindrome by comparing it with its reverse.

`Example:`  

```python
# Input:
"madam"

# Output:
True
```

`Topics Covered:`  
String manipulation, slicing  

**Hints:**  
- [Python string slicing](https://docs.python.org/3/library/stdtypes.html#str)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def is_palindrome(s):
    # Compare the string with its reverse
    return s == s[::-1]

# Example usage
print(is_palindrome("madam"))  # Output: True
print(is_palindrome("hello"))  # Output: False
```

**Explanation:**  

- `s[::-1]` creates a **reversed version** of the string `s`.  
- If the **original string** is the **same as its reverse**, it’s a **palindrome**.  

</details>

---

###### ` Question 7: Count Word Occurrences `  

Write a function `count_word_occurrences` to count how many times a word appears in a string.

`Example:`  

```python
# Input:
"hello world hello", "hello"

# Output:
2
```

`Topics Covered:`  
String manipulation, list methods  

**Hints:**  
- [Python string count() method](https://docs.python.org/3/library/stdtypes.html#str.count)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def count_word_occurrences(text, word):
    return text.split().count(word)

# Example usage
print(count_word_occurrences("hello world hello", "hello"))  # Output: 2
```

**Explanation:**  

- `text.split()` splits the **string into a list of words**.  
- `list.count(word)` counts occurrences of the **specified word** in the list.  

</details>

---

###### ` Question 8: Reverse Words in a Sentence `  

Write a function `reverse_words` to reverse the order of words in a sentence while keeping the characters within each word intact.

`Example:`  

```python
# Input:
"Hello World"

# Output:
"World Hello"
```

`Topics Covered:`  
String manipulation, list methods  

**Hints:**  
- [Python string split() method](https://docs.python.org/3/library/stdtypes.html#str.split)  
- [Python string join() method](https://docs.python.org/3/library/stdtypes.html#str.join)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def reverse_words(sentence):
    words = sentence.split()
    reversed_sentence = " ".join(reversed(words))
    return reversed_sentence

# Example usage
print(reverse_words("Hello World"))  # Output: "World Hello"
```

**Explanation:**  

- `sentence.split()` **splits** the sentence into a **list of words**.  
- `reversed(words)` **reverses the order** of the words.  
- `" ".join()` **joins the reversed words** back into a single sentence.  

</details>

---

###### ` Question 9: Validate Email Format `  

Write a function `validate_email` to check if a given string follows a **valid email format**.

`Example:`  

```python
# Input:
"test@example.com"

# Output:
True
```

`Topics Covered:`  
Regular expressions (regex), pattern matching  

**Hints:**  
- [Python re module](https://docs.python.org/3/library/re.html)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
import re

def validate_email(email):
    # Regex pattern for a valid email address
    pattern = r'^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$'
    return re.match(pattern, email) is not None

# Example usage
print(validate_email("test@example.com"))  # Output: True
print(validate_email("invalid-email"))    # Output: False
```

**Explanation:**  

🔹 **Pattern Breakdown:**  
- `^[a-zA-Z0-9._%+-]+` → Start with **letters, digits, or special characters**.  
- `@` → Must contain an **"@" symbol**.  
- `[a-zA-Z0-9.-]+` → Domain name.  
- `\.[a-zA-Z]{2,}$` → **Top-level domain** (TLD) with at least **2 characters**.  
- `re.match()` checks if the **email matches the pattern**.  

</details>

---

###### ` Question 10: Remove Extra Spaces `  

Write a function `remove_extra_spaces` to **remove redundant spaces** in a string.

`Example:`  

```python
# Input:
"   Hello   World  "

# Output:
"Hello World"
```

`Topics Covered:`  
String manipulation, whitespace trimming  

**Hints:**  
- [Python string split() method](https://docs.python.org/3/library/stdtypes.html#str.split)  
- [Python string join() method](https://docs.python.org/3/library/stdtypes.html#str.join)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def remove_extra_spaces(s):
    return " ".join(s.split())

# Example usage
print(remove_extra_spaces("   Hello   World  "))  # Output: "Hello World"
```

**Explanation:**  

- `s.split()` **splits the string into words** while removing excess whitespace.  
- `" ".join()` **joins the words back** into a **single space-separated sentence**.  

</details>

---

