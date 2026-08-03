# 📘 Shift Left Security

<p align="center">

> **"The earlier you find a vulnerability, the cheaper and easier it is to fix."**

Build Security Early • Reduce Risk • Deliver Faster

</p>

---

## 📑 Table of Contents

- [🎯 Learning Objectives](#-learning-objectives)
- [📖 What is Shift Left Security?](#-what-is-shift-left-security)
- [🤔 Why Shift Left Matters](#-why-shift-left-matters)
- [📜 Evolution of Security Testing](#-evolution-of-security-testing)
- [⚖️ Traditional vs Shift Left Security](#️-traditional-vs-shift-left-security)
- [💰 Cost of Fixing Vulnerabilities](#-cost-of-fixing-vulnerabilities)
- [🔄 Shift Left Across the SDLC](#-shift-left-across-the-sdlc)
- [🛠 Security Activities at Each Stage](#-security-activities-at-each-stage)
- [🚀 Benefits of Shift Left Security](#-benefits-of-shift-left-security)
- [⚠️ Challenges](#️-challenges)
- [🌍 Real-World Example](#-real-world-example)
- [💻 Hands-on Activity](#-hands-on-activity)
- [📌 Best Practices](#-best-practices)
- [❌ Common Mistakes](#-common-mistakes)
- [🎤 Interview Questions](#-interview-questions)
- [📝 Summary](#-summary)

---

# 🎯 Learning Objectives

After completing this chapter, you will be able to:

- Explain Shift Left Security.
- Understand why security should begin early.
- Compare traditional security with Shift Left Security.
- Identify security activities performed during each SDLC phase.
- Understand how Shift Left fits into CI/CD pipelines.

---

# 📖 What is Shift Left Security?

**Shift Left Security** is the practice of moving security activities earlier (to the left) in the Software Development Lifecycle (SDLC).

Instead of waiting until the application is ready for deployment, security checks are performed from the planning and development stages onward.

The goal is simple:

> **Find vulnerabilities early, fix them quickly, and prevent them from reaching production.**

---

# 🤔 Why Shift Left Matters

Imagine finding a security bug:

- During coding → Fix takes minutes.
- During testing → Fix takes hours.
- After deployment → Fix may take days or weeks.

The later a vulnerability is discovered, the more expensive and risky it becomes.

Shift Left Security helps reduce:

- Development cost
- Release delays
- Security incidents
- Business risk
- Customer impact

---

# 📜 Evolution of Security Testing

## Traditional Approach

```text
Planning
    │
Coding
    │
Build
    │
Testing
    │
Deployment
    │
Security Testing ❌
```

Security happens only at the end.

---

## Shift Left Security

```text
Security
    │
Planning
    │
Coding
    │
Build
    │
Testing
    │
Deployment
    │
Monitoring
```

Security is integrated into every phase.

---

# ⚖️ Traditional vs Shift Left Security

| Traditional Security | Shift Left Security |
|----------------------|---------------------|
| Security at the end | Security from the beginning |
| Manual testing | Automated testing |
| Late feedback | Early feedback |
| Expensive fixes | Lower-cost fixes |
| Higher deployment risk | Reduced deployment risk |

---

# 💰 Cost of Fixing Vulnerabilities

The later a vulnerability is discovered, the more expensive it becomes to fix.

| Stage | Relative Cost |
|--------|--------------:|
| Planning | Very Low |
| Development | Low |
| Build | Medium |
| Testing | High |
| Production | Very High |

**Example:**

Fixing an SQL injection during development may take a few minutes.

Fixing the same issue after production may require:

- Emergency patches
- Service downtime
- Customer notifications
- Security investigations

---

# 🔄 Shift Left Across the SDLC

```text
Planning
│
├── Threat Modeling
├── Security Requirements
│
▼
Coding
│
├── Secure Coding
├── Secret Scanning
├── SAST
│
▼
Build
│
├── Dependency Scan
├── SBOM Generation
│
▼
Testing
│
├── DAST
├── Container Scan
│
▼
Deployment
│
├── IaC Validation
├── Policy Checks
│
▼
Monitoring
│
├── Runtime Security
├── Alerts
└── Incident Response
```

---

# 🛠 Security Activities at Each Stage

| Stage | Security Activity |
|--------|-------------------|
| Planning | Threat Modeling |
| Coding | Secure Coding, SAST |
| Build | Dependency Scanning |
| Testing | DAST, Container Scanning |
| Deployment | IaC Security, Policy Validation |
| Monitoring | Runtime Monitoring, Alerts |

---

# 🚀 Benefits of Shift Left Security

- Detect vulnerabilities earlier.
- Reduce remediation costs.
- Improve software quality.
- Increase developer awareness.
- Enable secure CI/CD pipelines.
- Reduce production incidents.
- Accelerate secure releases.

---

# ⚠️ Challenges

Organizations adopting Shift Left may face:

- Learning new tools.
- Cultural resistance.
- False positives from scanners.
- Developer training requirements.
- Integrating security into existing pipelines.

---

# 🌍 Real-World Example

A developer accidentally commits an AWS Access Key.

### Without Shift Left

```text
Developer
    │
GitHub
    │
Deploy
    │
Production

❌ Secret exposed.
```

The secret reaches production before anyone notices.

---

### With Shift Left

```text
Developer
    │
GitHub
    │
GitHub Actions
    │
├── Secret Scan ✅
├── SAST ✅
├── Dependency Scan ✅
│
Pipeline Stops ❌
```

The pipeline blocks the deployment until the issue is fixed.

---

# 💻 Hands-on Activity

## Objective

Understand how secret scanning supports Shift Left Security.

### Scenario

A developer accidentally commits a fake API key.

### Steps

1. Create a sample project.
2. Add a fake secret to a `.env` file.
3. Commit the file locally.
4. Run a secret scanning tool such as **Gitleaks**.
5. Review the findings.
6. Remove the secret.
7. Scan again to confirm the issue is resolved.

**Expected Outcome**

- Detect the exposed secret before deployment.
- Understand why automated scanning is part of modern CI/CD pipelines.

---

# 📌 Best Practices

- Scan every pull request.
- Use secure coding standards.
- Automate security testing.
- Protect secrets with a secret manager.
- Keep dependencies updated.
- Include security in code reviews.
- Educate developers on secure coding practices.

---

# ❌ Common Mistakes

- Treating security as a final checkpoint.
- Ignoring automated scan results.
- Hardcoding credentials.
- Delaying vulnerability fixes.
- Skipping dependency updates.

---

# 🎤 Interview Questions

1. What is Shift Left Security?
2. Why is Shift Left important in DevSecOps?
3. How does Shift Left reduce costs?
4. What security checks can be performed during development?
5. Give examples of Shift Left tools.
6. How does GitHub Actions support Shift Left Security?
7. What challenges do organizations face when adopting Shift Left?

---

# 📝 Summary

Shift Left Security is a foundational DevSecOps practice that moves security activities to the earliest stages of the software development lifecycle. By integrating automated security checks into planning, coding, building, and testing, teams can identify and fix vulnerabilities before they reach production.

This approach reduces cost, minimizes risk, improves collaboration, and enables organizations to deliver software that is both fast and secure.

---

## 📚 Next Chapter

➡️ **04-threat-modeling.md**

Learn how to identify potential threats, analyze risks, and design secure systems before writing a single line of code.
