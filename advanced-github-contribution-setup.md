# Setting Up Your GitHub Repository for Safe Public Contributions

[Get the Basics Repository Settings ->](github-contribution-setup.md)

## 8. CODEOWNERS File
Create `.github/CODEOWNERS`:

```plaintext
# These owners will be the default owners for everything in the repo
* @your-username

# Specific file/directory owners
/docs/ @your-username
/src/ @your-username
*.js @your-username
```

## 9. Automated Workflows
Create `.github/workflows/pr-labeler.yml`:

```yaml
name: PR Labeler
on: [pull_request]

jobs:
  label:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/labeler@v4
      with:
        repo-token: "${{ secrets.GITHUB_TOKEN }}"
        configuration-path: .github/labeler.yml

  size:
    runs-on: ubuntu-latest
    steps:
    - uses: codelytv/pr-size-labeler@v1
      with:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        xs_max_size: '10'
        s_max_size: '100'
        m_max_size: '500'
        l_max_size: '1000'
        fail_if_xl: 'false'
```

Create `.github/workflows/stale.yml`:

```yaml
name: Mark stale issues and pull requests

on:
  schedule:
  - cron: "0 0 * * *"

jobs:
  stale:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/stale@v8
      with:
        repo-token: ${{ secrets.GITHUB_TOKEN }}
        stale-issue-message: 'This issue is stale due to inactivity.'
        stale-pr-message: 'This PR is stale due to inactivity.'
        stale-issue-label: 'no-issue-activity'
        stale-pr-label: 'no-pr-activity'
        days-before-stale: 60
        days-before-close: 7
```

Create `.github/dependabot.yml`:

```yaml
version: 2
updates:
  - package-ecosystem: "npm" # or other package managers
    directory: "/"
    schedule:
      interval: "weekly"
    open-pull-requests-limit: 10
    labels:
      - "dependencies"
      - "automerge"
    versioning-strategy: auto

  - package-ecosystem: "github-actions"
    directory: "/"
    schedule:
      interval: "weekly"
```

## 10. Release Process Documentation
Create `RELEASING.md`:

```markdown
# Release Process

## Versioning
This project follows [Semantic Versioning](https://semver.org/):
- MAJOR version for incompatible API changes
- MINOR version for backwards-compatible functionality
- PATCH version for backwards-compatible bug fixes

## Release Steps
1. Update version in package.json
2. Update CHANGELOG.md
3. Create a new tag: `git tag v1.0.0`
4. Push tag: `git push origin v1.0.0`
5. Create GitHub release with release notes
6. Deploy if applicable

## Release Checklist
- [ ] Tests passing
- [ ] Documentation updated
- [ ] CHANGELOG.md updated
- [ ] Version bumped
- [ ] Git tag created and pushed
- [ ] GitHub release created
```

## 11. Local Development Setup
Add to `CONTRIBUTING.md`:

```markdown
## Local Development Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/username/repo.git
   cd repo
   ```

2. Install dependencies:
   ```bash
   npm install # or your package manager
   ```

3. Set up pre-commit hooks:
   ```bash
   npx husky install
   ```

4. Create a branch for your work:
   ```bash
   git checkout -b feature/your-feature
   ```

5. Run tests:
   ```bash
   npm test
   ```

6. Start local development server:
   ```bash
   npm start
   ```

## Development Guidelines
- Write tests for new features
- Follow the code style guide
- Keep commits atomic and well-described
- Update documentation as needed
```

## 12. Branch Strategy Documentation
Add to `CONTRIBUTING.md`:

```markdown
## Branch Strategy

- `main`: Production-ready code
- `develop`: Integration branch for features
- `feature/*`: New features
- `bugfix/*`: Bug fixes
- `hotfix/*`: Urgent production fixes
- `release/*`: Release preparation

### Branch Workflow
1. Create feature branch from `develop`
2. Develop and test your changes
3. Create PR to merge into `develop`
4. After review and approval, merge to `develop`
5. Release branches are created from `develop`
6. After testing, release branches are merged to `main`
```
