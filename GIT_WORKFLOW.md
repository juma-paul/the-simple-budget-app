# Git Workflow Guidelines

## Table of Contents
1. [Initial Setup](#initial-setup)
2. [Branch Naming Convention](#branch-naming-convention)
3. [Commit Message Guidelines](#commit-message-guidelines)
4. [Development Workflow](#development-workflow)
5. [Pull Request Process](#pull-request-process)

## Initial Setup
1. Fork the repository
2. Clone it to your local machine
3. Create a branch following our naming convention
4. Make test changes to verify setup

## Branch Naming Convention
Format: `dev/description-of-task`

Example: `dev/test-repo-setup`

### Types
- `feat` - New features
- `fix` - Bug fixes
- `chore` - Maintenance tasks
- `docs` - Documentation updates
- `test` - Test-related changes
- `refactor` - Code refactoring
- `style` - Formatting changes

## Commit Message Guidelines

### Single-line Commits (max 72 characters)
```
type: brief description (#issue-number)
```
Example:
```
chore: setup initial directory structure (#1)
```

### Multi-line Commits
```
type: brief description (#issue-number)

Detailed explanation of the changes made.
Can span multiple lines.

Fixes: #issue-number
```

Example:
```
chore: setup initial directory structure (#1)

The setup consists of backend directory which has two subdirectories;
assets and src. The src directory consists of the entry point to our
project; app.py

Fixes: #1
```

## Development Workflow

### Creating a New Branch
```bash
git checkout -b dev/description-of-task
```

### Making Changes
1. Check status of changes:
```bash
git status
```

2. Add specific files:
```bash
git add <filename>
```

3. Commit changes:
```bash
# For single-line commits
git commit -m "type: description (#issue-number)"

# For multi-line commits (will open code editor; where you'll type your commit message)
git commit
```

4. Push changes:
```bash
git push -u origin dev/description-of-task
```

## Pull Request Process
1. Navigate to the GitHub repository
2. Create a Pull Request
3. Verify the correct branch mapping:
```
base: main <- compare: dev/description-of-task
```
4. Ensure PR title and description match commit message
5. Submit PR for review

### After PR is Merged
1. Return to main branch:
```bash
git checkout main
```

2. Verify current branch:
```bash
git branch  # Should show *main
```

3. Delete feature branch:
```bash
git branch -d dev/description-of-task
```

4. Verify deletion:
```bash
git branch  # Should only show main
```

## Important Notes
- Always use kebab-case for branch descriptions
- Keep commit messages clear and concise
- Reference issues in commits when applicable
- Ensure your branch is up-to-date before creating a PR
- Delete feature branches after they're merged(both on local and remote repo)
