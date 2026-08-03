# 📘 Static Application Security Testing (SAST)

<p align="center">

> **"Secure your code before you build it."**

Analyze Source Code • Find Vulnerabilities Early • Shift Security Left

</p>

---

## 📑 Table of Contents

- [📋 Chapter Information](#-chapter-information)
- [🎯 Learning Objectives](#-learning-objectives)
- [📚 Prerequisites](#-prerequisites)
- [📖 What is SAST?](#-what-is-sast)
- [🤔 Why SAST Matters](#-why-sast-matters)
- [⚙️ How SAST Works](#️-how-sast-works)
- [🔄 SAST Workflow](#-sast-workflow)
- [⚖️ SAST vs DAST vs SCA](#️-sast-vs-dast-vs-sca)
- [🔍 Common Vulnerabilities Detected](#-common-vulnerabilities-detected)
- [🛠 Popular SAST Tools](#-popular-sast-tools)
- [💻 Hands-on Lab (Semgrep)](#-hands-on-lab-semgrep)
- [🚀 GitHub Actions Integration](#-github-actions-integration)
- [📌 Best Practices](#-best-practices)
- [❌ Common Mistakes](#-common-mistakes)
- [💡 Key Takeaways](#-key-takeaways)
- [🎤 Interview Questions](#-interview-questions)
- [📚 References](#-references)
- [📝 Summary](#-summary)

---

# 📋 Chapter Information

| Category | Details |
|-----------|----------|
| Difficulty | 🟢 Beginner |
| Reading Time | 15–20 Minutes |
| Hands-on Lab | ✅ Yes |
| Interview Focus | ⭐⭐⭐⭐⭐ |

---

# 🎯 Learning Objectives

After completing this chapter, you will be able to:

- Explain what SAST is.
- Understand how SAST works.
- Identify common vulnerabilities found by SAST.
- Compare SAST with DAST and SCA.
- Scan source code using Semgrep.
- Integrate SAST into a GitHub Actions pipeline.

---

# 📚 Prerequisites

Before reading this chapter, you should understand:

- DevSecOps Basics
- SDLC
- Shift Left Security
- Git & GitHub
- CI/CD Fundamentals

---

# 📖 What is SAST?

**Static Application Security Testing (SAST)** is a security testing technique that analyzes an application's **source code, bytecode, or binaries without executing the application**.

Unlike runtime testing, SAST examines the code itself to identify security vulnerabilities during development.

Because the application does not need to run, SAST is considered a **static** testing method.

> 💡 **Shift Left Connection:** SAST helps developers identify and fix security issues before the application reaches testing or production.

---

# 🤔 Why SAST Matters

Imagine a developer introduces an SQL Injection vulnerability.

Without SAST:

- The vulnerable code is committed.
- The application is built.
- It is deployed.
- The vulnerability may only be discovered during penetration testing or after an attack.

With SAST:

- The code is scanned immediately.
- The vulnerability is reported.
- The developer fixes it before deployment.

This saves time, reduces costs, and lowers security risks.

---

# ⚙️ How SAST Works

```text
Developer Writes Code
          │
          ▼
Git Commit
          │
          ▼
SAST Scanner
          │
          ├── Analyze Source Code
          ├── Identify Security Patterns
          ├── Generate Report
          └── Suggest Fixes
          │
          ▼
Developer Fixes Issues
```

SAST tools examine the source code and compare it against predefined security rules to identify potential vulnerabilities.

---

# 🔄 SAST Workflow

```text
Plan
 │
 ▼
Write Code
 │
 ▼
Commit Code
 │
 ▼
Run SAST Scan
 │
 ▼
Review Findings
 │
 ▼
Fix Vulnerabilities
 │
 ▼
Commit Updated Code
 │
 ▼
Build & Deploy
```

---

# ⚖️ SAST vs DAST vs SCA

| Feature | SAST | DAST | SCA |
|----------|------|------|------|
| Analyzes | Source Code | Running Application | Third-Party Dependencies |
| Application Running | ❌ No | ✅ Yes | ❌ No |
| Finds | Coding Issues | Runtime Issues | Vulnerable Libraries |
| SDLC Stage | Development | Testing | Build |

---

# 🔍 Common Vulnerabilities Detected

SAST tools commonly detect:

- SQL Injection
- Cross-Site Scripting (XSS)
- Command Injection
- Hardcoded Credentials
- Weak Cryptography
- Buffer Overflows
- Path Traversal
- Insecure Deserialization
- Improper Error Handling
- Insecure Random Number Generation

---

# 🛠 Popular SAST Tools

| Tool | Description |
|------|-------------|
| Semgrep | Fast open-source static analysis tool |
| CodeQL | GitHub's semantic code analysis engine |
| SonarQube | Code quality and security analysis |
| Checkmarx | Enterprise SAST platform |
| Fortify SCA | Enterprise static analysis |
| Veracode | Cloud-based application security testing |

---

# 💻 Hands-on Lab (Semgrep)

## Objective

Scan a vulnerable application using Semgrep.

---

## Step 1 — Install Semgrep

```bash
python3 -m pip install semgrep
```

Verify the installation:

```bash
semgrep --version
```

---

## Step 2 — Create a Sample Python File

Create a file named `app.py`:

```python
import os

user_input = input("Enter filename: ")
os.system("cat " + user_input)
```

This example is intentionally vulnerable because it executes user input directly.

---

## Step 3 — Run a Security Scan

```bash
semgrep scan --config=auto .
```

---

## Expected Output

Semgrep should flag the use of `os.system()` with unsanitized user input as a potential command injection vulnerability.

---

## Step 4 — Fix the Code

Replace:

```python
os.system("cat " + user_input)
```

With a safer approach using Python's `subprocess` module and proper input validation.

Run the scan again to confirm the issue is resolved.

---

# 🚀 GitHub Actions Integration

Example workflow:

```yaml
name: SAST Scan

on:
  push:
  pull_request:

jobs:
  semgrep:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - uses: returntocorp/semgrep-action@v1
```

This workflow automatically scans code on every push and pull request.

---

# 📌 Best Practices

- Scan every Pull Request.
- Fix High and Critical findings immediately.
- Keep security rules updated.
- Combine SAST with DAST and SCA.
- Review false positives carefully.
- Educate developers on secure coding practices.

---

# ❌ Common Mistakes

- Ignoring scan results.
- Treating SAST as the only security solution.
- Running scans only before production.
- Using outdated rule sets.
- Not integrating SAST into CI/CD.

---

# 💡 Key Takeaways

- SAST analyzes source code without running the application.
- It supports the Shift Left Security approach.
- It detects coding vulnerabilities early.
- It integrates seamlessly into CI/CD pipelines.
- SAST should be combined with DAST, SCA, and runtime security for comprehensive protection.

---

# 🎤 Interview Questions

1. What is Static Application Security Testing (SAST)?
2. How does SAST differ from DAST?
3. Why is SAST considered a Shift Left practice?
4. Name three popular SAST tools.
5. What types of vulnerabilities can SAST detect?
6. Can SAST detect runtime vulnerabilities? Why or why not?
7. How would you integrate SAST into a GitHub Actions pipeline?

---

# 📚 References

- OWASP
- Semgrep Documentation
- GitHub CodeQL Documentation
- SonarQube Documentation

---

# 📝 Summary

Static Application Security Testing (SAST) is a foundational DevSecOps practice that analyzes source code for security vulnerabilities before an application is executed. By integrating SAST into the development workflow and CI/CD pipelines, teams can identify and remediate issues early, reducing risk and supporting the Shift Left Security approach.

---

## 📚 Next Chapter

➡️ **06-sca.md**

Learn how **Software Composition Analysis (SCA)** identifies vulnerable third-party libraries and open-source dependencies before they become security risks.
