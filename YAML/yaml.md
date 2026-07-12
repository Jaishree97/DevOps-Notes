# 📘 YAML Notes & Cheat Sheet for DevOps

> **YAML (YAML Ain't Markup Language)** is a human-readable data serialization language used to write configuration files. It is the backbone of many DevOps tools such as **GitHub Actions, Docker Compose, Kubernetes, Ansible, Helm, GitLab CI, and Azure DevOps**.

---

# 📑 Table of Contents

- What is YAML?
- Why YAML?
- YAML Syntax
- Data Types
- Key-Value Pairs
- Lists
- Nested Objects
- Multi-line Strings
- Comments
- Anchors & Aliases
- Real DevOps Examples
- Common Mistakes
- Best Practices
- Interview Questions
- Quick Cheat Sheet
- Summary

---

# 🚀 What is YAML?

**YAML** stands for:

> **YAML Ain't Markup Language**

It is a **data serialization language** designed to be:

- Human-readable
- Easy to write
- Easy to maintain
- Perfect for configuration files

Unlike XML or JSON, YAML relies on **indentation** instead of brackets and commas.

---

# ❓ Why YAML?

YAML is widely used because it is:

- ✅ Clean and readable
- ✅ Easy to learn
- ✅ Lightweight
- ✅ Supports comments
- ✅ Ideal for configuration files
- ✅ Supported by almost every DevOps tool

---

# 🛠 Where YAML is Used

| Tool | Purpose |
|------|----------|
| GitHub Actions | CI/CD Pipelines |
| Docker Compose | Multi-container Applications |
| Kubernetes | Deployments, Pods & Services |
| Ansible | Configuration Management |
| Helm | Kubernetes Package Manager |
| GitLab CI | CI/CD |
| Azure DevOps | Pipelines |
| CircleCI | CI/CD |
| ArgoCD | GitOps |

---

# 🧩 YAML Data Types

```yaml
string: DevOps

integer: 10

float: 3.14

boolean: true

null_value: null

list:
  - Docker
  - Kubernetes

object:
  cloud: AWS
  region: ap-south-1
```

| Type | Example |
|------|---------|
| String | `"Hello"` |
| Integer | `10` |
| Float | `3.14` |
| Boolean | `true` |
| Null | `null` |
| List | `- Docker` |
| Object | `server:` |

---

# 🔑 Key-Value Pairs

The basic building block of YAML.

```yaml
name: MyApp
version: 1.0
language: Python
environment: Production
active: true
```

---

# 📋 Lists

## Block Style (Recommended)

```yaml
tools:
  - Git
  - Docker
  - Kubernetes
  - Terraform
```

## Inline Style

```yaml
tools: [Git, Docker, Kubernetes, Terraform]
```

✅ Use **block style** for better readability.

---

# 🏗 Nested Objects (Maps)

```yaml
server:
  name: web-server
  ip: 192.168.1.10
  port: 8080

database:
  host: localhost
  port: 3306

  credentials:
    username: admin
    password: secret
```

Hierarchy is created using **indentation**.

---

# 📝 Multi-line Strings

## Literal Style (`|`)

Preserves line breaks exactly.

```yaml
script: |
  echo "Starting..."
  docker build -t app .
  docker run app
```

Output

```
echo "Starting..."
docker build -t app .
docker run app
```

---

## Folded Style (`>`)

Converts line breaks into spaces.

```yaml
message: >
  Welcome to DevOps.
  YAML is easy
  to learn.
```

Output

```
Welcome to DevOps. YAML is easy to learn.
```

| Symbol | Use |
|---------|-----|
| `|` | Scripts, commands, certificates |
| `>` | Long descriptions |

---

# 💬 Comments

```yaml
# Application Configuration

app:
  name: DevOpsApp

# Database Settings
database:
  host: localhost
```

Comments start with **#**

---

# 🔗 Anchors & Aliases (Advanced)

Reuse the same configuration without repeating it.

```yaml
default: &default_settings
  retries: 3
  timeout: 30

app1:
  <<: *default_settings

app2:
  <<: *default_settings
```

Useful for large configuration files.

---

# 🚀 Real DevOps Examples

## GitHub Actions

```yaml
name: CI Pipeline

on:
  push:
    branches:
      - main

jobs:
  build:

    runs-on: ubuntu-latest

    steps:

      - uses: actions/checkout@v4

      - name: Print Message
        run: echo "Hello DevOps!"
```

---

## Docker Compose

```yaml
version: "3.9"

services:

  web:

    image: nginx

    ports:
      - "80:80"
```

---

## Kubernetes Deployment

```yaml
apiVersion: apps/v1

kind: Deployment

metadata:
  name: nginx

spec:

  replicas: 3

  selector:

    matchLabels:
      app: nginx

  template:

    metadata:

      labels:
        app: nginx

    spec:

      containers:

      - name: nginx

        image: nginx
```

---

# ⚠️ Common Mistakes

## ❌ Missing Space

Wrong

```yaml
name:DevOps
```

Correct

```yaml
name: DevOps
```

---

## ❌ Using Tabs

Wrong

```yaml
server:
	name: app
```

Correct

```yaml
server:
  name: app
```

Always use **spaces**.

---

## ❌ Wrong Indentation

Wrong

```yaml
database:
host: localhost
```

Correct

```yaml
database:
  host: localhost
```

---

# 📏 YAML Rules

- Use spaces only
- Never use tabs
- YAML is case-sensitive
- Indentation defines hierarchy
- Keys must be unique
- Comments begin with `#`

---

# ⭐ Best Practices

- Use **2-space indentation**
- Keep keys meaningful
- Prefer block lists
- Keep files organized
- Add comments where useful
- Avoid unnecessary quotes
- Validate YAML before deployment
- Store secrets securely (don't hard-code passwords)

---

# 🔍 Interview Questions

### What is YAML?

A human-readable data serialization language used for configuration files.

---

### Why is YAML popular in DevOps?

Because it is simple, readable, lightweight, and supported by most automation tools.

---

### Difference between YAML and JSON?

| YAML | JSON |
|------|------|
| Human-readable | Machine-friendly |
| Supports comments | No comments |
| Uses indentation | Uses brackets and commas |

---

### Difference between `|` and `>`?

| `|` | `>` |
|-----|-----|
| Preserves new lines | Folds lines into spaces |

---

### Why is indentation important?

Because YAML uses indentation to define hierarchy. Incorrect indentation makes the file invalid.

---

# 📚 Quick Cheat Sheet

| Feature | Example |
|----------|---------|
| Key-Value | `name: DevOps` |
| Boolean | `enabled: true` |
| Integer | `replicas: 3` |
| List | `- Docker` |
| Inline List | `[Git, Docker]` |
| Object | `server:` |
| Comment | `# Comment` |
| Literal Block | `|` |
| Folded Block | `>` |
| Anchor | `&default` |
| Alias | `*default` |

---

# 🧠 Revision Tips

✅ Use **spaces**, never tabs.

✅ Remember:

```
:  → Key-Value

-  → List

#  → Comment

|  → Preserve formatting

>  → Fold text
```

---

# 📌 Summary

YAML is one of the most important configuration languages in modern DevOps. Understanding its syntax, indentation, data structures, and best practices is essential for working with tools like GitHub Actions, Docker Compose, Kubernetes, Ansible, and Helm.

---

# 🎯 Key Takeaways

- YAML uses indentation instead of brackets.
- Spaces matter—never use tabs.
- Keep configuration clean and readable.
- Validate YAML files before deployment.
- Learn YAML once and use it across the entire DevOps ecosystem.

---

> 💡 **Pro Tip:** One missing space can break an entire deployment. Always validate your YAML before committing it.
