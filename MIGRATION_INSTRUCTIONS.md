# Linear Skill Migration to skills-workshop

This document contains instructions for completing the migration of the linear-issue-handler skill to the skills-workshop repository.

## Status

✅ **skills-library deprecation**: Completed and pushed to branch `claude/migrate-linear-skill-IcmUK`
⏳ **skills-workshop migration**: Ready to push (authorization issue prevented automated push)

## What's Been Done

### In skills-library Repository
- ✅ Added deprecation notice to README.md
- ✅ Created MIGRATED.md in Skills/linear-issue-handler/
- ✅ Committed changes to branch `claude/migrate-linear-skill-IcmUK`
- ✅ Pushed branch successfully

### In skills-workshop Repository (Local Only)
- ✅ Created all necessary files:
  - `linear-issue-handler/SKILL.md` (434 lines)
  - `linear-issue-handler/INSTALL.md` (134 lines)
  - `releases/linear-issue-handler/VERSION` (v1.0.0)
  - `releases/linear-issue-handler/CHANGELOG.md`
- ✅ Updated README.md to include linear-issue-handler
- ✅ Committed to branch `claude/add-linear-skill-IcmUK`
- ❌ Push failed due to authorization issues

## How to Complete the Migration

### Option 1: Apply the Patch File (Recommended)

A patch file has been created with all the changes ready to apply:

```bash
# Navigate to your local skills-workshop repository
cd /path/to/skills-workshop

# Create and checkout the feature branch
git checkout -b claude/add-linear-skill-IcmUK

# Apply the patch
git am /home/user/skills-library/0001-Add-linear-issue-handler-skill-from-skills-library.patch

# Push to GitHub
git push -u origin claude/add-linear-skill-IcmUK

# Create PR via GitHub web interface or gh CLI:
gh pr create --title "Add linear-issue-handler skill from skills-library" \
  --body "Migrate Linear Issue Handler skill from trounceabout/skills-library.

## Summary
- Add comprehensive Linear issue management workflow skill
- Includes installation guide and complete documentation
- Version 1.0.0 with full changelog

Resolves #4"
```

### Option 2: Copy from Prepared Repository

A complete copy of the skills-workshop repository with all changes is available at:
`/home/user/skills-library/skills-workshop-migration/`

```bash
# Navigate to the prepared repository
cd /home/user/skills-library/skills-workshop-migration

# Push the branch (requires proper authentication)
git push -u origin claude/add-linear-skill-IcmUK

# Create PR as shown above
```

### Option 3: Manual File Copy

If you prefer to copy files manually:

```bash
# From your skills-workshop repository:
cd /path/to/skills-workshop
git checkout -b claude/add-linear-skill-IcmUK

# Copy files from the migration directory
cp -r /home/user/skills-library/skills-workshop-migration/linear-issue-handler ./
cp -r /home/user/skills-library/skills-workshop-migration/releases/linear-issue-handler ./releases/

# Update README.md - add this section after git-worktree-tool:
```

Add to `README.md` in the "Available Skills" section:

```markdown
### linear-issue-handler (v1.0.0)

**Linear Issue Management Workflow** - A comprehensive Claude Code skill for managing Linear issues using the linearis CLI tool.

- **What it does**: Provides intelligent workflows for creating, updating, and tracking Linear issues with context-aware decision making
- **Key features**: Issue creation and updates, commenting, file downloads, state management, decision trees for autonomous vs. approval-based actions
- **Getting started**: See `linear-issue-handler/INSTALL.md` for setup
- **Documentation**: See `linear-issue-handler/SKILL.md` for full guide
- **Version**: 1.0.0 (see `releases/linear-issue-handler/CHANGELOG.md`)
```

Also update the "Skill Versions" section at the bottom of README.md:

```markdown
### Skill Versions

**git-worktree-tool**: See `releases/git-worktree-tool/CHANGELOG.md`
**linear-issue-handler**: See `releases/linear-issue-handler/CHANGELOG.md`
```

Then:

```bash
git add -A
git commit -m "Add linear-issue-handler skill from skills-library

Migrate Linear Issue Handler skill with documentation, installation guide, and version tracking.

Resolves #4"

git push -u origin claude/add-linear-skill-IcmUK
```

## Creating the Pull Request

After pushing the branch, create a PR using either method:

### Via GitHub Web Interface
1. Go to https://github.com/trounceabout/skills-workshop
2. GitHub should show a banner suggesting to create a PR for `claude/add-linear-skill-IcmUK`
3. Click "Compare & pull request"
4. Use the title and description from the commands above

### Via GitHub CLI
```bash
gh pr create --title "Add linear-issue-handler skill from skills-library" \
  --body "Migrate Linear Issue Handler skill from trounceabout/skills-library.

## Summary
- Add comprehensive Linear issue management workflow skill
- Includes installation guide and complete documentation
- Version 1.0.0 with full changelog
- Update README to list new skill

## What's Included
- \`linear-issue-handler/SKILL.md\` - Complete skill documentation (434 lines)
- \`linear-issue-handler/INSTALL.md\` - Installation and setup guide (134 lines)
- \`releases/linear-issue-handler/VERSION\` - Version tracking (v1.0.0)
- \`releases/linear-issue-handler/CHANGELOG.md\` - Release history
- Updated \`README.md\` with linear-issue-handler in Available Skills section

## Migration Status
The source repository (skills-library) has been marked as deprecated and updated with migration notices.

Resolves #4"
```

## Files in This Migration

### Patch File
- `0001-Add-linear-issue-handler-skill-from-skills-library.patch` - Git patch with all changes

### Prepared Repository
- `skills-workshop-migration/` - Complete copy of skills-workshop with all changes committed

### Changed Files Summary
```
README.md                                  |  11 +
linear-issue-handler/INSTALL.md            | 134 +++++++++
linear-issue-handler/MIGRATED.md           |  35 +++
linear-issue-handler/SKILL.md              | 434 +++++++++++++++++++++++++++++
releases/linear-issue-handler/CHANGELOG.md |  29 ++
releases/linear-issue-handler/VERSION      |   1 +
```

Total: 6 files changed, 644 insertions(+)

## Verification

After completing the migration, verify:

1. ✅ PR created in skills-workshop repository
2. ✅ All 6 files are included in the PR
3. ✅ README.md shows linear-issue-handler in Available Skills
4. ✅ PR references "Resolves #4"
5. ✅ CI/CD checks pass (if any)

## Questions?

If you encounter any issues completing this migration, check:
- Git authentication is properly configured
- You have write access to the skills-workshop repository
- The branch name matches `claude/add-linear-skill-IcmUK`

---

Migration prepared: January 17, 2026
Issue: https://github.com/trounceabout/skills-workshop/issues/4
