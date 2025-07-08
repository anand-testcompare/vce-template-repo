# Git PR Workflow

Autonomously create a pull request from current changes without requiring any user input. Stage relevant changes (excluding node_modules, build artifacts, and credentials), commit, push to remote, and create PR. Never include Claude marketing or co-authorship text.

## Process
1. **Analyze Changes**: Check git status and diff to understand modifications
2. **Auto-Generate Content**: Create branch name, commit message, PR title, and description based on actual changes
3. **Stage & Commit**: Add relevant files and commit with clean message
4. **Push & PR**: Push to remote and create PR with professional description
5. **Return URL**: Provide the PR URL when complete

## Auto-Generation Rules
- **Branch Name**: Use existing branch or create descriptive name (feat/, fix/, refactor/)
- **Commit Message**: Analyze changes to create concise, descriptive message
- **PR Title**: Professional title based on the main changes
- **PR Description**: Summary with test plan based on modified files

## Commit Format
```
type: brief description

- Specific change 1
- Specific change 2
- Technical improvement 3
```

## PR Template
```markdown
## Summary
- [Auto-generated points from actual changes]

## Test plan
- [ ] [Generated test items based on file types and changes]
```

## Security
- Exclude sensitive files (.env*, credentials, node_modules, build artifacts)
- Verify .gitignore configuration
- Never commit secrets or hardcoded sensitive data
- No marketing text or co-authorship attribution

**Example (fully autonomous):**
When invoked, automatically analyze current changes, create appropriate branch/commit/PR content, and return the PR URL without requiring any parameters or user input.