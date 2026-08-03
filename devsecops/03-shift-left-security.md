# 📘 Shift Left Security

> **"The earlier you find a vulnerability, the cheaper and easier it is to fix."**

Shift Left Security is a DevSecOps practice of moving security activities earlier ("to the left") in the Software Development Lifecycle (SDLC), allowing teams to identify and fix vulnerabilities before they reach production.

---

## 📑 Table of Contents

- [📖 What is Shift Left Security?](#-what-is-shift-left-security)
- [❓ Why Shift Left Security?](#-why-shift-left-security)
- [📊 Traditional vs Shift Left Approach](#-traditional-vs-shift-left-approach)
- [🔄 How Shift Left Works](#-how-shift-left-works)
- [🛠 Common Security Practices](#-common-security-practices)
- [💻 Practical Example](#-practical-example)
- [✅ Best Practices](#-best-practices)
- [⚠️ Common Mistakes](#️-common-mistakes)
- [📝 Quick Revision](#-quick-revision)
- [🎤 Interview Questions](#-interview-questions)

---

# 📖 What is Shift Left Security?

Shift Left Security means performing security activities as early as possible during software development instead of waiting until deployment or production.

By identifying vulnerabilities early, developers can fix issues faster, reduce costs, and improve software quality.

> [!NOTE]
> Shift Left doesn't mean **doing security only at the beginning**—it means **starting security early and continuing it throughout the SDLC.**

---

# ❓ Why Shift Left Security?

Finding security issues late can lead to:

- Expensive fixes
- Delayed releases
- Security breaches
- Compliance failures
- Poor customer trust

By shifting security left, organizations can detect and resolve issues before they become critical.

---

# 📊 Traditional vs Shift Left Approach

## Traditional Security

```text
Plan → Code → Build → Test → Deploy → Security ❌
```

Security is performed only before deployment.

---

## Shift Left Security

```text
                  🔒 Security
                       ▲
                       │
Plan → Code → Build → Test → Release → Deploy → Monitor
```

Security starts early and continues throughout the SDLC.

---

# 🔄 How Shift Left Works

```text
Developer Writes Code
          │
          ▼
Code Review
          │
          ▼
SAST Scan
          │
          ▼
Dependency Scan (SCA)
          │
          ▼
Secret Scan
          │
          ▼
CI/CD Pipeline
          │
          ▼
Deploy
```

Every code change is automatically validated before deployment.

---

# 🛠 Common Security Practices

| Stage | Security Practice |
|--------|-------------------|
| Planning | Threat Modeling |
| Coding | Secure Coding Standards |
| Commit | Secret Scanning |
| Build | SAST, SCA |
| Test | Security Testing |
| Deploy | IaC & Container Scanning |
| Production | Monitoring & Logging |

---

# 💻 Practical Example

A developer accidentally commits an API key.

Without Shift Left:

```text
Developer
    │
Git Push
    │
Production ❌
    │
Security Team finds issue later
```

With Shift Left:

```text
Developer
    │
Git Push
    │
GitHub Actions
    │
├── Secret Scan ❌
├── SAST
└── Dependency Scan
    │
Pipeline Failed
    │
Developer fixes issue
```

The application is never deployed with the exposed secret.

---

# ✅ Benefits of Shift Left Security

- Detect vulnerabilities early.
- Reduce remediation costs.
- Improve software quality.
- Faster and safer releases.
- Automate security checks.
- Encourage developer ownership of security.

---

# ✅ Best Practices

- Automate security testing.
- Scan every Pull Request.
- Use secure coding guidelines.
- Review code regularly.
- Keep dependencies updated.
- Educate developers on secure coding.
- Integrate security into CI/CD.

---

# ⚠️ Common Mistakes

- Treating Shift Left as a one-time activity.
- Relying only on manual security testing.
- Ignoring failed security scans.
- Hardcoding secrets.
- Skipping dependency scanning.
- Delaying vulnerability fixes.

---

# 📝 Quick Revision

- Shift Left = Perform security early.
- Earlier detection = Lower remediation cost.
- Security starts during development.
- CI/CD automates security validation.
- Developers share responsibility for security.
- Shift Left improves both speed and security.

---

# 🎤 Interview Questions

### 1. What is Shift Left Security?

**Answer:**

Shift Left Security is the practice of integrating security earlier into the SDLC so vulnerabilities are detected and fixed before deployment.

---

### 2. Why is Shift Left Security important?

**Answer:**

It reduces remediation costs, improves software quality, accelerates delivery, and minimizes security risks by identifying vulnerabilities early.

---

### 3. How does Shift Left Security support DevSecOps?

**Answer:**

Shift Left is a core DevSecOps principle that embeds automated security testing into every stage of software development.

---

### 4. Name some tools commonly used for Shift Left Security.

**Answer:**

- SonarQube
- Semgrep
- CodeQL
- Snyk
- Dependabot
- Gitleaks
- Trivy
- Checkov

---

### 5. What types of security scans are commonly performed early?

**Answer:**

- Static Application Security Testing (SAST)
- Software Composition Analysis (SCA)
- Secret Scanning
- Infrastructure as Code (IaC) Scanning
- Container Image Scanning

---

### 6. Does Shift Left Security replace security after deployment?

**Answer:**

No. Shift Left starts security earlier but security must continue after deployment through monitoring, logging, runtime protection, and incident response.

---

# 📌 Key Takeaways

- Shift Left Security is a core principle of DevSecOps.
- Security begins during planning and development—not after deployment.
- Automated security scans help detect vulnerabilities early.
- Earlier fixes reduce cost, effort, and security risks.
- Shift Left improves both software quality and delivery speed.

---

## ⏭️ Next

**➡️ 04-threat-modeling.md**
