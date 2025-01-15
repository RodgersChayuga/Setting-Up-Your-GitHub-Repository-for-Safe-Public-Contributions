# Setting Up Your GitHub Repository for Safe Public Contributions

## 1. Branch Protection Rules

1. Go to your repository's Settings
2. Navigate to `Settings > Branches`
3. Under "Branch protection rules", click "Add rule"
4. Configure the following settings:
   - Branch name pattern: `main` (or your default branch)
   - Check "Require pull request reviews before merging"
   - Set "Required approving reviews" to at least 1
   - Check "Dismiss stale pull request approvals when new commits are pushed"
   - Check "Require status checks to pass before merging" if you have CI/CD
   - Check "Require branches to be up to date before merging"
   - Check "Include administrators" to apply rules to everyone

## 2. CONTRIBUTING.md
Create a `CONTRIBUTING.md` file in your repository root:

```markdown
# Contributing to [Project Name]

Thank you for your interest in contributing to [Project Name]! 

## Getting Started

1. Fork the repository
2. Create a new branch: `git checkout -b feature/your-feature-name`
3. Make your changes
4. Push to your fork: `git push origin feature/your-feature-name`
5. Create a Pull Request

## Pull Request Process

1. Ensure your PR description clearly describes the changes
2. Link any related issues
3. Update documentation if needed
4. Wait for review from maintainers
5. Address any requested changes

## Code Style

[Add your code style guidelines here]

## Code of Conduct

This project follows our Code of Conduct. Please read it before contributing.
```

## 3. Issue Templates
Create `.github/ISSUE_TEMPLATE/bug_report.md`:

```markdown
---
name: Bug report
about: Create a report to help us improve
title: '[BUG] '
labels: bug
assignees: ''
---

**Describe the bug**
A clear and concise description of what the bug is.

**To Reproduce**
Steps to reproduce the behavior:
1. Go to '...'
2. Click on '....'
3. See error

**Expected behavior**
A clear description of what you expected to happen.

**Additional context**
Add any other context about the problem here.
```

## 4. Pull Request Template
Create `.github/pull_request_template.md`:

```markdown
## Description
Please describe your changes here.

## Related Issue
Fixes #(issue)

## Type of change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation update
- [ ] Code refactoring

## Checklist:
- [ ] My code follows the style guidelines
- [ ] I have performed a self-review
- [ ] I have commented my code where needed
- [ ] I have updated the documentation
```

## 5. Security Policy
Create `SECURITY.md`:

```markdown
# Security Policy

## Reporting a Vulnerability

Please report security vulnerabilities to [your-email@example.com]

1. Do NOT create public GitHub issues for security vulnerabilities
2. Provide detailed information about the vulnerability
3. Allow up to 48 hours for initial response
4. Please respect disclosure timelines

## Security Measures

- All code is reviewed before merging
- Dependencies are regularly updated
- Security scanning is performed on all PRs
```

## 6. Code of Conduct
Create `CODE_OF_CONDUCT.md`:

```markdown
# Code of Conduct

## Our Pledge

We pledge to make participation in our project a harassment-free experience for everyone.

## Our Standards

Examples of behavior that contributes to creating a positive environment include:
- Being respectful of differing viewpoints
- Accepting constructive criticism
- Focusing on what is best for the community

## Enforcement

Violations may be reported to [your-email@example.com]. All complaints will be reviewed and investigated.
```

## 7. Repository Settings

Additional settings to configure:

1. Under Settings > General:
   - Enable "Issues"
   - Enable "Pull Requests"
   - Disable "Allow merge commits" if you prefer squash or rebase
   - Enable "Automatically delete head branches"

2. Under Settings > Security:
   - Enable "Dependency graph"
   - Enable "Dependabot alerts"
   - Enable "Code scanning alerts"
   - Enable "Secret scanning"
   - Enable "Push protection"
   - Enable "Private vulnerability reporting"

3. Under Settings > Actions > General:
   - Set "Fork pull request workflows" to "Require approval"
   - Configure "Workflow permissions" to read/write


[Move to The Advanced Repository Settings ->](advanced-github-contribution-setup.md)