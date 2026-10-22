# 📚 Introduction to Python

## 🐍 Introduction to Python and Programming Fundamentals

### 📌 Core Concepts & Mechanics

* **Programming:** The process of writing human-readable instructions that are translated into machine code (binary digits: `0`s and `1`s) for execution by a computer's CPU.
* **Python Language:** A versatile, high-level, general-purpose programming language known for concise syntax, readability, and broad applicability across web development, data analysis, and automation.
* **The Python Interpreter:** A specialized program that translates Python source code into executable computer instructions line by line during runtime.
* **Python Versions:** Emphasizes using **Python 3**, as syntax rules and library support differ significantly from legacy major versions (such as Python 2).

### ⚙️ Python Applications in Cybersecurity

In cybersecurity operations, Python is predominantly leveraged for **automation**—reducing manual effort, eliminating human error, and streamlining repetitive, high-volume operational tasks.

| Security Domain               | Automated Python Application / Task                                                                              |
| :---------------------------- | :--------------------------------------------------------------------------------------------------------------- |
| **Log Analysis**        | Parsing large volumes of SIEM and system logs to flag anomalies, errors, or Indicators of Compromise (IoCs).     |
| **Malware Analysis**    | Automating static file inspections, hash lookups, and dynamic behavioral analysis of suspicious binaries.        |
| **Access Control**      | Programmatically auditing, generating, and updating Access Control Lists (ACLs) and user permission matrices.    |
| **Intrusion Detection** | Scripting alert triage workflows and correlating threat telemetry across IDS/IPS sensor feeds.                   |
| **Compliance Checks**   | Running continuous automated scripts to audit infrastructure against baseline security policies and regulations. |
| **Network Scanning**    | Automating port discovery, socket connections, and vulnerability probing using networking libraries.             |

### 💻 Python Development Environments & Tooling

* **Python Runtime Environments:** Python code can be authored, executed, and documented across multiple distinct execution interfaces based on operational needs.
* **Primary Interfaces:** Interactive **Notebooks**, feature-rich **Integrated Development Environments (IDEs)**, and text-based **Command-Line Interfaces (CLIs)**.

#### 🛠️ Comparison of Python Execution Environments

| Environment                                                 | Primary Characteristics & Structure                                                                                                                                           | Best Operational Use Case                                                                                     |
| :---------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------ |
| **Interactive Notebooks** *(Jupyter, Google Colab)* | Web-based interfaces utilizing **Code Cells** (for executing code and rendering live output) and **Markdown Cells** (for technical documentation and formatting). | Data analysis, security research, interactive prototyping, and step-by-step investigative workflows.          |
| **Integrated Development Environments (IDEs)**        | GUI software applications offering robust source-code editing, syntax highlighting, integrated debugging, and automated error-checking tools.                                 | Developing scalable security applications, building automation scripts, and maintaining large codebases.      |
| **Command-Line Interface (CLI)**                      | Text-based terminal interface executing standalone Python scripts (`.py`) or interactive REPL sessions via shell commands.                                                  | Automating headless security tools, executing scheduled cron jobs, and running fast terminal-based utilities. |

### 📊 Python Data Types & Core Structures

* **Data Types:** Classifications that specify which type of value a variable holds and what operations can be performed on it.
* **Dynamic Typing:** Python automatically determines data types at runtime, eliminating the need for explicit variable declaration.

#### 🔢 Fundamental Python Data Types

| Data Type                    | Description & Syntax Example                                                             | Cybersecurity Application / Use Case                                      |
| :--------------------------- | :--------------------------------------------------------------------------------------- | :------------------------------------------------------------------------ |
| **Integer (`int`)**  | Whole numbers without a fractional component (e.g., `port = 443`).                     | Representing network port numbers, packet counts, and retry limits.       |
| **Float (`float`)**  | Numbers containing a decimal point or fractional precision (e.g., `cvss_score = 9.8`). | Storing risk metrics, CVSS vulnerability scores, and execution timings.   |
| **String (`str`)**   | Textual data enclosed in single or double quotes (e.g., `ip_addr = "192.168.1.1"`).    | Storing IP addresses, hostnames, file paths, hashes, and log strings.     |
| **Boolean (`bool`)** | Binary truth values evaluated as `True` or `False` (e.g., `is_malicious = True`).  | Representing operational flags, conditional states, and alert thresholds. |

#### 📦 Complex Data Structures & Collections

* **Lists (`list`):** Ordered, mutable collections enclosed in square brackets `[]` (e.g., `watchlist = ["10.0.0.1", "10.0.0.2"]`). Used for storing sequential items and iterables.
* **Dictionaries (`dict`):** Key-value pairs enclosed in curly brackets `{}` (e.g., `log_entry = {"status": "fail", "code": 403}`). Directly mirrors JSON-formatted log structures.
* **Tuples (`tuple`):** Ordered, immutable collections enclosed in parentheses `()`. Used for fixed sets of data that should not change during execution.
* **Sets (`set`):** Unordered collections of unique elements enclosed in `{}`. Ideal for de-duplicating IP addresses and matching unique Indicators of Compromise (IoCs).

### 📦 Python Variables and Conditional Statements

#### 📌 Variables: Definition and Assignment

* **Variable:** A symbolic name associated with a specific value stored in computer memory, allowing scripts to reference, modify, and process data dynamically.
* **Assignment Operator (`=`):** Used to bind a value to a variable name (e.g., `alert_status = "critical"` or `port_number = 443`).
* **Naming Conventions:** Variable names should be descriptive, lowercase, and use underscores to separate words (snake_case), making code self-documenting for security automation tasks (e.g., `failed_login_count`, `source_ip_address`).

### 🔀 Conditional Statements & Control Flow

Conditional statements enable scripts to execute different blocks of code based on whether a specific logical condition evaluates to `True` or `False`. This programmatic logic is essential for automating alert triage, filtering malicious traffic, and making decisions during security workflows.

#### 1. Comparison & Logical Operators

Conditions rely on operators to evaluate data states:

* **Comparison Operators:** Equal (`==`), Not Equal (`!=`), Greater Than (`>`), Less Than (`<`), Greater than or equal (`>=`), Less than or equal (`<=`).
* **Logical Operators:** Combine multiple conditions using `and`, `or`, and `not`.

#### 2. Control Flow Structure (`if`, `elif`, `else`)

* **`if`:** Evaluates an initial condition. If `True`, executes the indented block.
* **`elif` (Else If):** Evaluates alternative conditions sequentially if previous checks fail.
* **`else`:** Acts as a catch-all fallback block executed if all preceding conditions evaluate to `False`.

### 🛡️ Practical Cybersecurity Application Example

The following Python snippet demonstrates how variables and conditional statements are used to triage incoming log severity scores:

```python
# Define variables representing a security event telemetry
event_id = 4625
severity_score = 8.5
is_external_ip = True

# Conditional logic for automated incident triage
if severity_score >= 9.0:
    action = "Immediate Escalation to Tier 2 SOC & Isolate Host"
elif severity_score >= 7.0 and is_external_ip:
    action = "High Priority Alert: Trigger Automated Forensics and Notify Analyst"
elif severity_score >= 4.0:
    action = "Medium Priority: Log and Monitor for Persistence"
else:
    action = "Low Priority: Informational Event (Benign)"

print("Triage Verdict:", action)
```

## 🔄 Python Loops: Iterating with `for` and `while`

* **Loops:** Programming constructs used to execute a block of code repeatedly based on a sequence of items or a specific condition.
* **Cybersecurity Utility:** Loops automate high-volume repetitive tasks—such as iterating over lists of IP addresses, parsing multi-line SIEM logs, scanning active network ports, and processing batches of Indicator of Compromise (IoC) records.

### 🔁 `for` Loops: Iterating Over Sequences

A `for` loop iterates over a sequence (such as a list, string, range, or dictionary) and executes a block of code once for each element.

#### Common Use Cases

* Iterating through known collections (e.g., a list of blocked IP addresses or parsed log lines).
* Running a task a fixed number of times using `range()`.

#### Syntax & Example: Iterating Through an IP Blocklist

```python
# List of target IP addresses from a firewall log
target_ips = ["192.168.1.10", "10.0.0.5", "172.16.0.22", "192.168.1.50"]
ip_blocklist = ["10.0.0.5", "192.168.1.50"]

# Iterate over each IP address and evaluate against the blocklist
for ip in target_ips:
    if ip in ip_blocklist:
        print(f"[ALERT] Connection attempt from blocked IP: {ip}")
    else:
        print(f"[INFO] Connection allowed for IP: {ip}")
```

### ⏳ `while` Loops: Conditional Execution

A `while` loop continuously executes a code block as long as a specified logical condition remains `True`.

#### Common Use Cases

* Continuous monitoring scripts (e.g., tailing a log file or checking an API status).
* Processing tasks until a termination signal or threshold is reached (e.g., retrying a failed network socket connection).

#### Syntax & Example: Simulating Automated Connection Retries

```python
# Simulating continuous connection attempts to a SIEM endpoint
max_retries = 3
retry_count = 0
connection_successful = False

while retry_count < max_retries and not connection_successful:
    retry_count += 1
    print(f"[RETRY {retry_count}] Attempting connection to remote SIEM...")

    # Simulate success on 3rd try
    if retry_count == 3:
        connection_successful = True
        print("[SUCCESS] Connected to SIEM successfully.")

if not connection_successful:
    print("[ERROR] Failed to establish connection after maximum retries.")
```

---

### 🛑 Loop Control Statements (`break` and `continue`)

Control statements alter the default flow of loop execution:

| Statement              | Operational Effect                                                                       | Practical Security Example                                                           |
| :--------------------- | :--------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------- |
| **`break`**    | Immediately terminates the loop and moves execution to the statement following the loop. | Stopping a log search as soon as a critical malicious signature match is identified. |
| **`continue`** | Skips the remainder of the current iteration and jumps directly to the next iteration.   | Bypassing benign or empty log entries during a forensic parsing routine.             |

---

---

# 📚 Write effective Python Code

## 🛠️ Python Functions in Cybersecurity

* **Functions:** Reusable blocks of code designed to perform specific, isolated tasks.
* **Cybersecurity Utility:** Functions eliminate code redundancy by automating repeatable workflows—such as parsing multiple log files for failed logins, checking IP blocklists, or validating file hashes across diverse systems.
* **Modularity:** Breaking complex security automation scripts into modular functions improves readability, debugging efficiency, and maintenance.

### 📝 Defining and Structuring Functions

Python utilizes both **built-in functions** (e.g., `print()`, `len()`) and **user-defined functions** tailored to custom operational requirements.

#### 1. Function Components

* **Function Header:** Initiated with the `def` keyword, followed by the unique function name, parentheses `()`, and a colon `:` (e.g., `def display_investigation_message():`).
* **Function Body:** An indented block of code immediately following the header that defines the operational logic executed when the function runs.

#### 2. Code Example: Custom Security Function

```python
# User-defined function to alert analysts on suspicious activity
def display_investigation_message(log_type, alert_status):
    if alert_status == "critical":
        print(f"[ALERT] Investigate activity: {log_type} log indicates potential breach.")
    else:
        print(f"[INFO] Routine check: {log_type} log appears normal.")

# Calling the function with parameters
display_investigation_message("Authentication", "critical")
display_investigation_message("Firewall", "normal")
```

### 📞 Calling Functions & Execution Flow

* **Calling a Function:** Executing a defined function by writing its name followed by parentheses (`function_name()`).
* **Placement:** Functions can be invoked multiple times across different parts of a script, including inside conditional statements (`if`/`else`) and looping blocks (`for`/`while`).

### ⚠️ Common Pitfalls: Infinite Recursion

* **Definition:** An infinite loop occurs when a function calls itself inside its own body without a termination condition (base case).
* **Risk:** This triggers continuous execution until memory or stack limits are exhausted (e.g.,`def func1(): func1()`), causing script crashes. Always ensure recursive or self-referential calls include explicit exit criteria.

## 🔧 Python Functions: Parameters, Returns, and Variable Scope

* **Functions with Inputs & Outputs:** Expanding modular code by passing parameters, returning computed data via `return` statements, and managing variable lifespan across different execution scopes.
* **Variable Scope:** The boundary within a program where a variable is recognized, accessed, or modified. Understanding scope prevents unintended side effects during security automation scripting.

### 📥 Parameters vs. Arguments

When passing data into functions, it is critical to distinguish between the variable placeholder defined in the function and the actual data supplied during execution.

| Term                | Definition & Role                                                                                            | Example Context                                                                                 |
| :------------------ | :----------------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------- |
| **Parameter** | A variable identifier listed inside a function's definition header. Acts as a placeholder for incoming data. | `def analyze_logs(log_file, threshold):` (*`log_file` and `threshold` are parameters*). |
| **Argument**  | The actual data (values or variables) passed into a function when it is invoked or called.                   | `analyze_logs("auth.log", 5)` (*`"auth.log"` and `5` are arguments*).                   |

### 📤 Return Statements and Control Flow

* **The `return` Keyword:** Used to output data computed within a function back to the main program so it can be stored in variables, evaluated in conditionals, or passed to other functions. *(Note: `return` is a keyword, not a function; do not use parentheses with it).*
* **Execution Termination:** When Python encounters a `return` statement, it executes it and **immediately exits the function**, terminating any subsequent lines of code inside that function block.

#### Code Example: Returning and Storing Function Output

```python
def calculate_remaining_attempts(max_attempts, current_attempts):
    # Returns the calculation result back to the caller
    return max_attempts - current_attempts

# Storing returned output in a variable for conditional evaluation
remaining_attempts = calculate_remaining_attempts(3, 3)

if remaining_attempts <= 0:
    print("[ALERT] Account locked due to excessive failed logins.")
else:
    print(f"[INFO] Access granted. Remaining attempts: {remaining_attempts}")
```

## 🌐 Global vs. Local Variables

Variables behave differently depending on where they are defined in a script.

| **Variable Type**   | **Definition Scope**                             | **Lifespan & Memory Behavior**                                                                                           |
| ------------------------- | ------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------ |
| **Global Variable** | Defined outside of any function (at the script level). | Available throughout the entire program execution, accessible both inside and outside functions.                               |
| **Local Variable**  | Defined inside a function body (including parameters). | Created dynamically when the function runs and**deleted from memory**immediately after the function completes execution. |

### ⚠️ Scope Best Practices & Variable Shadowing

1. **Avoid Relying on Globals Inside Functions:** While functions can read global variables, modifying or relying on them inside functions makes code hard to debug. Always pass data explicitly via  **parameters** .
2. **Variable Shadowing (Name Collisions):** If you reuse a global variable name as a local variable inside a function, Python creates a separate local variable with that name. The local variable temporarily "shadows" the global one during function execution without altering the global value.

### Global variable

```Python
# Global variable
username = "elarson"

def check_user():
    # Local variable sharing the same name (Shadowing)
    username = "bmoreno"
    print("Inside function (Local):", username)  # Outputs: bmoreno

check_user()
print("Outside function (Global):", username)    # Outputs: elarson
```

## 📌Importing Modules and Libraries in Python

* **Module:** A file containing Python code—including definitions, functions, and classes—designed to be reused across different programs.
* **Library / Package:** A collection of modules bundled together to provide specialized functionality beyond Python's built-in core (e.g., networking, file handling, web requests).
* **Cybersecurity Utility:** Importing external and built-in libraries allows security analysts to leverage pre-built tools for parsing log files, querying REST APIs, interacting with file systems, and automating threat hunting scripts without writing low-level code from scratch.

### ⚙️ Python Import Syntax Variations

Python offers multiple ways to bring external or standard libraries into your script depending on what you need to access.

| Import Syntax                                  | Description & Usage                                                                  | Best Practice / Example                                                   |
| :--------------------------------------------- | :----------------------------------------------------------------------------------- | :------------------------------------------------------------------------ |
| **`import module`**                    | Imports the entire module. Requires referencing functions using dot notation.        | `import jsondata = json.loads(log_string)`                              |
| **`import module as alias`**           | Imports the module and assigns a shorthand alias for cleaner code.                   | `import datetime as dtnow = dt.datetime.now()`                          |
| **`from module import specific_item`** | Imports only specific functions, classes, or variables directly into your namespace. | `from os import pathexists = path.exists("/var/log/suricata/eve.json")` |

### 🛠️ Essential Standard Libraries for Cybersecurity

Python includes a robust standard library containing powerful modules that require no external installation:

* **`json`:** Encodes and decodes JSON data, indispensable for parsing Suricata `eve.json` logs, API payloads, and SIEM event streams.
* **`os` & `sys`:** Interact with the operating system, handle file system paths, manage environment variables, and process command-line arguments.
* **`datetime`:** Handles timestamps, log timelines, event correlation, and calculating time deltas during incident triage.
* **`re`:** Provides Regular Expression (RegEx) matching operations for extracting IP addresses, hashes, and custom patterns from raw log text.

### 💻 Code Example: Automating Log Parsing with Modules

The following script demonstrates how to import and combine standard Python modules (`json` and `os`) to check for a log file and parse structured security alerts:

```python
import json
import os

# Define path to Suricata alert log
log_path = "eve.json"

# Check if log file exists using the 'os' module
if os.path.exists(log_path):
    print(f"[INFO] Target log found: {log_path}")
  
    # Simulate reading and parsing a single JSON log line
    sample_log_line = '{"timestamp": "2026-10-22T11:00:00Z", "event_type": "alert", "alert": {"signature": "ET MALWARE Suspicious Activity"}}'
  
    # Parse JSON string into a Python dictionary using the 'json' module
    parsed_event = json.loads(sample_log_line)
  
    # Extract and display key event details
    print(f"[ALERT DETECTED] Time: {parsed_event['timestamp']}")
    print(f"Signature: {parsed_event['alert']['signature']}")
else:
    print(f"[WARNING] Log file not found at {log_path}. Check file path.")
```

## 🧵 Python Strings and Security Analysis

* **String Data (`str`):** An ordered sequence of characters used to store non-numeric text data. In cybersecurity, strings represent crucial telemetry items, including IP addresses, hostnames, usernames, URLs, file paths, hashes, and employee IDs.
* **Security Utility:** Analysts frequently manipulate strings to parse log files, extract specific packet metadata, validate identifier formats, and search for specific text patterns or Indicators of Compromise (IoCs).

### 🔢 String Indexing and Bracket Notation

Every character in a string is assigned a numerical index representing its position, enabling precise data extraction.

#### 1. Zero-Based & Negative Indices

* **Forward Indexing:** Starts at `0` for the first character (e.g., in `"h32rb17"`, index `0` is `"h"`).
* **Reverse Indexing:** Uses negative integers starting at `-1` for the final character, counting backward relative to the end of the string.

#### 2. Slicing Strings

Slicing allows analysts to extract multi-character sub-sequences using bracket notation with a colon (`[start:end]`):

* **Exclusion Rule:** The start index is inclusive, but the end index is **exclusive** (stops one character before the specified end position).
* **Example:** `"h32rb17"[0:3]` extracts characters at indices `0`, `1`, and `2`, returning `"h32"`.

### 🛠️ Essential String Functions and Methods

Python provides robust built-in functions and type-specific methods to evaluate and transform string data.

| Function / Method                     | Description & Behavior                                                                                                         | Cybersecurity Application Example                                                                                   |
| :------------------------------------ | :----------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------ |
| **`str()`**                   | Converts non-string inputs (like integers or floats) into string format.                                                       | Converting employee IDs or numerical error codes into strings so they can be parsed or sliced.                      |
| **`len()`**                   | Returns the total count of characters in a string object.                                                                      | Validating that a device ID or log entry adheres to a strict character-length standard before processing.           |
| **`.upper()` / `.lower()`** | Converts all characters in a string to uppercase or lowercase.                                                                 | Normalizing usernames, file extensions, or command strings to ensure case-insensitive matching during log analysis. |
| **`.index()`**                | Finds the **first occurrence** of a character or substring and returns its starting index. Raises an error if not found. | Locating specific substrings, usernames, or protocol headers within a raw log line.                                 |

### ⚠️ Important Considerations with `.index()`

* **First Occurrence Only:** If a target character or substring appears multiple times in a string (e.g., `"r45rt46".index("r")`), `.index()` returns **only the index of the first match** (`0`).
* **Substring Traps:** When searching for specific substrings (like `"tshah"`), ensure your query is precise. Searching for a partial match that exists earlier in the string (e.g., searching for `"ts"` when `"tsnow"` precedes it) will return the incorrect starting index.

## 📋 Python Lists and Security Analysis

* **List Data (`list`):** An ordered, mutable collection of items stored within a single variable. A single list can contain multiple data types.
* **Cybersecurity Utility:** Analysts use lists to manage collections of Indicators of Compromise (IoCs), such as lists of blocked IP addresses, suspicious usernames, active device IDs, and target URLs.
* **Mutability:** Unlike strings (which are immutable), **lists are mutable**, meaning elements can be added, removed, or modified in place after the list is created.

### 🔢 Indexing, Bracket Notation, and Slicing

Like strings, lists use zero-based indexing to track element positions.

#### 1. Bracket Notation & Modification

* **Accessing Elements:** Use square brackets with an index (e.g., `username_list[2]`).
* **Modifying Elements:** Because lists are mutable, you can reassign specific index positions directly:
  ```python
  username_list = ["elarson", "fgarcia", "tshah"]
  username_list[1] = "bmoreno"  # Replaces "fgarcia" with "bmoreno"
  ```

#### 2. List Slicing (Sublists)

* Extracting a range of elements yields a **sublist**.
* **Exclusion Rule:** `list_name[start:end]` includes the start index but **excludes** the end index (stops one position before).
  * Example: `["elarson", "fgarcia", "tshah"][0:2]` returns `["elarson", "fgarcia"]`.

### 🛠️ Essential List Methods

Python provides specialized built-in methods to manipulate and query list contents.

| List Method             | Syntax Example                      | Description & Behavior                                                                         |
| :---------------------- | :---------------------------------- | :--------------------------------------------------------------------------------------------- |
| **`.insert()`** | `usernames.insert(2, "wjaffrey")` | Inserts an element at a specific index position, shifting subsequent elements to the right.    |
| **`.remove()`** | `usernames.remove("elarson")`     | Removes the **first occurrence** of a specified element and shifts remaining items left. |
| **`.append()`** | `usernames.append("btang")`       | Adds a new element directly to the **end** of the list.                                  |
| **`.index()`**  | `usernames.index("tshah")`        | Returns the integer index of the **first occurrence** of the specified element.          |

### 🔄 Dynamic List Population: Lists with Loops

The `.append()` method is frequently paired with `for` loops to dynamically populate lists (such as accumulating filtered logs, active IP sockets, or processed numerical ranges).

```python
# Initializing an empty list
numbers_list = []

# Populating the list dynamically using a for loop and .append()
for i in range(1, 4):
    numbers_list.append(i)

print(numbers_list)  # Output: [1, 2, 3]
```

## 🔍 Python Regular Expressions (`re` Module) in Cybersecurity

* **Regular Expression (Regex):** A sequence of characters defining a search pattern. In Python, regex is used to search, parse, and extract complex patterns (such as IP addresses, email addresses, device IDs, and log anomalies) from unstructured text strings.
* **The `re` Module:** Python's built-in library for regular expression operations. It must be imported via `import re` before use.
* **`re.findall()`:** A core function that searches through a target string and returns **a list of all non-overlapping matches** matching the specified regex pattern.

#### 🔣 Regex Character Type Symbols

Character symbols match single characters of a specific category within a string.

| Symbol           | Description                                                                                          | Example Match                                                      |
| :--------------- | :--------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------- |
| **`\w`** | Matches any alphanumeric character (`A-z`, `0-9`) or an underscore (`_`).                      | In `"ID_A17"`, matches `I`, `D`, `_`, `A`, `1`, `7`. |
| **`\d`** | Matches any single numerical digit (`0-9`).                                                        | In `"ID_A17"`, matches `1`, `7`.                             |
| **`\s`** | Matches any single whitespace character (space, tab, newline).                                       | Matches the space in `"user 1"`.                                 |
| **`.`**  | Matches any single character (letters, digits, symbols, spaces) **except** for a newline.      | Matches any character except line breaks.                          |
| **`\.`** | Matches the literal period character (`.`). The backslash escapes the dot's special regex meaning. | Matches a literal dot in domain names or IP addresses.             |

#### 🔢 Quantifiers: Controlling Repetition

Quantifiers specify how many times a preceding character or character type must appear to constitute a valid match.

| Quantifier Symbol   | Description & Behavior                                        | Example                                                                     |
| :------------------ | :------------------------------------------------------------ | :-------------------------------------------------------------------------- |
| **`+`**     | One or more consecutive occurrences of the preceding element. | `\d+` matches `1`, `12`, or `12345`.                                |
| **`*`**     | Zero, one, or more occurrences of the preceding element.      | Matches elements including empty string states where characters are absent. |
| **`{n}`**   | Exactly `n` consecutive occurrences.                        | `\d{4}` matches four consecutive digits (e.g., `1234`).                 |
| **`{m,n}`** | Between `m` (minimum) and `n` (maximum) occurrences.      | `\d{1,3}` matches `1`, `12`, or `123`.                              |

> ⚠️ **Left-to-Right Scanning Rule:** Python scans strings from left to right. When a pattern match is completed (e.g., matching two digits with `\d{2}` in a sequence like `123`), Python extracts the match and resumes scanning immediately after the matched block (starting at the third digit, `3`), rather than overlapping indices.

#### 💻 Practical Code Example: Log Parsing with `re.findall()`

The following script demonstrates how to break down complex log data strings and use regex patterns (`\w+`, `:`, `\s`, `\d+`) to extract specific fields—such as usernames and login counts—while ignoring employee IDs and departments:

```python
import re

# Sample employee security log string
employee_logins_string = "1001 bmoreno: 12 Marketing 1002 tshah: 7 Human Resources 1003 sgilmore: 5 Finance"

# Define regex pattern to capture username, colon, space, and login attempts
# \w+ matches the username
# : matches the literal colon
# \s matches the whitespace
# \d+ matches one or more login digits
pattern = r"\w+:\s\d+"

# Extract all matches into a list
extracted_logins = re.findall(pattern, employee_logins_string)

print(extracted_logins)
# Output: ['bmoreno: 12', 'tshah: 7', 'sgilmore: 5']
```

--

--

# 📚 Python in practice

## 🚀 Automating Security in CI/CD Pipelines (DevSecOps)

* **DevSecOps:** A collaborative culture and operational model that integrates security practices directly into every stage of the Continuous Integration and Continuous Delivery/Deployment (CI/CD) lifecycle.
* **Security Automation:** Using scripts and programmatic tools (such as Python) to execute repeatable security checks, vulnerability scans, and policy evaluations without manual intervention.
* **Cybersecurity Utility:** Automating pipeline security shifts security left, catching vulnerabilities, misconfigurations, and hardcoded secrets early in development when remediation is fastest and least expensive.

### ⚙️ Why Automate Security with Python in CI/CD?

Manual security reviews slow down deployment pipelines and introduce human error. Python serves as an ideal glue language for CI/CD security automation due to its flexibility, rich ecosystem of libraries, and robust API integration capabilities.

| **Benefit**                      | **Operational Impact in CI/CD**                                                                                          |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| **Increased Speed & Efficiency** | Automated scripts run instantly alongside builds, maintaining rapid release cycles without sacrificing security coverage.      |
| **Early Problem Detection**      | Identifies code weaknesses and dependency vulnerabilities during development before code reaches production.                   |
| **Guaranteed Consistency**       | Standardizes security checks across every build, eliminating oversight and human error.                                        |
| **Reduced Analyst Workload**     | Frees security teams from repetitive testing tasks, allowing them to focus on complex threat modeling and architecture review. |
| **Cultural Integration**         | Embeds security into everyday developer workflows, reinforcing shared responsibility.                                          |

### 🔍 Core Security Tasks Automated via Python

Python scripts can orchestrate and interpret results across multiple layers of pipeline security:

#### 1. Security Testing

* **Static Application Security Testing (SAST):** Scripts initiate SAST tools to inspect raw source code for vulnerabilities, parse results, generate reports, and automatically fail builds upon detecting high-severity flaws.
* **Dynamic Application Security Testing (DAST):** Automates the execution of DAST tools against running applications in staging environments and feeds results back into the pipeline.
* **Software Composition Analysis (SCA):** Evaluates third-party libraries and open-source dependencies for known vulnerabilities, enforcing risk-based thresholds.

#### 2. Vulnerability & Compliance Automation

* **Vulnerability Scanning:** Schedules and executes scans on container images, cloud infrastructure configurations, and pipeline infrastructure.
* **Compliance Checks:** Automatically validates code and infrastructure settings against regulatory standards and internal security baselines.
* **Secrets Management:** Scans code repositories to prevent hardcoded credentials (`git secrets`) and interfaces with tools like HashiCorp Vault to inject runtime secrets securely.
* **Policy Enforcement ("Policy as Code"):** Defines security policies in code, evaluates pipeline artifacts against these rules, and halts releases if violations occur.

### 🔌 Integration with CI/CD Ecosystems

Python integrates seamlessly with industry-standard CI/CD platforms (such as Jenkins, GitLab CI, and CircleCI) through two primary mechanisms:

* **Pipeline Execution Steps:** CI/CD systems are configured to invoke Python script execution directly as part of their build/test stages.
* **API Orchestration:** Python scripts leverage robust HTTP libraries to interact with CI/CD system APIs (managing jobs, triggering builds, pulling artifacts) and security tool APIs (initiating scans and retrieving telemetry).

### 💻 Extended Pipeline Automation Tasks

Beyond direct security testing, Python scripts automate supporting infrastructure tasks to ensure secure deployments:

* **Environment Provisioning:** Automatically configures staging and test environments with hardened network settings and access controls.
* **Code Quality & Linting:** Runs linters early in development to flag syntax anomalies, style violations, and potential logic errors.
* **Secure Release Management:** Automates the secure transfer of build packages and configuration files to staging and production environments following strict deployment protocols.

## 🐍 Essential Python Components for Security Automation

* **Automation:** The use of programmatic logic to reduce human manual effort for repetitive, high-volume cybersecurity tasks such as log triage, account access management, and device patching.
* **Component Integration:** Effective security automation scripts integrate multiple fundamental Python programming constructs into cohesive workflows.

### 🧱 The Core Pillars of Python Automation

To build robust security automation scripts, analysts rely on a foundational set of Python components:

| Component                        | Description & Cybersecurity Utility                                                                                                   |
| :------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------ |
| **Variables**              | Containers that store dynamic data (e.g., IP addresses, counts, usernames), eliminating the need to hardcode static values.           |
| **Conditional Statements** | Evaluates specific criteria (`if`/`else`) to determine whether an action should execute, enabling automated decision-making.      |
| **Iterative Statements**   | Loops (`for` and `while`) that automate repetitive execution across sequences or until specific conditions are met.               |
| **Functions**              | Reusable blocks of code (built-in or user-defined) that encapsulate specific tasks, preventing code redundancy.                       |
| **String Techniques**      | Methods (`str()`, `len()`, `.index()`) and bracket slicing used to parse, clean, and extract text data from logs.               |
| **List Techniques**        | Mutable data structures managed via methods (`.append()`, `.remove()`, `.insert()`, `.index()`) to track collections of IoCs. |

### 🛠️ Practical Example: Analyzing Flagged User Logins

Security automation frequently requires combining multiple core components to investigate anomalies. For example, counting daily login attempts for a flagged user involves:

1. **Iteration (`for` loop):** Traverse a list containing all username strings associated with daily login attempts.
2. **Conditionals (`if` statement):** Evaluate whether each iterated username matches the flagged user identifier.
3. **Counter Variable:** Increment a tracking variable each time a match evaluates to `True`.
4. **Encapsulation (Functions):** Wrap the entire logic inside a reusable function that accepts parameters (target username and the login list) and returns the final count.

### 📂 Working with Security Log Files

Security telemetry is primarily generated and stored in external log files—chronological records of system events where new entries are continuously appended.

* **Common Security File Formats:**
  * **`.txt` Files:** Plain text files with flexible or unformatted delimiters (such as spaces or tabs).
  * **`.csv` (Comma-Separated Values) Files:** Plain text files where data fields are explicitly separated by commas.
* **Python File Handling:** Python allows analysts to automate the ingestion, reading, writing, and parsing of `.txt` and `.csv` log files directly within security pipelines.

## 📂 Importing, Reading, and Writing Files in Python

* **File Operations:** The programmatic ability to open, read, modify, and create external files (such as `.txt` and `.csv` logs) using Python.
* **Security Utility:** Security analysts rely on file handling to ingest raw system logs (e.g., authentication records, error logs, firewall activity), parse security events, record indicators of compromise (IoCs), and generate audit reports.

### ⚙️ Opening Files with `with open()`

To safely open and manage files in Python without risking resource leaks or file corruption, analysts use the `with` statement combined with the `open()` function.

#### 1. Syntax Structure

```python
with open("update_log.txt", "r") as file:
    # Indented block for file operations
```

#### 2. Breakdown of Components

* **`with` Keyword:** Context manager that automatically handles error management and ensures the file is properly closed once the indented code block finishes executing.
* **`open()` Function:** Opens the target file. Requires two main parameters:
  1. **File Name / Path:** A string representing either the filename (if located in the same directory) or the **absolute file path** (e.g., `"/home/analyst/logs/access_log.txt"`) starting from the root directory.
  2. **Mode Argument:** Specifies the intended action (`"r"` for reading, `"w"` for writing/overwriting, or `"a"` for appending).
* **`as file`:** Assigns the open file object to a local variable (e.g., `file`) for manipulation within the context block.

### 📖 Reading Files in Python

* **The `"r"` Mode:** Opens an existing file exclusively for reading.
* **The `.read()` Method:** Converts the contents of an open file into a standard Python string, enabling analysts to apply string methods (`.index()`, `len()`, slicing, regex searching) to raw log data.

#### Code Example: Reading a Log File

```python
# Open log file in read mode and extract contents into a string variable
with open("update_log.txt", "r") as file:
    updates = file.read()

# Display or analyze log contents using standard string functions
print(f"Log length: {len(updates)} characters")
```

### ✍️ Writing and Appending to Files in Python

Analysts frequently need to generate new security reports, write approved allow lists, or append real-time log entries to storage files. This requires switching the mode argument in `open()`:

| Mode                       | Action & Behavior                                                                                                                         | Use Case in Cybersecurity                                                                      |
| :------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------- |
| **`"w"`** (Write)  | Opens a file for writing. **Destroys existing content** if the file already exists, or **creates a new file** if it does not. | Overwriting configuration baselines or creating a fresh allow list from scratch.               |
| **`"a"`** (Append) | Opens a file to add data. Preserves existing content and **appends new text to the end** of the file.                               | Continuously logging new security events, failed login attempts, or access logs as they occur. |

* **The `.write()` Method:** Writes string data directly into the target file when opened in `"w"` or `"a"` mode.

#### Code Example: Appending to a Log File

```python
# New telemetry line to log
new_login_entry = "jrafael,192.168.243.140,4:56:27,True\n"

# Open log file in append mode ('a') and write the new entry
with open("access_log.txt", "a") as file:
    file.write(new_login_entry)
```

## 🧩 Parsing File Contents in Python: `.split()` and `.join()`

* **Parsing:** The process of converting raw, unstructured data into a structured format (such as transforming raw text strings into manageable lists, or vice versa) for processing and interpretation.
* **Security Utility:** Logs read from `.txt` or `.csv` files are initially loaded as large continuous strings via `.read()`. Analysts use parsing methods like `.split()` and `.join()` to process log entries line-by-line, extract specific fields, filter out unauthorized access, and save modified data back to files.

### ✂️ Converting Strings to Lists with `.split()`

The `.split()` method breaks a single string object into a list of elements based on a specified delimiter.

#### 1. Delimiters & Default Behavior

* **Custom Delimiters:** Passing a character as an argument (e.g., `string.split(",")`) splits the text wherever that specific character appears (ideal for CSV logs or comma-separated allow lists).
* **Default Whitespace Splitting:** If no argument is passed (e.g., `string.split()`), Python automatically splits the string at every whitespace character—including spaces, tabs, and newline (`\n`) characters.

#### 2. Applied Security Example: Parsing Log Data

```python
# Step 1: Open and read file into a string
with open("update_log.txt", "r") as file:
    log_contents = file.read()

# Step 2: Convert log string into a list of words/tokens after closing the file context
log_list = log_contents.split()

# Step 3: Iterate through elements using a loop
for token in log_list:
    if "FAIL" in token:
        print(f"[ALERT] Found failure flag: {token}")
```

### 🔗 Converting Lists to Strings with `.join()`

When updated list data needs to be written back to a file using `.write()`, it must first be converted back into string format. The `.join()` method concatenates list elements into a single string.

#### 1. Syntax Structure & Mechanics

Unlike `.split()`, the syntax for `.join()` attaches the method to the **delimiter string** rather than the variable:

```python
# Delimiter string appended with .join(target_list)
formatted_string = "DELIMITER".join(list_variable)
```

#### 2. Common Join Delimiters

* **`" ".join(list_var)`:** Joins elements separated by a single space.
* **`",".join(list_var)`:** Joins elements separated by commas (formatting as CSV).
* **`" ".join(list_var)`:** Joins elements with each item placed on a **new line** (ideal for clean log file writing).

### 🔄 Complete File Update Cycle (Read -> Parse -> Modify -> Write)

The following workflow illustrates a complete cycle of reading a file, parsing it to modify contents, converting it back to a string, and updating the original file:

```python
# 1. Read existing log file contents
with open("update_log.txt", "r") as file:
    updates_string = file.read()

# 2. Parse string into a list for modification
updates_list = updates_string.split()

# [Perform security operations/modifications on updates_list here]
# Example: updates_list.append("SYSTEM_PATCHED")

# 3. Convert modified list back into a single string separated by spaces
updated_log_string = " ".join(updates_list)

# 4. Overwrite original log file with updated string
with open("update_log.txt", "w") as file:
    file.write(updated_log_string)
```







aa
