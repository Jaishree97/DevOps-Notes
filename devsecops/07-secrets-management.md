# 📘 Secrets Management

> **"Never hardcode secrets. Store them securely and access them safely."**

Secrets Management is the practice of securely storing, managing, rotating, and controlling access to sensitive information such as passwords, API keys, tokens, certificates, and encryption keys.

---

## 📑 Table of Contents

- [📖 What is Secrets Management?](#-what-is-secrets-management)
- [🎯 Why Secrets Management?](#-why-secrets-management)
- [🔑 Common Types of Secrets](#-common-types-of-secrets)
- [🔄 How Secrets Management Works](#-how-secrets-management-works)
- [🛠 Common Secrets Management Tools](#-common-secrets-management-tools)
- [💻 Practical Example](#-practical-example)
- [📊 Hardcoded Secrets vs Secrets Management](#-hardcoded-secrets-vs-secrets-management)
- [✅ Best Practices](#-best-practices)
- [⚠️ Common Mistakes](#️-common-mistakes)
- [📝 Quick Revision](#-quick-revision)
- [🎤 Interview Questions](#-interview-questions)

---

# 📖 What is Secrets Management?

Secrets Management is the process of securely storing and controlling access to sensitive information used by applications and infrastructure.

Examples include:

- Passwords
- API Keys
- Database Credentials
- Access Tokens
- SSH Keys
- TLS/SSL Certificates
- Encryption Keys

> [!NOTE]
> Secrets should **never** be stored in source code or committed to Git repositories.

---

# 🎯 Why Secrets Management?

Exposed secrets are one of the most common causes of security breaches.

Secrets Management helps:

- Prevent credential leaks.
- Protect sensitive data.
- Control who can access secrets.
- Rotate secrets regularly.
- Meet security and compliance requirements.

---

# 🔑 Common Types of Secrets

| Secret | Example |
|---------|---------|
| Password | Database password |
| API Key | OpenAI API Key |
| Access Token | GitHub Personal Access Token |
| SSH Key | Server authentication |
| Certificate | SSL/TLS certificate |
| Encryption Key | AES encryption key |

---

# 🔄 How Secrets Management Works

```text
Developer
     │
     ▼
Store Secret
(HashiCorp Vault / AWS Secrets Manager / GitHub Secrets)
     │
     ▼
Application Requests Secret
     │
     ▼
Identity Verification
     │
     ▼
Secret Retrieved Securely
     │
     ▼
Application Uses Secret
```

Applications retrieve secrets securely at runtime instead of storing them in code.

---

# 🛠 Common Secrets Management Tools

| Tool | Description |
|------|-------------|
| GitHub Secrets | Store secrets for GitHub Actions |
| HashiCorp Vault | Enterprise secrets management |
| AWS Secrets Manager | AWS-managed secret storage |
| Azure Key Vault | Secrets management for Azure |
| Google Secret Manager | Secrets management for GCP |
| Kubernetes Secrets | Store secrets in Kubernetes |
| Gitleaks | Detect hardcoded secrets |
| TruffleHog | Scan repositories for exposed secrets |

---

# 💻 Practical Example

❌ Hardcoded Secret

```python
API_KEY = "sk-123456789abcdef"
```

Anyone with access to the repository can see the secret.

---

✅ Environment Variable

```python
import os

API_KEY = os.getenv("API_KEY")
```

The secret is stored securely outside the application code.

---

Example in GitHub Actions:

```yaml
env:
  API_KEY: ${{ secrets.API_KEY }}
```

The secret is securely injected during workflow execution.

---

# 📊 Hardcoded Secrets vs Secrets Management

| Hardcoded Secrets | Secrets Management |
|-------------------|-------------------|
| Stored in source code | Stored securely |
| Easy to expose | Access controlled |
| Difficult to rotate | Easy to rotate |
| High security risk | More secure |
| Poor compliance | Supports compliance |

---

# ✅ Best Practices

- Never commit secrets to Git.
- Store secrets in dedicated secret managers.
- Rotate secrets regularly.
- Apply the Principle of Least Privilege (PoLP).
- Use environment variables whenever possible.
- Enable secret scanning in repositories.
- Remove unused or expired secrets.

---

# ⚠️ Common Mistakes

- Hardcoding passwords or API keys.
- Sharing secrets through email or chat.
- Using the same secret across multiple systems.
- Forgetting to rotate secrets.
- Granting excessive access to secrets.
- Ignoring secret scanning alerts.

---

# 📝 Quick Revision

- Secrets include passwords, API keys, tokens, and certificates.
- Never store secrets in source code.
- Use dedicated secret management tools.
- Rotate secrets regularly.
- Automate secret scanning in CI/CD.

---

# 🎤 Interview Questions

### 1. What is Secrets Management?

**Answer:**

Secrets Management is the process of securely storing, accessing, and rotating sensitive information such as passwords, API keys, tokens, and certificates.

---

### 2. Why should secrets never be hardcoded?

**Answer:**

Hardcoded secrets can be exposed through source code repositories, making them easy for attackers to steal and misuse.

---

### 3. Name some common secrets.

**Answer:**

- API Keys
- Passwords
- Access Tokens
- SSH Keys
- TLS/SSL Certificates
- Encryption Keys

---

### 4. What tools are commonly used for Secrets Management?

**Answer:**

- GitHub Secrets
- HashiCorp Vault
- AWS Secrets Manager
- Azure Key Vault
- Google Secret Manager
- Kubernetes Secrets

---

### 5. What tools detect exposed secrets?

**Answer:**

- Gitleaks
- TruffleHog
- GitHub Secret Scanning

---

### 6. How are secrets commonly used in CI/CD?

**Answer:**

Secrets are securely injected into pipelines using secret managers or environment variables instead of storing them directly in workflow files.

---

# 📌 Key Takeaways

- Secrets Management protects sensitive credentials from unauthorized access.
- Never hardcode secrets in source code.
- Use dedicated secret management solutions.
- Automate secret scanning and rotate secrets regularly.
- Proper Secrets Management is a critical part of DevSecOps.

---

## ⏭️ Next

**➡️ 08-dast.md**
