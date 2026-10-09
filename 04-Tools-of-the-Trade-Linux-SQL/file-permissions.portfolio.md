# File Permissions in Linux - Security Audit & Authorization Management

## Project description

As a security professional working with the research team at a large organization, my role involves ensuring that all users are correctly authorized with appropriate system permissions to maintain strict confidentiality and data integrity. This project demonstrates the investigation, modification, and post-modification validation of file and directory permissions within a Linux environment. By auditing and correcting overly permissive access rights using command-line tools, I successfully aligned system configurations with organizational security policies and verified the security posture through continuous validation.

---

## Check file and directory details

To establish the baseline and examine the existing file structure, file names, hidden files, and their respective permissions within the `projects` directory, the initial audit command was executed:

```Shell
ls -la
```

**Baseline Analysis:** The initial audit revealed multiple authorization anomalies, including excessive write permissions for *Others* on `project_k.txt`, misconfigured permissions on the hidden archive `.project_x.txt`, and unauthorized group access rights on the `drafts` directory.

![1791552779032](<https://file+.vscode-resource.vscode-cdn.net/c%3A/Users/Francisco/OneDrive/Ambiente%20de%20Trabalho/google-cybersecurity-portfolio/04-Tools-of-the-Trade-Linux-SQL/image/Linux-commands/1791552779032.png>)

## Describe the permissions string

Taking the initial permission string `-rw-rw-rw-` from `project_k.txt` as an example:

* **First character (`-`):** Indicates the file type (in this case, a standard regular file; a directory would display as `d`).
* **Characters 2 to 4 (`rw-`):** Represent the **User (Owner)** permissions. The owner (`melo`) has read (`r`) and write (`w`) permissions.
* **Characters 5 to 7 (`rw-`):** Represent the **Group** permissions. Members of the owner's group have read (`r`) and write (`w`) permissions.
* **Characters 8 to 10 (`rw-`):** Represent the **Others** permissions. Any other system user has read (`r`) and write (`w`) permissions.

## Change file permissions

**Scenario Requirement:** The organization strictly prohibits granting write access to "Others" on any files. Upon reviewing `project_k.txt`, it was found to have `rw-` permissions for Others (`-rw-rw-rw-`).

### 1\. Execution Command

To remove write access for Others while preserving user and group permissions, and to immediately validate the corrected permissions string, the following commands were executed:

```Shell
chmod o-w project\_k.txt
ls \-la project\_k.txt
```

![1791552635986](<https://file+.vscode-resource.vscode-cdn.net/c%3A/Users/Francisco/OneDrive/Ambiente%20de%20Trabalho/google-cybersecurity-portfolio/04-Tools-of-the-Trade-Linux-SQL/image/Linux-commands/1791552635986.png>)

**Explanation:** The permission string for `project_k.txt` successfully transitioned from `-rw-rw-rw-` to `-rw-rw-r--`, confirming the complete removal of write access for unauthorized external users.

## Change file permissions on a hidden file

**Scenario Requirement:** The archived hidden file `.project_x.txt` should not grant write permissions to anyone, but both the user and the group should have read access.

### 1\. Execution Command

To secure the hidden file by stripping write permissions, assigning appropriate read rights, and verifying the outcome, the following commands were executed:

```Shell
chmod u-w,g-w+r .project\_x.txt
ls \-la .project\_x.txt
```

![1791552643942](image/Linux-commands/1791552643942.png)

**Explanation:** The validation confirmed that write permissions were entirely removed from both the owner and the group, while read access was correctly established, ensuring secure, restricted data archiving.

## Change directory permissions

**Scenario Requirement:** The `drafts` subdirectory and its contents must be strictly restricted so that only the owner can access them, removing group execution rights.

### 1\. Execution Command

To remove execution permissions from the group, isolate the directory, and audit the updated directory permissions, the following commands were executed:

```Shell
chmod g-x drafts
ls \-ld drafts
```

![1791552655394](image/Linux-commands/1791552655394.png)

**Explanation:** By removing the execute (`x`) permission from the group (`g-x`), members of the group can no longer enter or list the contents of the `drafts` directory, enforcing a strict least-privilege boundary around sensitive research drafts.

## Summary

Through this structured security audit and remediation process, I successfully identified, corrected, and validated multiple file and directory authorization gaps. By systematically applying targeted Linux commands (`chmod`) and proving correctness via rigorous post-remediation validation (`ls -la` / `ls -ld`), I enforced the principle of least privilege across the environment. This project highlights my practical capability to manage secure system access, investigate configurations, and maintain robust audit trails for enterprise assets.
