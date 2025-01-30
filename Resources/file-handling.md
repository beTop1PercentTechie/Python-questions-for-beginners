# File Handling  

---

###### ` Question 41: Read and Write a Text File `  

Write a function `read_and_write_file` to **read the contents of a file and write them to another file**.

`Example:`  

```python
# Input:
file1.txt → "Hello, world! This is a test file."

# Output:
file2.txt → "Hello, world! This is a test file."
```

`Topics Covered:`  
Reading and writing files.  

**Hints:**  
- [Python open() function](https://docs.python.org/3/library/functions.html#open)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def read_and_write_file(input_file, output_file):
    with open(input_file, 'r') as file1:  # Open the input file in read mode
        content = file1.read()  # Read the content

    with open(output_file, 'w') as file2:  # Open the output file in write mode
        file2.write(content)  # Write the content to the output file

# Example usage
read_and_write_file('file1.txt', 'file2.txt')
```

**Explanation:**  

- Open the **input file** in read mode (`'r'`) and store its contents.  
- Open the **output file** in write mode (`'w'`) and write the stored content.  

</details>

---

###### ` Question 42: Count Lines, Words, and Characters `  

Write a function `count_lines_words_characters` to **count the number of lines, words, and characters** in a file.

`Example:`  

```python
# Input:
file.txt → "Hello world!\nPython is great.\nLet's count words."

# Output:
Lines: 3, Words: 7, Characters: 41
```

`Topics Covered:`  
File reading, string operations.  

**Hints:**  
- [Python file handling](https://docs.python.org/3/tutorial/inputoutput.html#reading-and-writing-files)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def count_lines_words_characters(file):
    with open(file, 'r') as f:
        lines = 0
        words = 0
        characters = 0

        for line in f:
            lines += 1  # Count lines
            words += len(line.split())  # Count words
            characters += len(line)  # Count characters

    return lines, words, characters

# Example usage
result = count_lines_words_characters('file.txt')
print(f"Lines: {result[0]}, Words: {result[1]}, Characters: {result[2]}")
```

**Explanation:**  

- Read the file line by line.  
- Count lines, words (`split()`), and characters (`len()`).  

</details>

---

###### ` Question 43: Find and Replace Text `  

Write a function `find_and_replace` to **replace specific words in a file**.

`Example:`  

```python
# Input:
file.txt → "Hello world! Welcome to programming."

# Output:
output.txt → "Hi world! Welcome to programming."
```

`Topics Covered:`  
File reading, string replacement.  

**Hints:**  
- [Python str.replace() method](https://docs.python.org/3/library/stdtypes.html#str.replace)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
def find_and_replace(file, old_word, new_word, output_file):
    with open(file, 'r') as f:
        lines = f.readlines()  # Read all lines

    with open(output_file, 'w') as f:
        for line in lines:
            updated_line = line.replace(old_word, new_word)  # Replace words
            f.write(updated_line)  # Write updated content

# Example usage
find_and_replace('file.txt', 'Hello', 'Hi', 'output.txt')

# Verify the output
with open('output.txt', 'r') as file:
    print(file.read())  # Output: "Hi world! Welcome to programming."
```

**Explanation:**  

- Read the file line by line.  
- Use `replace()` to update occurrences of `old_word` with `new_word`.  
- Write the modified content to the new file.  

</details>

---

###### ` Question 44: Log File Analysis `  

Write a function `analyze_log_file` to **parse a log file and summarize errors by type**.

`Example:`  

```python
# Input:
error.log → Contains HTTP error codes like 404, 500, 403.

# Output:
{'404': 4, '500': 3, '403': 2}
```

`Topics Covered:`  
Regex, dictionary operations.  

**Hints:**  
- [Python re module](https://docs.python.org/3/library/re.html)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
import re

def analyze_log_file(log_file):
    error_count = {}  # Dictionary to store error counts
    with open(log_file, 'r') as f:
        for line in f:
            match = re.search(r'\b(\d{3})\b', line)  # Extract 3-digit error code
            if match:
                error_code = match.group(1)
                error_count[error_code] = error_count.get(error_code, 0) + 1

    return error_count

# Example usage
print(analyze_log_file('error.log'))  # Output: {'404': 4, '500': 3, '403': 2}
```

**Explanation:**  

- Use regex (`\b\d{3}\b`) to extract HTTP error codes (like 404, 500, 403).  
- Count occurrences using a dictionary.  

</details>

---

###### ` Question 45: CSV Reader and Writer `  

Write a function `read_and_modify_csv` to **read data from a CSV file, modify it, and write back**.

`Example:`  

```python
# Input:
data.csv → Name,Salary
              Alice,5000
              Bob,6000

# Output:
updated_data.csv → Name,Salary
                     Alice,6000
                     Bob,7000
```

`Topics Covered:`  
CSV file handling, data modification.  

**Hints:**  
- [Python csv module](https://docs.python.org/3/library/csv.html)  

<details>
  <summary>Solution</summary>

### Let's look at the solution:

```python
import csv

def read_and_modify_csv(input_file, output_file):
    with open(input_file, 'r', newline='') as infile:
        reader = csv.reader(infile)  # Read the CSV file
        rows = list(reader)  # Convert to list

    # Modify rows (increment salary if numeric)
    for row in rows:
        if row and row[1].isdigit():  # Assuming column 2 is numeric
            row[1] = str(int(row[1]) + 1000)

    with open(output_file, 'w', newline='') as outfile:
        writer = csv.writer(outfile)  # Write the updated CSV
        writer.writerows(rows)

# Example usage
read_and_modify_csv('data.csv', 'updated_data.csv')

# Verify output
with open('updated_data.csv', 'r') as updated_file:
    print(updated_file.read())
```

**Explanation:**  

- **Reading CSV (`csv.reader`)**: Reads rows from a CSV file.  
- **Modifying Data**: Increments salary if numeric.  
- **Writing CSV (`csv.writer`)**: Writes modified data back to a new file.  

</details>

---
