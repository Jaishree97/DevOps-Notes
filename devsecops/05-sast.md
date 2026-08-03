# 📘 Static Application Security Testing (SAST)

> **"Find security vulnerabilities in source code before the application is built or deployed."**

Static Application Security Testing (SAST) analyzes an application's **source code, bytecode, or binaries** without executing the application to identify security vulnerabilities early in the Software Development Lifecycle (SDLC).

---

## 📑 Table of Contents

- [📖 What is SAST?](#-what-is-sast)
- [🎯 Why SAST?](#-why-sast)
- [🔄 How SAST Works](#-how-sast-works)
- [🔍 Vulnerabilities Detected by SAST](#-vulnerabilities-detected-by-sast)
- [🛠 Common SAST Tools](#-common-sast-tools)
- [💻 Practical Example](#-practical-example)
- [📊 SAST vs DAST](#-sast-vs-dast)
- [✅ Best Practices](#-best-practices)
- [⚠️ Common Mistakes](#️-common-mistakes)
- [📝 Quick Revision](#-quick-revision)
- [🎤 Interview Questions](#-interview-questions)

---

# 📖 What is SAST?

Static Application Security Testing (SAST) is a security testing technique that scans an application's **source code** without running it.

It identifies coding mistakes and security vulnerabilities early in the development process.

> [!NOTE]
> SAST is also known as **White Box Testing** because it has access to the application's source code.

---

# 🎯 Why SAST?

SAST helps developers:

- Detect vulnerabilities early.
- Reduce remediation costs.
- Improve code quality.
- Secure applications before deployment.
- Integrate security into CI/CD pipelines.

---

# 🔄 How SAST Works

```text
Developer Writes Code
          │
          ▼
 Git Push / Pull Request
          │
          ▼
     SAST Scanner
          │
          ▼
Analyzes Source Code
          │
          ▼
Security Report
          │
          ▼
Developer Fixes Issues
```

SAST scans the code **without executing the application**.

---

# 🔍 Vulnerabilities Detected by SAST

| Vulnerability | Example |
|---------------|---------|
| SQL Injection | Unsafe database queries |
| Cross-Site Scripting (XSS) | Unsanitized user input |
| Hardcoded Secrets | API keys, passwords |
| Buffer Overflow | Memory handling issues |
| Command Injection | Unsafe system commands |
| Weak Cryptography | Insecure encryption algorithms |
| Insecure Coding Practices | Poor input validation |

---

# 🛠 Common SAST Tools

| Tool | Description |
|------|-------------|
| SonarQube | Code quality and security analysis |
| Semgrep | Fast rule-based code scanning |
| CodeQL | Semantic code analysis by GitHub |
| Checkmarx | Enterprise SAST platform |
| Fortify SCA | Static code security analysis |
| Veracode | Cloud-based application security testing |

---

# 💻 Practical Example

A developer writes the following code:

```python
query = "SELECT * FROM users WHERE id = " + user_input
```

A SAST tool detects this as a potential **SQL Injection** vulnerability.

Recommended fix:

```python
cursor.execute(
    "SELECT * FROM users WHERE id = %s",
    (user_input,)
)
```

Using parameterized queries helps prevent SQL Injection attacks.

---

# 📊 SAST vs DAST

| SAST | DAST |
|------|------|
| Tests source code | Tests running application |
| Finds issues early | Finds runtime vulnerabilities |
| Does not execute the application | Requires a running application |
| White Box Testing | Black Box Testing |
| Used during development | Used after deployment or staging |

---

# ✅ Best Practices

- Scan every Pull Request.
- Integrate SAST into CI/CD pipelines.
- Fix High and Critical issues first.
- Review findings regularly.
- Combine SAST with DAST and SCA.
- Keep SAST rules updated.

---

# ⚠️ Common Mistakes

- Running SAST only before release.
- Ignoring reported vulnerabilities.
- Treating all findings as critical.
- Not reviewing false positives.
- Depending only on SAST for application security.

---

# 📝 Quick Revision

- SAST scans source code without executing it.
- SAST is a White Box Testing technique.
- Finds vulnerabilities early in development.
- Common tools include SonarQube, Semgrep, and CodeQL.
- SAST works best when integrated into CI/CD.

---

# 🎤 Interview Questions

### 1. What is SAST?

**Answer:**

SAST (Static Application Security Testing) analyzes an application's source code without executing it to identify security vulnerabilities early in the SDLC.

---

### 2. Why is SAST important?

**Answer:**

It helps detect vulnerabilities early, reduces remediation costs, improves code quality, and supports Shift Left Security.

---

### 3. What types of vulnerabilities can SAST detect?

**Answer:**

SAST can detect:

- SQL Injection
- Cross-Site Scripting (XSS)
- Hardcoded secrets
- Command Injection
- Weak cryptography
- Insecure coding practices

---

### 4. What is the difference between SAST and DAST?

**Answer:**

SAST analyzes source code without executing the application, whereas DAST tests a running application from the outside to identify runtime vulnerabilities.

---

### 5. Name some popular SAST tools.

**Answer:**

- SonarQube
- Semgrep
- CodeQL
- Checkmarx
- Fortify SCA
- Veracode

---

### 6. Can SAST replace DAST?

**Answer:**

No. SAST and DAST complement each other. SAST identifies coding issues early, while DAST detects vulnerabilities in a running application.

---

# 📌 Key Takeaways

- SAST scans source code without executing the application.
- It supports Shift Left Security by identifying vulnerabilities early.
- SAST improves code quality and application security.
- Integrating SAST into CI/CD enables automated security checks.
- SAST should be used together with DAST, SCA, and other security testing techniques.

---

## ⏭️ Next

**➡️ 06-sca.md**
