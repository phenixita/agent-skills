---
name: azure-devops-cli-admin
description: Azure DevOps administration commands such as banners and marketplace extensions.
---

# Azure DevOps CLI - Admin

Administration tasks like banners and DevOps extensions.

**CLI Version:** 2.81.0 (current as of 2025)

## Prerequisites

```bash
# Install Azure DevOps extension
az extension add --name azure-devops
```

## Banner Management

```bash
# List banners
az devops admin banner list

# Show banner details
az devops admin banner show --id {banner-id}

# Add new banner
az devops admin banner add \
  --message "System maintenance scheduled" \
  --level info  # info, warning, error

# Update banner
az devops admin banner update \
  --id {banner-id} \
  --message "Updated message" \
  --level warning \
  --expiration-date "2025-12-31T23:59:59Z"

# Remove banner
az devops admin banner remove --id {banner-id}
```

## DevOps Extensions

Manage extensions installed in an Azure DevOps organization (different from CLI extensions).

```bash
# List installed extensions
az devops extension list --org https://dev.azure.com/{org}

# Search marketplace extensions
az devops extension search --search-query "docker"

# Show extension details
az devops extension show --ext-id {extension-id} --org https://dev.azure.com/{org}

# Install extension
az devops extension install \
  --ext-id {extension-id} \
  --org https://dev.azure.com/{org} \
  --publisher {publisher-id}

# Enable extension
az devops extension enable \
  --ext-id {extension-id} \
  --org https://dev.azure.com/{org}

# Disable extension
az devops extension disable \
  --ext-id {extension-id} \
  --org https://dev.azure.com/{org}

# Uninstall extension
az devops extension uninstall \
  --ext-id {extension-id} \
  --org https://dev.azure.com/{org} --yes
```
