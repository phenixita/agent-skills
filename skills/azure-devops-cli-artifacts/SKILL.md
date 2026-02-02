---
name: azure-devops-cli-artifacts
description: Manage Azure Artifacts universal packages with the CLI.
---

# Azure DevOps CLI - Artifacts

Publish and download Azure Artifacts universal packages.

**CLI Version:** 2.81.0 (current as of 2025)

## Prerequisites

```bash
# Install Azure DevOps extension
az extension add --name azure-devops
```

## Universal Packages

### Publish Package

```bash
az artifacts universal publish \
  --feed {feed-name} \
  --name {package-name} \
  --version {version} \
  --path {package-path} \
  --project {project}
```

### Download Package

```bash
az artifacts universal download \
  --feed {feed-name} \
  --name {package-name} \
  --version {version} \
  --path {download-path} \
  --project {project}
```
