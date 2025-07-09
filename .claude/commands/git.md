**Purpose**: Git workflow with checkpoint management

---

@include shared/universal-constants.yml#Universal_Legend

## Command Execution
Execute: immediate. --plan→show plan first
Legend: Generated based on symbols used in command
Purpose: "[Action][Subject] in $ARGUMENTS"

Manage comprehensive git workflows for repositories specified in $ARGUMENTS.

@include shared/flag-inheritance.yml#Universal_Always

Examples:
- `/git --commit "Add user profile API endpoint"` - Standard commit w/ message
- `/git --pr --reviewers alice,bob --labels api,feature` - Create PR w/ reviewers
- `/git --flow feature "payment-integration" --think` - Full feature workflow
- `/git --pre-commit` - Setup pre-commit framework and basic hooks
- `/git --commit "Fix validation logic" --pre-commit` - Commit with pre-commit validation
- `/git --pre-commit --security` - Setup with security hooks included

Git operations:

**--commit:** Stage appropriate files | Generate meaningful commit message | Include co-author attribution | Follow conventional commits

**--pr:** Create pull request | Generate PR description | Set reviewers & labels | Link related issues

**--flow:** Git workflow patterns
- feature: Feature branch workflow | hotfix: Emergency fix workflow
- release: Release branch workflow | gitflow: Full GitFlow model

**--pre-commit:** Setup and manage pre-commit hooks | Auto-install framework | Configure quality checks | Run hooks before commits

@include shared/execution-patterns.yml#Git_Integration_Patterns

## Git Standards & Professional Workflow

### Commit Types (Single Letter)
- `f`: Feature (feat)
- `x`: Fix/Bug (fix)
- `d`: Documentation (docs)
- `r`: Refactor (refactor)
- `s`: Style (style)
- `t`: Test (test)
- `c`: Chore (chore)

### Branch Naming (Single Letter)
- `f/description` - Features
- `x/description` - Bug fixes
- `r/description` - Refactoring
- `s/description` - Style changes
- `d/description` - Documentation
- `t/description` - Tests

### Professional Standards
- **NEVER use emojis** in commit messages or pull request titles/descriptions
- **NEVER reference AI agents** (Claude, Anthropic, Gemini, OpenCode, Aider, etc.) in commits or pull requests
- **Use conventional commit format**: `type: description` (Max 50 characters)
- **Capitalize the subject line**
- **Use imperative mood** in the subject line
- **Do not end the subject line with a period**
- **Separate subject from body with a blank line**
- **Use the body to explain what and why vs. how**
- **Keep all messages professional and factual**
- **Focus on technical implementation details**
- **Stage commits frequently for small, logical changes**
- **Use GitHub CLI (`gh`) for PRs and issues, `git` for all other operations**

### Commit Message Examples

#### Short format (subject line only)
```
f: Add user authentication endpoint
x: Resolve memory leak in data processing
r: Extract validation logic to utils module
s: Format code according to style guidelines
d: Update API endpoint documentation
t: Add unit tests for validation functions
c: Update build dependencies
```

#### Full format (with body and references)
```
x: Resolve memory leak in data processing

The previous implementation was causing a memory leak when processing large datasets.
This change introduces a more efficient data handling method that releases memory correctly.

Github issue #23
```

@include shared/pre-commit-patterns.yml#Pre_Commit_Setup

@include shared/docs-patterns.yml#Standard_Notifications

@include shared/universal-constants.yml#Standard_Messages_Templates