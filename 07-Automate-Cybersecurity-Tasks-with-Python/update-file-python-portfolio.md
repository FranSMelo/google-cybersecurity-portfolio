# Algorithm for File Updates in Python

## Project Description

As a security professional working at a healthcare company, maintaining strict control over network access is vital to protecting sensitive patient records and complying with health privacy standards. Access to restricted subnetworks containing personal medical data is restricted based on employee IP addresses.

The organization maintains an allow list of IP addresses authorized to log into these systems. However, as employees change roles or leave the team, their access permissions must be revoked.

The goal of this project was to develop an automated Python algorithm that reads an existing allow list file (`allow_list.txt`), parses its contents into an actionable data structure, cross-references it against a removal list (`remove_list`), removes any unauthorized IP addresses, and updates the file with the revised allow list.

## Open the File That Contains the Allow List

To begin the algorithm, the target file containing the permitted IP addresses must be opened in Python. The file path is assigned to a string variable named `import_file`. Using the `with` statement alongside the `open()` function allows the file to be opened safely in read mode (`"r"`), ensuring that system resources are properly managed and closed automatically after execution.

```python
# Assign the file name to a variable
import_file = "allow_list.txt"

# Open the file in read mode using a context manager
with open(import_file, "r") as file:
```

### Syntax, Functions, and Keywords

* **`import_file = "allow_list.txt"`**: Creates a string variable storing the target filename.
* **`with`**: A context manager keyword that automatically handles file opening and closing operations, preventing memory leaks or file corruption.
* **`open()`**: A built-in Python function that opens files. It takes two parameters: the file variable (`import_file`) and the mode (`"r"` for read-only).
* **`as file`**: Assigns the opened file object to a reference variable named `file` for use within the indented block.

## Read the File Contents

Once the file object is created, its contents are extracted into a single continuous string format using the `.read()` method. This string is stored in a new variable named `ip_addresses`.

```python
    # Read file contents into a string
    ip_addresses = file.read()
```

### Syntax, Functions, and Keywords

* **`ip_addresses`**: A variable created to hold the raw text contents extracted from the file.
* **`file`**: The file object reference variable established during the file opening stage.
* **`.read()`**: A built-in file object method that converts the unformatted stream of text inside the open file into a single string.

## Convert the String Into a List

Because string data cannot easily be modified element-by-element to remove specific IP addresses, the `ip_addresses` string is converted into a list structure. The `.split()` method breaks down the string based on default whitespace delimiters (spaces and newlines), producing an indexed list of individual IP address elements.

```python
# Convert string of IP addresses into a list
ip_addresses = ip_addresses.split()
```

### Syntax, Functions, and Keywords

* **`ip_addresses = ...`**: Reassigns the `ip_addresses` variable so that it now holds a Python list instead of a string.
* **`.split()`**: A built-in string method that splits text into individual list elements based on whitespace or newline characters (`\n`).

## Iterate Through the Remove List

A second list, `remove_list`, contains all the IP addresses that must be removed from the allow list. A `for` loop is declared to iterate through each item in `remove_list`, assigning the current IP address to the loop variable `element` during each pass.

```python
# Define the list of IP addresses to remove
remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]

# Loop through each IP address in the remove list
for element in remove_list:
```

### Syntax, Functions, and Keywords

* **`remove_list`**: A list containing the specific IP addresses flagged for access revocation.
* **`for`**: A control flow keyword used to construct an iterative loop.
* **`element`**: A temporary loop variable that holds the current IP address from `remove_list` during the iteration cycle.
* **`in`**: A membership keyword linking the loop variable `element` to the target sequence `remove_list`.

## Remove IP Addresses That Are on the Remove List

Inside the body of the `for` loop, a conditional statement (`if`) evaluates whether the current `element` (IP address) exists within the `ip_addresses` allow list. If present, the `.remove()` method is called on `ip_addresses` to delete that specific IP.

*Note: Applying the `.remove()` method directly in this manner is safe and effective because there are no duplicate entries inside the `ip_addresses` list.*

```python
    # Check if the IP address is in the allow list
    if element in ip_addresses:
        # Remove the IP address from the allow list
        ip_addresses.remove(element)
```

### Syntax, Functions, and Keywords

* **`if`**: A conditional statement keyword that evaluates whether an expression returns `True`.
* **`element in ip_addresses`**: A membership evaluation returning `True` if the loop variable `element` is found inside the `ip_addresses` list.
* **`.remove()`**: A built-in list method that removes the first matching instance of a value from a list.

## Update the File With the Revised List of IP Addresses

To write the updated IP addresses back to `allow_list.txt`, the list structure must first be converted back into a formatted string. The `.join()` method combines the list elements using a newline character (`"\n"`) as a delimiter so that each IP address sits on its own line.

Next, a second `with` statement opens `allow_list.txt` in write mode (`"w"`). Applying the `.write()` method overwrites the previous contents of the file with the updated string.

```python
# Convert the list back into a single string separated by newlines
ip_addresses = "\n".join(ip_addresses)

# Open the file in write mode and update its contents
with open(import_file, "w") as file:
    file.write(ip_addresses)
```

### Syntax, Functions, and Keywords

* **`"\n"`**: An escape character representing a line break (newline).
* **`.join()`**: A string method that concatenates list items into a single string, inserting the specified separator (`"\n"`) between each item.
* **`"w"`**: The write mode argument passed to `open()`, which empties existing file contents and writes new data.
* **`.write()`**: A file object method that writes string data into an open file stream.

---

## Complete Python Script

Here is the complete Python algorithm combining all steps:

```python
# Assign file name to a variable
import_file = "allow_list.txt"

# Assign list of IP addresses to remove
remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]

# Read allow_list.txt and store contents
with open(import_file, "r") as file:
    ip_addresses = file.read()

# Convert string to list structure
ip_addresses = ip_addresses.split()

# Iterate through remove_list and strip matching IPs from ip_addresses
for element in remove_list:
    if element in ip_addresses:
        ip_addresses.remove(element)

# Convert list back to string with newline formatting
ip_addresses = "\n".join(ip_addresses)

# Overwrite file with updated allow list
with open(import_file, "w") as file:
    file.write(ip_addresses)
```

---

## Summary

This Python algorithm automates the management of restricted access files by reading, parsing, filtering, and updating an network allow list (`allow_list.txt`). Using built-in functions such as `open()` within context managers (`with`), raw data is extracted with `.read()` and converted into an actionable list using `.split()`. Iterative logic (`for` loops) and conditionals (`if`) cross-reference access lists to systematically purge unauthorized IPs using `.remove()`. Finally, the algorithm formats the revised list back into a string with `.join()` and overwrites the target file using `.write()`. This automated process reduces human error, guarantees access revocation consistency, and helps safeguard sensitive organizational infrastructure.
