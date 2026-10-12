# 🐧 Course 4: Tools of the Trade: Linux and SQL

## 📌 Overview

This course introduced the foundational Linux and SQL skills used in cybersecurity operations. It focused on understanding how operating systems work, how Linux is used in security environments, how to work effectively from the Bash shell, and how to query databases to investigate access patterns and operational data.

The work in this folder reflects the practical, hands-on learning completed during the final module of the Google Cybersecurity Certificate. It includes notes on Linux and SQL fundamentals, a permissions remediation exercise, and a set of SQL filtering investigations used to analyze authentication and employee data.

## 🧭 Course 4 Modules at a Glance

### Module 1: Introduction to operating systems

This module introduced the role of the operating system and how it manages hardware, software, and user interaction. I explored common operating systems, virtualization concepts, and the difference between graphical and command-line interfaces.

### Module 2: The Linux operating system

This module introduced Linux as a key operating system in cybersecurity and IT operations. I reviewed Linux architecture, common distributions, shell usage, and the importance of Linux for system administration, investigation, and automation.

### Module 3: Linux commands in the Bash shell

This module focused on using the Bash shell to navigate the filesystem, inspect system state, manage users and permissions, and troubleshoot configurations. It emphasized the practical value of command-line tools for security analysts and administrators.

### Module 4: Databases and SQL

This module introduced SQL as a way to interact with databases and analyze structured data. I learned how to use `SELECT`, `WHERE`, `LIKE`, and logical operators such as `AND`, `OR`, and `NOT` to filter and investigate records in security-related datasets.

## 🔐 What I Learned

- How operating systems coordinate software, hardware, and user requests.
- The purpose and structure of the Linux operating system in security and systems administration.
- How the Bash shell supports file navigation, process control, and system inspection.
- The importance of file permissions and least-privilege access in protecting information.
- How to interpret Linux permission strings such as `rwx`, `r-x`, and `rw-`.
- How to use SQL to retrieve, filter, and analyze relevant records from a database.
- How logical operators and wildcards help narrow investigations and isolate suspicious activity.
- How database queries support incident analysis, access review, and operational reporting.

## 🧪 Practical Exercises and Deliverables

This section includes the hands-on work completed during the course:

- [M4-Notes.md](./M4-Notes.md) — Summary of core Linux and SQL concepts, system fundamentals, and security-relevant notes from the course.
- [file-permissions.portfolio.md](./file-permissions.portfolio.md) — Linux permission audit and remediation exercise focused on least privilege and secure access control.
- [filters-SQL-queries.md](./filters-SQL-queries.md) — SQL investigation covering login attempts and employee data using filters, wildcards, and logical conditions.
- [Reference Guide SQL.pdf](./Reference%20Guide%20SQL.pdf) — Reference material covering SQL syntax and database query fundamentals.

## 📚 Core Study Notes

### Operating systems and Linux fundamentals

- An operating system is the software layer that manages hardware and application interaction.
- Linux is an open-source operating system widely used in enterprise environments, server infrastructure, and cybersecurity work.
- The shell allows users to interact with the system using text commands.
- Bash is a powerful shell commonly used for scripting, configuration, investigation, and automation.

### Linux command-line operations

- Commands such as `ls`, `pwd`, `cd`, `mkdir`, and `rm` are used to navigate and manage files.
- Security analysts use system commands to inspect configurations and validate access controls.
- The `chmod` command modifies file permissions to enforce least privilege and reduce exposure.
- File permission strings help define what the owner, group, and others can read, write, or execute.

### SQL and database investigation

- SQL is used to communicate with relational databases and extract relevant data.
- The `SELECT` statement retrieves one or more columns from a table.
- The `WHERE` clause filters records based on conditions such as dates, times, departments, or values.
- Logical operators such as `AND`, `OR`, and `NOT` allow analysts to combine conditions and target specific records.
- The `LIKE` keyword paired with `%` supports wildcard matching for partial values such as office names or country codes.

### Security relevance

- Least privilege is essential for reducing the risk of unauthorized access or accidental changes.
- Permission review helps ensure files and directories remain properly restricted.
- SQL filtering helps security teams isolate suspicious events, identify patterns, and support investigations.
- Database queries are a practical tool for reviewing access events, asset assignments, and operational conditions.

## 🛡️ Key Linux and SQL Concepts Covered

- **Operating system:** Software responsible for managing hardware and user interaction.
- **Linux:** Open-source OS widely used for secure, scalable infrastructure.
- **Bash shell:** Command-line interface used to execute system commands.
- **File permissions:** Controls that determine read, write, and execute access.
- **Least privilege:** Granting only the access needed to perform a function.
- **SQL:** Language used to interact with structured data.
- **SELECT:** Retrieves data from a database.
- **WHERE:** Filters records based on conditions.
- **LIKE:** Matches patterns in text values.
- **AND / OR / NOT:** Logical operators used to combine or negate search criteria.

## 📁 Folder Contents

```text
04-Tools-of-the-Trade-Linux-SQL/
├── README.md
├── M4-Notes.md
├── file-permissions.portfolio.md
├── filters-SQL-queries.md
├── Reference Guide SQL.pdf
└── image/
```

## 📌 Key Takeaway

This course built a practical foundation in Linux system administration and SQL-based investigation. It showed how command-line tools and database queries support cybersecurity work by improving visibility, strengthening access control, and helping analysts identify suspicious behavior quickly and accurately.
