# 📘 Threat Modeling

> **"Think like an attacker before an attacker thinks like you."**

Threat Modeling is the process of identifying potential security threats, vulnerabilities, and attack paths during the design phase of an application so they can be mitigated before development begins.

---

## 📑 Table of Contents

- [📖 What is Threat Modeling?](#-what-is-threat-modeling)
- [🎯 Why Threat Modeling?](#-why-threat-modeling)
- [🔄 Threat Modeling Process](#-threat-modeling-process)
- [🛡 STRIDE Threat Model](#-stride-threat-model)
- [🛠 Common Tools](#-common-tools)
- [💻 Practical Example](#-practical-example)
- [✅ Best Practices](#-best-practices)
- [⚠️ Common Mistakes](#️-common-mistakes)
- [📝 Quick Revision](#-quick-revision)
- [🎤 Interview Questions](#-interview-questions)

---

# 📖 What is Threat Modeling?

Threat Modeling is a proactive security practice used to identify potential threats and vulnerabilities before an application is developed or deployed.

It helps development teams understand:

- What needs protection?
- Who could attack it?
- How could it be attacked?
- How can those attacks be prevented?

> [!NOTE]
> Threat Modeling is performed during the **planning and design phase**, making it an important Shift Left Security practice.

---

# 🎯 Why Threat Modeling?

Without Threat Modeling:

- Security risks may be overlooked.
- Design flaws become expensive to fix later.
- Applications become easier to attack.

Threat Modeling helps teams design secure applications from the beginning.

---

# 🔄 Threat Modeling Process

```text
Identify Assets
       │
       ▼
Identify Threats
       │
       ▼
Analyze Risks
       │
       ▼
Plan Mitigations
       │
       ▼
Implement Security Controls
```

This process is repeated whenever new features or architecture changes are introduced.

---

# 🛡 STRIDE Threat Model

STRIDE is Microsoft's popular Threat Modeling framework.

| Threat | Description | Example |
|---------|-------------|---------|
| **S - Spoofing** | Pretending to be another user | Stolen login credentials |
| **T - Tampering** | Modifying data | Changing database records |
| **R - Repudiation** | Denying performed actions | User denies making a transaction |
| **I - Information Disclosure** | Exposing sensitive data | Leaking passwords or API keys |
| **D - Denial of Service (DoS)** | Making services unavailable | Flooding a server with requests |
| **E - Elevation of Privilege** | Gaining higher permissions | Normal user becomes administrator |

---

# 🛠 Common Tools

| Tool | Purpose |
|------|---------|
| Microsoft Threat Modeling Tool | Create threat models |
| OWASP Threat Dragon | Open-source threat modeling |
| Draw.io | Architecture diagrams |
| Lucidchart | System diagrams |
| Miro | Collaborative design sessions |

---

# 💻 Practical Example

Suppose you're designing an Online Banking Application.

```text
User
 │
 ▼
Login Page
 │
 ▼
Application Server
 │
 ▼
Database
```

Possible threats:

- Stolen user credentials (Spoofing)
- SQL Injection (Tampering)
- Data leakage (Information Disclosure)
- DDoS attack (Denial of Service)

Possible mitigations:

- Multi-Factor Authentication (MFA)
- Input validation
- Encryption
- Rate limiting
- Web Application Firewall (WAF)

---

# ✅ Best Practices

- Perform Threat Modeling during application design.
- Include developers, security, and operations teams.
- Update threat models whenever the architecture changes.
- Prioritize high-risk threats.
- Document mitigation strategies.
- Review threat models regularly.

---

# ⚠️ Common Mistakes

- Skipping Threat Modeling.
- Considering only external attackers.
- Ignoring insider threats.
- Not updating threat models.
- Focusing only on technical risks.
- Failing to document identified threats.

---

# 📝 Quick Revision

- Threat Modeling identifies security risks before development.
- It is a Shift Left Security practice.
- STRIDE is the most commonly used Threat Modeling framework.
- The goal is to identify threats and define mitigations early.
- Threat Modeling reduces security risks and development costs.

---

# 🎤 Interview Questions

### 1. What is Threat Modeling?

**Answer:**

Threat Modeling is the process of identifying potential threats, vulnerabilities, and attack paths during the design phase of an application so they can be mitigated before development begins.

---

### 2. Why is Threat Modeling important?

**Answer:**

It helps identify security risks early, reduces remediation costs, improves application design, and supports secure software development.

---

### 3. When should Threat Modeling be performed?

**Answer:**

Threat Modeling should be performed during the planning and design phase and updated whenever the application's architecture changes.

---

### 4. What is STRIDE?

**Answer:**

STRIDE is a Threat Modeling framework developed by Microsoft that categorizes threats into:

- Spoofing
- Tampering
- Repudiation
- Information Disclosure
- Denial of Service
- Elevation of Privilege

---

### 5. Name some Threat Modeling tools.

**Answer:**

- Microsoft Threat Modeling Tool
- OWASP Threat Dragon
- Draw.io
- Lucidchart
- Miro

---

### 6. Is Threat Modeling a one-time activity?

**Answer:**

No. Threat Modeling is an ongoing process and should be updated whenever new features, services, or architecture changes are introduced.

---

# 📌 Key Takeaways

- Threat Modeling is a proactive security practice.
- It identifies threats before development begins.
- STRIDE is one of the most widely used Threat Modeling frameworks.
- Early threat identification reduces security risks and remediation costs.
- Threat Modeling is a key component of Shift Left Security and DevSecOps.

---

## ⏭️ Next

**➡️ 05-sast.md**
