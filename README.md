# linux-file-permissions-security-fundamentals
Linux file permissions from a security perspective — foundational access control aligned with ISO/IEC 27001:2022 (A.15, A.16, A.18).

# File Permissions in Linux – Security Fundamentals (Google Cybersecurity Certificate Lab)

This project focuses on examining and modifying file and directory permissions in a Linux environment to ensure that users have only the access they are authorized for. It was completed as part of the Google Cybersecurity Professional Certificate (via INCO Academy) and demonstrates foundational access control practices relevant to both SOC operations and ISO/IEC 27001:2022.

---

## Project Description

The tasks were performed in a managed Linux authorization lab environment. The goal was to:

- analyze existing permissions,
- adjust them according to organizational security policies,
- and document the results clearly and accurately.

Proper permission management is essential for preventing unauthorized access, enforcing least privilege, and maintaining secure system configurations.

---

## Objectives

This project demonstrates the ability to:

- inspect file and directory permissions using `ls -l` and `ls -la`
- interpret Linux permission strings for user, group, and others
- understand how read (`r`), write (`w`), and execute (`x`) permissions apply to files and directories
- apply organizational access control policies to real files and directories
- modify permissions using `chmod` to remove or restrict write access
- adjust permissions on hidden files and directories
- ensure that access rights align with security requirements and least‑privilege principles

---

## Key Tasks Performed

### Checking file and directory details
- Used `ls -l` to view permission strings, ownership, file type, size, and modification dates.
- Used `ls -la` to inspect hidden files (e.g., `.project_x.txt`).

### Understanding permission strings
- Interpreted the structure of permission strings:
  - file type (`d` for directory, `-` for file)
  - user permissions
  - group permissions
  - others permissions

### Modifying file permissions
- Applied organizational policy: “others” must not have write access.
- Adjusted permissions on `project_k.txt` using:
  - `chmod u=r,g=r,o=r project_k.txt`
  - or `chmod o-w project_k.txt`
- Ensured the resulting permissions were `-rw-rw-r--`.

### Modifying permissions on a hidden file
- Ensured `.project_x.txt` had no write permissions for any user type.
- Applied:
  - `chmod u=r,g=r .project_x.txt`
- Resulting permissions: `-r--r-----`.

### Adjusting directory permissions
- Ensured only the correct user (`researcher2`) could access the `drafts` directory.
- Removed group execute permission using:
  - `chmod g-x drafts`


---

## ISO/IEC 27001:2022 Alignment

Although this is a technical fundamentals lab, the concepts directly support several access control–related controls in ISO/IEC 27001:2022:

- **A.15 Access control** — Linux permissions enforce logical access rules and least privilege.
- **A.16 Identity management** — Users and groups represent identity lifecycle and ownership.
- **A.18 Access rights** — Provisioning, modifying, and revoking file and directory access.

These mappings demonstrate how technical configuration supports governance, compliance, and secure operations.

---

## SOC Relevance

Correct file permissions are essential in SOC environments because:

- misconfigured permissions often appear in alerts and logs,
- unauthorized write access can lead to data tampering or malware placement,
- privilege escalation frequently begins with overly permissive files or directories.

Understanding these fundamentals strengthens incident analysis and secure configuration review.

---

## Commands Used

- `cd` — change directory  
- `ls` — list files  
- `ls -l` — show detailed permissions  
- `ls -la` — show detailed permissions including hidden files  
- `chmod` — modify file and directory permissions  

---

## Author

**Kurnia Wijayanti**  
Cybersecurity Analyst bridging technical SOC experience with ISMS, audit, and risk‑based security governance.

## Full Portfolio Document

The complete assessment, including screenshots of command execution and detailed analysis, is available in the `/portfolio` folder.
