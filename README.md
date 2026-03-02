# Service Ports Registry – Git Workflow Automation

This repository is used to practice advanced Git workflow automation using GitHub Actions.

It automatically:

- Syncs `main` branch to multiple deployment branches
- Builds Docker image
- Pushes image to GitHub Container Registry (GHCR)

---

## 🔄 Workflow: Sync Branch

Trigger:
- On push to `main`

---

## 🚀 What This Pipeline Does

When code is pushed to `main`:

### 1️⃣ Sync Branches
Force push `main` into:

- `main-site-A`
- `main-site-B`

This simulates deploying the same source to multiple environments.


---

### 2️⃣ Prepare Repository Name (Lowercase)

GHCR requires lowercase image names.


---

### 3️⃣ Login to GHCR

Uses:

- `GITHUB_TOKEN`
- GitHub Actor



### 4️⃣ Build Docker Image



### 5️⃣ Push Docker Image



## 🐳 Docker Image Location

Image is pushed to:

You can view it in:

GitHub → Packages → Container Registry

---

## 🔐 Permissions Used

```yaml
permissions:
  contents: write
  packages: write
```
📌 Notes

Repository name must be lowercase for GHCR

Force push will overwrite target branches

Ensure branch protection rules are configured if used in production
