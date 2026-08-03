# 📘 Software Composition Analysis (SCA)

> **"Secure your dependencies before they become your vulnerabilities."**

Software Composition Analysis (SCA) is the process of identifying and managing security risks in third-party libraries, open-source packages, and project dependencies.

---

## 📑 Table of Contents

- [📖 What is SCA?](#-what-is-sca)
- [🎯 Why SCA?](#-why-sca)
- [🔄 How SCA Works](#-how-sca-works)
- [🔍 What Does SCA Detect?](#-what-does-sca-detect)
- [🛠 Common SCA Tools](#-common-sca-tools)
- [💻 Practical Example](#-practical-example)
- [📊 SAST vs SCA](#-sast-vs-sca)
- [✅ Best Practices](#-best-practices)
- [⚠️ Common Mistakes](#️-common-mistakes)
- [📝 Quick Revision](#-quick-revision)
- [🎤 Interview Questions](#-interview-questions)

---

# 📖 What is SCA?

Software Composition Analysis (SCA) scans an application's third-party libraries, frameworks, and open-source dependencies to identify known security vulnerabilities.

Instead of analyzing your source code, SCA analyzes the external packages your application depends on.

> [!NOTE]
> Modern applications often contain more third-party code than custom code, making dependency security critical.

---

# 🎯 Why SCA?

Using outdated or vulnerable dependencies can expose applications to serious security risks.

SCA helps organizations:

- Detect vulnerable dependencies.
- Identify outdated packages.
- Ensure license compliance.
- Reduce supply chain risks.
- Improve overall application security.

---

# 🔄 How SCA Works

```text
Developer Adds Dependency
          │
          ▼
 Git Push / Pull Request
          │
          ▼
      SCA Scanner
          │
          ▼
Analyzes Dependencies
          │
          ▼
Checks Vulnerability Database
          │
          ▼
Security Report
          │
          ▼
Update or Replace Dependency
```

SCA compares project dependencies against known vulnerability databases such as the **National Vulnerability Database (NVD)**.

---

# 🔍 What Does SCA Detect?

| Detects | Example |
|----------|---------|
| Vulnerable Dependencies | Old Log4j version |
| Outdated Packages | Unsupported library versions |
| Known CVEs | Publicly disclosed vulnerabilities |
| License Issues | GPL, MIT, Apache licenses |
| Transitive Dependencies | Vulnerabilities in nested packages |

---

# 🛠 Common SCA Tools

| Tool | Description |
|------|-------------|
| Dependabot | GitHub dependency updates |
| Snyk | Dependency vulnerability scanning |
| OWASP Dependency-Check | Open-source dependency scanner |
| Mend (WhiteSource) | Open-source security management |
| GitLab Dependency Scanning | Built-in GitLab security scanner |

---

# 💻 Practical Example

A project uses the following dependency:

```text
log4j-core:2.14.1
```

The SCA tool detects that this version contains **Log4Shell (CVE-2021-44228)**.

Security Report:

```text
Dependency: log4j-core
Version: 2.14.1
Severity: Critical
Recommendation:
Upgrade to the latest secure version.
```

The developer updates the dependency, eliminating the known vulnerability.

---

# 📊 SAST vs SCA

| SAST | SCA |
|------|-----|
| Scans source code | Scans third-party dependencies |
| Detects coding vulnerabilities | Detects dependency vulnerabilities |
| Focuses on custom code | Focuses on open-source libraries |
| Example: SQL Injection | Example: Vulnerable Log4j version |

---

# ✅ Best Practices

- Scan dependencies regularly.
- Keep libraries updated.
- Remove unused dependencies.
- Automate dependency scanning in CI/CD.
- Review license compliance.
- Monitor newly published CVEs.

---

# ⚠️ Common Mistakes

- Ignoring dependency updates.
- Using unsupported libraries.
- Installing unnecessary packages.
- Ignoring transitive dependencies.
- Running SCA only before release.

---

# 📝 Quick Revision

- SCA scans third-party dependencies.
- Detects known vulnerabilities and CVEs.
- Supports software supply chain security.
- Works best when automated in CI/CD.
- Dependabot and Snyk are popular SCA tools.

---

# 🎤 Interview Questions

### 1. What is Software Composition Analysis (SCA)?

**Answer:**

Software Composition Analysis (SCA) identifies vulnerabilities, outdated versions, and license issues in third-party libraries and open-source dependencies.

---

### 2. Why is SCA important?

**Answer:**

Modern applications rely heavily on open-source software. SCA helps detect vulnerable dependencies before they reach production.

---

### 3. What types of issues can SCA detect?

**Answer:**

- Vulnerable dependencies
- Known CVEs
- Outdated libraries
- License compliance issues
- Transitive dependency vulnerabilities

---

### 4. What is the difference between SAST and SCA?

**Answer:**

SAST scans your application's source code for coding vulnerabilities, while SCA scans third-party dependencies for known security vulnerabilities.

---

### 5. Name some popular SCA tools.

**Answer:**

- Dependabot
- Snyk
- OWASP Dependency-Check
- Mend (WhiteSource)
- GitLab Dependency Scanning

---

### 6. What is a CVE?

**Answer:**

A **Common Vulnerabilities and Exposures (CVE)** is a publicly disclosed security vulnerability with a unique identifier, making it easier to track and remediate known security issues.

---

# 📌 Key Takeaways

- SCA focuses on securing third-party libraries and dependencies.
- It identifies known vulnerabilities, outdated packages, and license issues.
- SCA is essential for software supply chain security.
- Integrating SCA into CI/CD enables continuous dependency monitoring.
- Keeping dependencies updated reduces security risks.

---

## ⏭️ Next

**➡️ 07-secrets-management.md**
