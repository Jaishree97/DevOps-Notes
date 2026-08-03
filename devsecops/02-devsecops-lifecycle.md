# 📘 DevSecOps Lifecycle

> **"Secure every stage of the Software Development Lifecycle (SDLC)."**

The DevSecOps lifecycle integrates security into every phase of software development, from planning to monitoring. Instead of treating security as a final checkpoint, DevSecOps makes it a continuous process.

---

## 📑 Table of Contents

- [📖 What is the DevSecOps Lifecycle?](#-what-is-the-devsecops-lifecycle)
- [🔄 Lifecycle Stages](#-lifecycle-stages)
- [🛡 Security Activities at Each Stage](#-security-activities-at-each-stage)
- [🛠 Common Tools](#-common-tools)
- [💻 Example Workflow](#-example-workflow)
- [✅ Best Practices](#-best-practices)
- [⚠️ Common Mistakes](#️-common-mistakes)
- [📝 Quick Revision](#-quick-revision)
- [🎤 Interview Questions](#-interview-questions)

---

# 📖 What is the DevSecOps Lifecycle?

The **DevSecOps Lifecycle** is a software development approach where **security is integrated into every stage of the Software Development Lifecycle (SDLC)**.

Instead of performing security checks only before deployment, every stage includes automated security practices to identify and fix vulnerabilities as early as possible.

> [!NOTE]
> The goal is to **build secure software continuously**, not secure software only before release.

---

# 🔄 Lifecycle Stages

```text
                   🔒 Security
                        ▲
                        │
Plan → Code → Build → Test → Release → Deploy → Monitor
                        │
                Continuous Feedback
```

> [!IMPORTANT]
> Security is **not a separate stage** in DevSecOps. It is integrated into every stage of the SDLC through automation, continuous testing, and monitoring.

---

# 🛡 Security Activities at Each Stage

| Stage | Purpose | Security Activities |
|--------|---------|---------------------|
| 📋 Plan | Define project requirements | Threat modeling, security requirements, risk assessment |
| 💻 Code | Develop application | Secure coding, code reviews, secret scanning |
| 🏗 Build | Compile application | SAST, dependency scanning (SCA) |
| 🧪 Test | Validate functionality | Security testing, vulnerability scanning |
| 🚀 Release | Prepare deployment | Policy validation, artifact signing |
| ☁️ Deploy | Deploy application | IaC scanning, container security, secure configuration |
| 📊 Monitor | Monitor production | Logging, runtime monitoring, alerting |
| 🔁 Feedback | Continuous improvement | Patch vulnerabilities, improve security policies |

---

# 🛠 Common Tools

| Stage | Popular Tools |
|--------|---------------|
| Plan | Jira, Confluence |
| Code | Git, GitHub, GitLab |
| Build | GitHub Actions, Jenkins, GitLab CI |
| SAST | SonarQube, Semgrep, CodeQL |
| SCA | Snyk, Dependabot, OWASP Dependency-Check |
| Secret Scanning | Gitleaks, TruffleHog |
| Container Security | Trivy, Docker Scout, Grype |
| IaC Security | Checkov, tfsec, Terrascan |
| Monitoring | Prometheus, Grafana, Falco |

---

# 💻 Example Workflow

A developer pushes new code to GitHub.

```text
Developer
    │
 Git Push
    │
GitHub Actions
    │
├── Build
├── Unit Tests
├── SAST
├── Dependency Scan
├── Secret Scan
├── Container Scan
└── IaC Scan
    │
Deploy
    │
Monitor
```

If any security check fails, the pipeline stops until the issue is resolved.

---

# ✅ Best Practices

- Integrate security from the planning stage.
- Automate security scans in CI/CD pipelines.
- Scan every Pull Request.
- Keep dependencies updated.
- Never hardcode secrets.
- Apply the Principle of Least Privilege (PoLP).
- Continuously monitor production environments.
- Fix vulnerabilities as early as possible.

---

# ⚠️ Common Mistakes

- Treating security as the final step.
- Ignoring failed security scans.
- Hardcoding credentials or API keys.
- Using outdated dependencies or container images.
- Skipping production monitoring.
- Delaying vulnerability remediation.

---

# 📝 Quick Revision

- DevSecOps integrates security throughout the SDLC.
- Every SDLC stage includes security activities.
- CI/CD automates security testing.
- Security is a shared responsibility.
- Continuous monitoring helps detect and respond to threats.
- Early detection reduces cost and improves software quality.

---

# 🎤 Interview Questions

### 1. What is the DevSecOps lifecycle?

**Answer:**

The DevSecOps lifecycle integrates security into every stage of the Software Development Lifecycle (SDLC). Security is continuously applied from planning and coding to deployment and monitoring through automation and collaboration.

---

### 2. Why should security be integrated into every SDLC stage?

**Answer:**

Integrating security early helps detect vulnerabilities sooner, reduces remediation costs, speeds up software delivery, and minimizes security risks in production.

---

### 3. What security activities happen during the Build stage?

**Answer:**

During the Build stage, automated security checks such as:

- SAST (Static Application Security Testing)
- SCA (Software Composition Analysis)
- Dependency Scanning
- Build Artifact Validation

are commonly performed.

---

### 4. Which tools are commonly used for SAST and SCA?

**Answer:**

**SAST Tools**

- SonarQube
- Semgrep
- CodeQL

**SCA Tools**

- Snyk
- Dependabot
- OWASP Dependency-Check

---

### 5. Why is monitoring important in DevSecOps?

**Answer:**

Monitoring helps detect security incidents, suspicious activities, performance issues, and vulnerabilities after deployment. It enables faster response and continuous improvement.

---

### 6. How does CI/CD support the DevSecOps lifecycle?

**Answer:**

CI/CD automates security checks such as code analysis, dependency scanning, secret detection, container scanning, and IaC scanning before deployment, ensuring only secure code reaches production.

---

# 📌 Key Takeaways

- DevSecOps embeds security into every phase of the SDLC.
- Security is continuous, automated, and collaborative.
- CI/CD pipelines automate security validation.
- Early vulnerability detection reduces cost and risk.
- Continuous monitoring strengthens application security over time.

---

## ⏭️ Next

**➡️ 03-shift-left-security.md**
