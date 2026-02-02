---
name: azure-devops-cli-wiki
description: Manage Azure DevOps wikis and pages with the CLI.
---

# Azure DevOps CLI - Wiki

Create and manage wikis and wiki pages.

**CLI Version:** 2.81.0 (current as of 2025)

## Prerequisites

```bash
# Install Azure DevOps extension
az extension add --name azure-devops
```

## Wikis

```bash
# List all wikis in project
az devops wiki list --project {project}

# List all wikis in organization
az devops wiki list

# Show wiki
az devops wiki show --wiki {wiki-name} --project {project}
az devops wiki show --wiki {wiki-name} --project {project} --open

# Create project wiki
az devops wiki create \
  --name {wiki-name} \
  --project {project} \
  --type projectWiki

# Create code wiki from repository
az devops wiki create \
  --name {wiki-name} \
  --project {project} \
  --type codeWiki \
  --repository {repo-name} \
  --mapped-path /wiki

# Delete wiki
az devops wiki delete --wiki {wiki-id} --project {project} --yes
```

## Wiki Pages

```bash
# List pages
az devops wiki page list --wiki {wiki-name} --project {project}

# Show page
az devops wiki page show \
  --wiki {wiki-name} \
  --path "/page-name" \
  --project {project}

# Create page
az devops wiki page create \
  --wiki {wiki-name} \
  --path "/new-page" \
  --content "# New Page\n\nPage content here..." \
  --project {project}

# Update page
az devops wiki page update \
  --wiki {wiki-name} \
  --path "/existing-page" \
  --content "# Updated Page\n\nNew content..." \
  --project {project}

# Delete page
az devops wiki page delete \
  --wiki {wiki-name} \
  --path "/old-page" \
  --project {project} --yes
```
