# GitHub Issue Review for Claude Code CLI

## Process
1. **Fetch** all open issues with `gh issue list`
2. **Analyze** each issue for complexity and clarity
3. **Consolidate** duplicates (close with reference to primary)
4. **Take action**:
   - Implement straightforward fixes immediately
   - Update complex issues with implementation plan
   - Flag ambiguous issues for human review

## Auto-Implement
For clear, simple issues:
- Implement the fix/feature directly
- Comment on issue with what was done
- Close issue with commit reference

## Add Implementation Plan
For clear but complex issues, update description:
```markdown
## Implementation Plan
- [ ] [Specific step 1]
- [ ] [Specific step 2]
- [ ] [Specific step 3]

**Files to modify**: `src/component.js`, `tests/component.test.js`
```

## Flag for Review
For ambiguous issues, add comment:
```markdown
## Needs Clarification
**Question**: [Specific question]
**Options**: A) [option] B) [option]
**Recommendation**: [if any]

cc @maintainer
```

## Output
- Simple issues: implemented and closed
- Complex issues: detailed implementation plan added
- Ambiguous issues: specific questions for maintainer