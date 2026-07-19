# GitHub Actions: Artifacts & Caching

Artifacts and caching are powerful features in GitHub Actions that improve workflow efficiency and reliability.

- **Artifacts** allow you to store and share files generated during workflow execution.
- **Caching** speeds up workflows by reusing dependencies between runs.

Both are commonly used in modern CI/CD pipelines to optimize build times and preserve important workflow outputs.

---

## Why Use Artifacts and Caching?

- Reduce workflow execution time.
- Share files between jobs.
- Preserve build outputs and reports.
- Avoid repeatedly downloading dependencies.
- Improve CI/CD pipeline performance and reliability.

---

## 1. Artifacts

Artifacts are files or directories produced during a workflow run that you want to preserve.

### Common Use Cases

- Build outputs
- Compiled binaries
- Test reports
- Application logs
- Deployment packages
- Coverage reports

Artifacts are uploaded using:

```yaml
actions/upload-artifact
```

Artifacts are downloaded using:

```yaml
actions/download-artifact
```

> **Note:** Artifacts are stored for 90 days by default (configurable).

---

## Uploading an Artifact

### Example

```yaml
steps:
  - name: Build Project
    run: npm run build

  - name: Upload Build Output
    uses: actions/upload-artifact@v4
    with:
      name: build-output
      path: dist/
      retention-days: 7
```

### Explanation

| Parameter | Description |
|----------|----------|
| name | Name of the artifact |
| path | File or directory to upload |
| retention-days | Number of days to retain the artifact |

---

## Downloading an Artifact

Artifacts can be downloaded in the same workflow by another job.

### Example

```yaml
jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - run: npm run build

      - uses: actions/upload-artifact@v4
        with:
          name: build-output
          path: dist/

  deploy:
    needs: build
    runs-on: ubuntu-latest

    steps:
      - name: Download Build Output
        uses: actions/download-artifact@v4
        with:
          name: build-output
          path: dist/

      - name: Deploy Application
        run: ./deploy.sh
```

### Workflow Execution Flow

```text
Build Job
    |
    v
Generate Files
    |
    v
Upload Artifact
    |
    v
Deploy Job
    |
    v
Download Artifact
    |
    v
Deploy Application
```

> **Important:** The artifact name must match during upload and download.

---

## 2. Caching

Caching stores dependencies between workflow runs.

Instead of downloading dependencies every time the workflow runs, GitHub restores them from the cache whenever possible.

### Common Use Cases

- Node.js packages
- Python packages
- Maven dependencies
- Docker layers
- Terraform plugins
- Package manager caches

Caching improves:

- Build speed
- Pipeline performance
- Resource utilization

---

## Cache Key Strategy

A cache key uniquely identifies cached data.

A good cache key should change whenever dependencies change.

### Example

```yaml
key: node-${{ runner.os }}-${{ hashFiles('package-lock.json') }}
```

GitHub automatically creates a new cache when:

- Dependency files change.
- Cache keys change.

---

## Caching Node.js Dependencies

### Example

```yaml
steps:
  - uses: actions/checkout@v4

  - name: Cache Node Modules
    uses: actions/cache@v4
    with:
      path: node_modules
      key: node-${{ runner.os }}-${{ hashFiles('package-lock.json') }}
      restore-keys: |
        node-${{ runner.os }}-

  - name: Install Dependencies
    run: npm install

  - name: Run Tests
    run: npm test
```

### Explanation

| Parameter | Purpose |
|---------|---------|
| path | Directory to cache |
| key | Unique cache identifier |
| restore-keys | Fallback cache keys |

---

## Caching Python Dependencies

### Example

```yaml
steps:
  - uses: actions/checkout@v4

  - name: Cache Pip Packages
    uses: actions/cache@v4
    with:
      path: ~/.cache/pip
      key: pip-${{ runner.os }}-${{ hashFiles('requirements.txt') }}
      restore-keys: |
        pip-${{ runner.os }}-

  - name: Install Dependencies
    run: pip install -r requirements.txt
```

---

## Cache Workflow

```text
Workflow Starts
      |
      v
Check Cache Key
      |
      v
Cache Found?
   /       \
 Yes        No
 |           |
Restore     Install Dependencies
 |           |
Skip         Create Cache
Installation |
      \     /
       v   v
    Continue Workflow
```

---

## Artifacts vs Cache

| Feature | Artifacts | Cache |
|--------|--------|--------|
| Purpose | Store generated files | Speed up workflows |
| Shared Between | Jobs and workflow runs | Workflow runs |
| Lifetime | Configurable (90 days default) | 7 days since last access |
| Best For | Build outputs and reports | Dependencies |
| Examples | dist/, logs, test reports | node_modules/, pip cache |

---

## When to Use Artifacts

Use artifacts when you want to:

- Preserve workflow outputs.
- Share files between jobs.
- Store deployment packages.
- Save logs and reports.

### Examples

```text
dist/
build/
coverage/
logs/
reports/
```

---

## When to Use Cache

Use cache when you want to:

- Reduce build time.
- Avoid downloading dependencies repeatedly.
- Improve CI/CD performance.

### Examples

```text
node_modules/
~/.cache/pip
.gradle/
.maven/
terraform plugin cache
```

---

## Best Practices

### Artifacts

- Use descriptive artifact names.
- Configure appropriate retention periods.
- Store only required files.
- Remove unnecessary large files.

### Cache

- Use `hashFiles()` for dependency-based cache invalidation.
- Keep cache keys predictable.
- Use `restore-keys` for fallback matching.
- Cache only frequently reused dependencies.

---

## Key Rules

- Artifact names should be unique within a workflow run.
- Cache keys are immutable.
- Use `hashFiles()` for automatic cache invalidation.
- Cache is not automatically shared across branches.
- Downloaded artifact names must match uploaded names.
- Use caching only for dependencies, not build outputs.

---

## Key Takeaways

- Artifacts preserve important workflow files.
- Caching significantly improves workflow speed.
- Artifacts are ideal for build outputs and reports.
- Cache is ideal for dependencies and package managers.
- Proper cache key design is essential.
- Using both features can greatly optimize CI/CD pipelines.

---

## Quick Summary

| Concept | Purpose |
|--------|--------|
| Artifacts | Store workflow-generated files |
| Upload Artifact | Save files after a workflow run |
| Download Artifact | Access saved files in other jobs |
| Cache | Reuse dependencies between runs |
| Cache Key | Identify cached data |
| restore-keys | Fallback cache matching |
| hashFiles() | Automatically invalidate cache |
| Best Practice | Use artifacts for outputs and cache for dependencies |
