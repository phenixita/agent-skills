# dotnet-skillz

.NET CLI tools with SKILLS for coding agents.

## Available Skills

| Skill | Description |
|-------|-------------|
| [ilspy-decompile](skills/dotnet/ilspy-decompile/SKILL.md) | Understand .NET implementation details by decompiling assemblies |

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