# Skills Library

A collection of useful Agent Skills for Claude Code. This repository contains reusable, well-documented skills that enhance Claude's capabilities and streamline common workflows.

## About Agent Skills

Agent Skills are specialized instructions that extend Claude's functionality. They provide clear decision trees, best practices, and workflows for complex tasks. Skills can be:
- Integrated into Claude Code for seamless access
- Shared with teams and collaborators
- Versioned and improved over time
- Customized to match your specific workflow

## Currently Available Skills

### Linear Issue Handler
**Location:** `linear-issue-handler/`

A comprehensive workflow for managing Linear issues using the `linearis` CLI tool.

**What it does:**
- Handles issue creation with smart decision trees (when to ask first vs. create directly)
- Provides status tracking and progress update workflows
- Manages commenting and file downloads from issues
- Includes best practices for state changes and team communication
- Supports sub-task creation and cross-issue references

**Key features:**
- Clear guidelines on when to update issue descriptions directly vs. asking for approval
- Workflows for common scenarios (starting work, reporting progress, completing tasks)
- Tool reference and quick decision flowchart
- Integration with `~/.linear_api_token` for authentication

**When to use:** Any time you're managing work tracked in Linear, reading issue context, or creating follow-up tasks.

## How to Use These Skills

### In Claude Code

1. Place skill folders in your `.claude/skills` directory
2. Reference the skill by name in Claude Code sessions
3. The skill's instructions automatically enhance Claude's behavior for that task

### In Custom Projects

1. Review the skill's documentation (e.g., `SKILL.md`)
2. Adapt the workflows and decision trees to your needs
3. Provide the skill context to Claude when working on relevant tasks

## Skill Structure

Each skill follows this structure:

```
skill-name/
├── SKILL.md          # Complete skill documentation, workflows, and decision trees
└── README.md         # (Optional) Additional context or usage notes
```

The `SKILL.md` file is the primary reference and should include:
- Overview of what the skill does
- Foundation (tools, authentication, key principles)
- Decision trees for common scenarios
- Detailed workflows with examples
- Tool reference and best practices
- Quick decision flowcharts

## Contributing

When adding new skills to this library:

1. **Create a descriptive folder** - Use kebab-case naming (e.g., `linear-issue-handler`)
2. **Write comprehensive documentation** - Include workflows, decision trees, and examples in `SKILL.md`
3. **Test the workflow** - Ensure instructions are clear and actionable
4. **Include best practices** - Share lessons learned and common pitfalls
5. **Version it** - Add a last updated date in the skill metadata

## License

These skills are shared freely. Feel free to use, modify, and adapt them for your own workflows.

---

**Last Updated:** November 13, 2025
