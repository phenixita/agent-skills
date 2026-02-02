# dotnet-skillz

.NET CLI tools with SKILLS for coding agents.

## Available Skills

| Skill | Description |
|-------|-------------|
| [ilspy-decompile](skills/ilspy-decompile/SKILL.md) | Understand .NET implementation details by decompiling assemblies |
| [azure-devops-cli-devops](skills/azure-devops-cli-devops/SKILL.md) | Core Azure DevOps CLI setup, auth, configuration, and projects |
| [azure-devops-cli-repos](skills/azure-devops-cli-repos/SKILL.md) | Azure Repos management, pull requests, refs, and policies |
| [azure-devops-cli-pipelines](skills/azure-devops-cli-pipelines/SKILL.md) | Pipelines, runs, builds, releases, variables, and agents |
| [azure-devops-cli-boards](skills/azure-devops-cli-boards/SKILL.md) | Azure Boards work items, areas, and iterations |
| [azure-devops-analytics](skills/azure-devops-analytics/SKILL.md) | Azure DevOps Analytics OData queries |
| [azure-devops-cli-artifacts](skills/azure-devops-cli-artifacts/SKILL.md) | Azure Artifacts universal packages |
| [azure-devops-cli-admin](skills/azure-devops-cli-admin/SKILL.md) | Admin banners and DevOps extensions |
| [azure-devops-cli-security](skills/azure-devops-cli-security/SKILL.md) | Security groups and permissions |
| [azure-devops-cli-wiki](skills/azure-devops-cli-wiki/SKILL.md) | Wikis and wiki pages |
| [azure-devops-cli-users](skills/azure-devops-cli-users/SKILL.md) | User management and licensing |
| [azure-devops-cli-teams](skills/azure-devops-cli-teams/SKILL.md) | Team management and membership |
| [azure-devops-cli-service-endpoint](skills/azure-devops-cli-service-endpoint/SKILL.md) | Service endpoints and service connections |

## What are Skills?

Skills are lightweight prompts that teach coding agents how to use CLI tools effectively. They provide:

- **Token-efficient** workflows that don't bloat LLM context
- **Purpose-built commands** for specific tasks
- **Best practices** for common scenarios

## Requirements

- .NET 10 SDK or newer
- Claude Code, GitHub Copilot, or any other coding agent

## Installing Skills

### GitHub Copilot CLI (recommended)

```bash
/plugin marketplace add phenixita/agent-skills
/plugin install ilspy-decompile@agent-skills
```

### Claude Code

```bash
mkdir -p .claude/skills/<skill-name>
curl -o .claude/skills/<skill-name>/SKILL.md \
  https://raw.githubusercontent.com/phenixita/agent-skills/main/skills/<skill-name>/SKILL.md
```
 
## Contributing

To add a new skill:

1. Create a folder under `skills/<skill-name>/`
2. Add a `SKILL.md` file following the format of existing skills
3. Update the Available Skills table in this README