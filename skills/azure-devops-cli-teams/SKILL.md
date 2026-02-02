---
name: azure-devops-cli-teams
description: Manage Azure DevOps teams with the CLI.
---

# Azure DevOps CLI - Teams

Manage teams in an Azure DevOps project.

**CLI Version:** 2.81.0 (current as of 2025)

## Prerequisites

```bash
# Install Azure DevOps extension
az extension add --name azure-devops
```

## Teams

```bash
# List teams
az devops team list --project {project}

# Show team
az devops team show --team {team-name} --project {project}

# Create team
az devops team create \
  --name {team-name} \
  --description "Team description" \
  --project {project}

# Update team
az devops team update \
  --team {team-name} \
  --project {project} \
  --name "{new-team-name}" \
  --description "Updated description"

# Delete team
az devops team delete --team {team-name} --project {project} --yes

# Show team members
az devops team list-member --team {team-name} --project {project}
```
