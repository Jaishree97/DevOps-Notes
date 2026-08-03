# 📘 Software Composition Analysis (SCA)

<p align="center">

> **"Secure your dependencies before they become your vulnerabilities."**

Analyze Open-Source Libraries • Detect Known Vulnerabilities • Secure the Software Supply Chain

</p>

---

## 📑 Table of Contents

- [📋 Chapter Information](#-chapter-information)
- [🎯 Learning Objectives](#-learning-objectives)
- [📚 Prerequisites](#-prerequisites)
- [📖 What is SCA?](#-what-is-sca)
- [🤔 Why SCA Matters](#-why-sca-matters)
- [⚙️ How SCA Works](#️-how-sca-works)
- [🔄 SCA Workflow](#-sca-workflow)
- [⚖️ SAST vs SCA](#️-sast-vs-sca)
- [🔍 What Can SCA Detect?](#-what-can-sca-detect)
- [🛠 Popular SCA Tools](#-popular-sca-tools)
- [💻 Hands-on Example](#-hands-on-example)
- [🚀 GitHub Actions Integration](#-github-actions-integration)
- [📌 Best Practices](#-best-practices)
- [❌ Common Mistakes](#-common-mistakes)
- [💡 Key Takeaways](#-key-takeaways)
- [🎤 Interview Questions](#-interview-questions)
- [📚 References](#-references)
- [📝 Summary](#-summary)

---

## 📋 Chapter Information

| Category | Details |
|-----------|----------|
| Difficulty | 🟢 Beginner |
| Reading Time | 15–20 Minutes |
| Hands-on | ✅ Yes |
| Interview Focus | ⭐⭐⭐⭐⭐ |

---

## 🎯 Learning Objectives

After completing this chapter, you will be able to:

- Explain Software Composition Analysis (SCA).
- Understand dependency vulnerabilities.
- Identify risks in open-source libraries.
- Use SCA tools to scan dependencies.
- Integrate SCA into CI/CD pipelines.

---

## 📚 Prerequisites

Before reading this chapter, you should understand:

- DevSecOps Basics
- Shift Left Security
- SAST
- Git & GitHub

---

## 📖 What is SCA?

**Software Composition Analysis (SCA)** is a security testing practice that analyzes an application's third-party libraries and open-source dependencies for known security vulnerabilities.

Modern applications rely heavily on external packages from ecosystems such as:

- npm
- pip
- Maven
- Gradle
- NuGet
- Go Modules

If one of these dependencies contains a known vulnerability, your application may also become vulnerable.

---

## 🤔 Why SCA Matters

Developers rarely write every line of code themselves.

Instead, applications often include hundreds or even thousands of open-source packages.

Example:

```text
Application
│
├── Flask
├── Requests
├── NumPy
├── Jinja2
└── urllib3
```

If one package has a published CVE, attackers may exploit it unless it is updated or replaced.

---

## ⚙️ How SCA Works

```text
Application
      │
      ▼
Dependency Manifest
(requirements.txt / package.json / pom.xml)
      │
      ▼
SCA Scanner
      │
      ├── Identify Packages
      ├── Check CVE Database
      ├── Report Vulnerabilities
      └── Recommend Updates
```

---

## 🔄 SCA Workflow

```text
Developer
     │
     ▼
Install Dependencies
     │
     ▼
Run SCA Scan
     │
     ▼
Identify Vulnerabilities
     │
     ▼
Upgrade Packages
     │
     ▼
Re-scan
     │
     ▼
Deploy
```

---

## ⚖️ SAST vs SCA

| SAST | SCA |
|------|-----|
| Scans your source code | Scans third-party libraries |
| Finds coding vulnerabilities | Finds vulnerable dependencies |
| No application execution required | No application execution required |
| Focuses on developer-written code | Focuses on external packages |

---

## 🔍 What Can SCA Detect?

SCA tools can identify:

- Known CVEs
- Outdated packages
- Vulnerable dependencies
- Transitive dependencies
- License issues
- End-of-life libraries

---

## 🛠 Popular SCA Tools

| Tool | Description |
|------|-------------|
| OWASP Dependency-Check | Open-source dependency scanner |
| Snyk | Cloud-native dependency security |
| GitHub Dependabot | Automated dependency updates |
| Trivy | Dependency and container scanning |
| Mend (WhiteSource) | Enterprise SCA platform |

---

## 💻 Hands-on Example

Suppose a Python project contains:

```text
requirements.txt

Flask==2.0.0
requests==2.25.0
```

Run a dependency scan using your preferred SCA tool.

The scanner compares package versions against known vulnerability databases and reports any issues.

Update affected packages and run the scan again to verify that the vulnerabilities have been resolved.

---

## 🚀 GitHub Actions Integration

```yaml
name: Dependency Scan

on:
  push:
  pull_request:

jobs:
  dependency-scan:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - name: Run Dependency Check
        run: echo "Run your preferred SCA tool here"
```

Replace the placeholder command with the SCA tool used in your environment.

---

## 📌 Best Practices

- Scan dependencies regularly.
- Keep packages updated.
- Remove unused libraries.
- Enable Dependabot or similar tools.
- Review transitive dependencies.
- Automate dependency scanning in CI/CD.

---

## ❌ Common Mistakes

- Ignoring dependency updates.
- Using unsupported libraries.
- Installing unnecessary packages.
- Running SCA only before production.
- Ignoring vulnerability reports.

---

## 💡 Key Takeaways

- SCA secures third-party dependencies.
- It detects known vulnerabilities before deployment.
- It supports Shift Left Security.
- It complements SAST rather than replacing it.
- Automated dependency scanning should be part of every CI/CD pipeline.

---

## 🎤 Interview Questions

1. What is Software Composition Analysis (SCA)?
2. Why is SCA important?
3. What is a dependency vulnerability?
4. How does SCA differ from SAST?
5. Name some popular SCA tools.
6. What are transitive dependencies?
7. How can SCA be integrated into GitHub Actions?

---

## 📚 References

- OWASP Dependency-Check Documentation
- GitHub Dependabot Documentation
- Snyk Documentation
- Trivy Documentation

---

## 📝 Summary

Software Composition Analysis (SCA) helps organizations identify and manage security risks introduced by third-party libraries and open-source dependencies. By continuously scanning dependencies, updating vulnerable packages, and integrating SCA into CI/CD pipelines, teams can reduce the risk of known vulnerabilities reaching production.

---

## 📚 Next Chapter

➡️ **07-secrets-management.md**

Learn how to protect API keys, passwords, tokens, and other sensitive information using secure secrets management practices.
