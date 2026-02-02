---
name: azure-devops-cli-security
description: Manage Azure DevOps security groups and permissions with the CLI.
---

# Azure DevOps CLI - Security

Manage security groups and permissions using Azure DevOps CLI.

**CLI Version:** 2.81.0 (current as of 2025)

## Prerequisites

```bash
# Install Azure DevOps extension
az extension add --name azure-devops
```

## Security Groups

### List Groups

```bash
# List all groups in project
az devops security group list --project {project}

# List all groups in organization
az devops security group list --scope organization

# List with filtering
az devops security group list --project {project} --subject-types vstsgroup
```

### Show Group Details

```bash
az devops security group show --group-id {group-id}
```

### Create Group

```bash
az devops security group create \
  --name {group-name} \
  --description "Group description" \
  --project {project}
```

### Update Group

```bash
az devops security group update \
  --group-id {group-id} \
  --name "{new-group-name}" \
  --description "Updated description"
```

### Delete Group

```bash
az devops security group delete --group-id {group-id} --yes
```

### Group Memberships

```bash
# List memberships
az devops security group membership list --id {group-id}

# Add member
az devops security group membership add \
  --group-id {group-id} \
  --member-id {member-id}

# Remove member
az devops security group membership remove \
  --group-id {group-id} \
  --member-id {member-id} --yes
```

## Security Permissions

### List Namespaces

```bash
az devops security permission namespace list
```

### Show Namespace Details

```bash
# Show permissions available in a namespace
az devops security permission namespace show --namespace "GitRepositories"
```

### List Permissions

```bash
# List permissions for user/group and namespace
az devops security permission list \
  --id {user-or-group-id} \
  --namespace "GitRepositories" \
  --project {project}

# List for specific token (repository)
az devops security permission list \
  --id {user-or-group-id} \
  --namespace "GitRepositories" \
  --project {project} \
  --token "repoV2/{project}/{repository-id}"
```

### Show Permissions

```bash
az devops security permission show \
  --id {user-or-group-id} \
  --namespace "GitRepositories" \
  --project {project} \
  --token "repoV2/{project}/{repository-id}"
```

### Update Permissions

```bash
# Grant permission
az devops security permission update \
  --id {user-or-group-id} \
  --namespace "GitRepositories" \
  --project {project} \
  --token "repoV2/{project}/{repository-id}" \
  --permission-mask "Pull,Contribute"

# Deny permission
az devops security permission update \
  --id {user-or-group-id} \
  --namespace "GitRepositories" \
  --project {project} \
  --token "repoV2/{project}/{repository-id}" \
  --permission-mask 0
```

### Reset Permissions

```bash
# Reset specific permission bits
az devops security permission reset \
  --id {user-or-group-id} \
  --namespace "GitRepositories" \
  --project {project} \
  --token "repoV2/{project}/{repository-id}" \
  --permission-mask "Pull,Contribute"

# Reset all permissions
az devops security permission reset-all \
  --id {user-or-group-id} \
  --namespace "GitRepositories" \
  --project {project} \
  --token "repoV2/{project}/{repository-id}" --yes
```

## Error Handling

### Handle Permission Errors

```bash
# Try operation, handle permission errors
if az devops security permission update \
  --id "$USER_ID" \
  --namespace "GitRepositories" \
  --project "$PROJECT" \
  --token "repoV2/$PROJECT/$REPO_ID" \
  --allow-bit 2 \
  --deny-bit 0 2>&1 | grep -q "unauthorized"; then
  echo "Error: Insufficient permissions to update repository permissions"
  exit 1
fi
```
