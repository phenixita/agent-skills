---
name: azure-devops-cli-users
description: Manage Azure DevOps users with the CLI.
---

# Azure DevOps CLI - Users

Manage users in your Azure DevOps organization.

**CLI Version:** 2.81.0 (current as of 2025)

## Prerequisites

```bash
# Install Azure DevOps extension
az extension add --name azure-devops
```

## Users

```bash
# List users
az devops user list --org https://dev.azure.com/{org}
az devops user list --top 10 --output table

# Show user
az devops user show --user {user-id-or-email} --org https://dev.azure.com/{org}

# Add user
az devops user add \
  --email user@example.com \
  --license-type express \
  --org https://dev.azure.com/{org}

# Update user
az devops user update \
  --user {user-id-or-email} \
  --license-type advanced \
  --org https://dev.azure.com/{org}

# Remove user
az devops user remove --user {user-id-or-email} --org https://dev.azure.com/{org} --yes
```
