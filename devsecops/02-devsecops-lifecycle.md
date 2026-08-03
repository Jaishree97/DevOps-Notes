# 📘 DevSecOps Lifecycle

<p align="center">

> **"Security is not a checkpoint—it's a continuous process throughout the software development lifecycle."**

</p>

---

# 📑 Table of Contents

- [🎯 Learning Objectives](#-learning-objectives)
- [📖 What is the DevSecOps Lifecycle?](#-what-is-the-devsecops-lifecycle)
- [🏗 DevSecOps Lifecycle Overview](#-devsecops-lifecycle-overview)
- [1️⃣ Planning](#1️⃣-planning)
- [2️⃣ Coding](#2️⃣-coding)
- [3️⃣ Build](#3️⃣-build)
- [4️⃣ Testing](#4️⃣-testing)
- [5️⃣ Release](#5️⃣-release)
- [6️⃣ Deployment](#6️⃣-deployment)
- [7️⃣ Operations](#7️⃣-operations)
- [8️⃣ Monitoring](#8️⃣-monitoring)
- [🛠 Security Tools Across the Lifecycle](#-security-tools-across-the-lifecycle)
- [💻 Hands-on Example](#-hands-on-example)
- [🌍 Real-World Workflow](#-real-world-workflow)
- [🚀 Best Practices](#-best-practices)
- [⚠️ Common Mistakes](#️-common-mistakes)
- [💡 Key Takeaways](#-key-takeaways)
- [🎤 Interview Questions](#-interview-questions)
- [📝 Summary](#-summary)

---

# 🎯 Learning Objectives

After completing this chapter, you will be able to:

- Explain every phase of the DevSecOps lifecycle.
- Identify security activities performed at each stage.
- Understand how automation improves security.
- Recognize commonly used DevSecOps tools.

---

# 📖 What is the DevSecOps Lifecycle?

The **DevSecOps Lifecycle** is a continuous approach to software development where **security is integrated into every phase** of the Software Development Lifecycle (SDLC).

Instead of performing security checks only before deployment, security controls are applied continuously—from planning to production monitoring.

---

# 🏗 DevSecOps Lifecycle Overview

```text
                ┌────────────────────────────┐
                │ Continuous Monitoring      │
                └─────────────▲──────────────┘
                              │
Plan
 │
 ▼
Code
 │
 ▼
Build
 │
 ▼
Test
 │
 ▼
Release
 │
 ▼
Deploy
 │
 ▼
Operate
 │
 └────────────────────────────► Monitor
```

Every phase includes automated security checks and continuous feedback.

---

# 1️⃣ Planning

## Purpose

Define project requirements, architecture, risks, and security objectives before development begins.

### Security Activities

- Define security requirements
- Perform threat modeling
- Risk assessment
- Compliance planning
- Identify sensitive data

### Example

A banking application identifies that customer account numbers and passwords require encryption before development starts.

---

# 2️⃣ Coding

## Purpose

Develop secure application code.

### Security Activities

- Secure coding practices
- Secret management
- Code reviews
- Static code analysis (SAST)

### Example

Instead of hardcoding AWS credentials, developers use GitHub Secrets or a secret management service.

---

# 3️⃣ Build

## Purpose

Compile the application and prepare deployment artifacts.

### Security Activities

- Dependency scanning (SCA)
- SBOM generation
- Package validation
- Build verification

### Example

GitHub Actions automatically scans project dependencies for known vulnerabilities during every build.

---

# 4️⃣ Testing

## Purpose

Verify application quality and security before release.

### Security Activities

- Unit testing
- Integration testing
- Dynamic Application Security Testing (DAST)
- Container scanning

### Example

Trivy scans Docker images before publishing them.

---

# 5️⃣ Release

## Purpose

Prepare a secure release for deployment.

### Security Activities

- Artifact signing
- Release approval
- Security validation
- Version verification

Only approved and verified artifacts should move to production.

---

# 6️⃣ Deployment

## Purpose

Deploy applications securely to production environments.

### Security Activities

- Secure CI/CD pipelines
- Infrastructure validation
- Policy enforcement
- Least-privilege access

Deployment should be automated to reduce manual errors.

---

# 7️⃣ Operations

## Purpose

Keep applications running securely after deployment.

### Security Activities

- Patch management
- Configuration management
- Backup
- Vulnerability management

Operations teams ensure infrastructure remains secure and available.

---

# 8️⃣ Monitoring

## Purpose

Continuously observe applications and infrastructure for security events.

### Security Activities

- Log monitoring
- Alerting
- Intrusion detection
- Runtime security
- Incident response

Monitoring enables rapid detection and response to threats.

---

# 🛠 Security Tools Across the Lifecycle

| Stage | Common Tools |
|---------|--------------|
| Planning | Jira, Confluence, Threat Dragon |
| Coding | Git, GitHub, Semgrep, CodeQL |
| Build | Maven, Gradle, npm, Snyk |
| Testing | Trivy, OWASP ZAP |
| Release | Cosign, GitHub Releases |
| Deployment | GitHub Actions, Jenkins, Argo CD |
| Operations | Kubernetes, Docker |
| Monitoring | Prometheus, Grafana, Falco |

---

# 💻 Hands-on Example

A developer pushes code to GitHub.

```text
Developer
      │
      ▼
GitHub Repository
      │
      ▼
GitHub Actions
      │
      ├── Code Quality
      ├── Secret Scan
      ├── SAST
      ├── Dependency Scan
      ├── Build
      ├── Docker Image Scan
      └── Deploy
```

If any security check fails, the pipeline stops automatically.

---

# 🌍 Real-World Workflow

A fintech company follows this workflow:

- Plan security requirements
- Develop secure code
- Scan dependencies
- Scan Docker images
- Deploy using GitHub Actions
- Monitor production with Prometheus and Grafana
- Detect runtime threats using Falco

This approach helps deliver secure software continuously.

---

# 🚀 Best Practices

- Automate security checks.
- Scan every pull request.
- Keep dependencies updated.
- Apply least-privilege access.
- Monitor production continuously.
- Review security findings regularly.
- Integrate security early.

---

# ⚠️ Common Mistakes

- Treating security as the final step.
- Ignoring dependency vulnerabilities.
- Hardcoding secrets.
- Skipping image scans.
- Using outdated libraries.
- Disabling security checks to speed up releases.

---

# 💡 Key Takeaways

- Security exists in every lifecycle phase.
- Automation enables faster and more consistent security.
- Continuous monitoring is essential after deployment.
- Collaboration between developers, operations, and security teams is key.

---

# 🎤 Interview Questions

1. What is the DevSecOps Lifecycle?
2. Why is security integrated into every phase?
3. What happens during the Build stage?
4. What is the purpose of continuous monitoring?
5. Which tools are commonly used during Testing?
6. Why is dependency scanning important?
7. What security checks should run in a CI/CD pipeline?

---

# 📝 Summary

The DevSecOps Lifecycle embeds security into every stage of software delivery—from planning and coding to deployment and monitoring. By combining automation, collaboration, and continuous security practices, organizations can release software quickly while maintaining a strong security posture.

---

## 📚 Next Chapter

➡️ **03-shift-left-security.md**

Learn why identifying vulnerabilities early is one of the most effective ways to reduce security risks, development costs, and release delays.
