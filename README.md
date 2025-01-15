# GitHub Repository Contribution Setting

Setting Up Your GitHub Repository for Safe Public Contributions.
By: [Eng. Rodgers Chayuga](https://www.github.com/RodgersChayuga)

## Table of Contents

1. [Branch Protection Rules](github-contribution-setup.md#1-branch-protection-rules)
   - Required Reviews
   - Status Checks
   - Up-to-date Branches

2. [Contributing Guidelines](github-contribution-setup.md#2-contributingmd)
   - Getting Started
   - Pull Request Process
   - Code Style Guidelines
   - Local Development Setup
   - Branch Strategy

3. [Issue Templates](github-contribution-setup.md#3-issue-templates)
   - Bug Report Template
   - Feature Request Template

4. [Pull Request Template](github-contribution-setup.md#4-pull-request-template)
   - Description Requirements
   - Checklist
   - Type of Change

5. [Security Policy (SECURITY.md)](github-contribution-setup.md#5-security-policy)
   - Vulnerability Reporting Process
   - Security Measures
   - Disclosure Timeline

6. [Code of Conduct](github-contribution-setup.md#6-code-of-conduct)
   - Our Pledge
   - Our Standards
   - Enforcement Guidelines

7. [Repository Settings](github-contribution-setup.md#7-repository-settings)
   - General Settings
   - Security Settings
   - Actions Settings

8. [CODEOWNERS Configuration](advanced-github-contribution-setup.md#8-codeowners-file)
   - Default Owners
   - Specific Path Owners
   - File Type Owners

9.  [Automated Workflows](advanced-github-contribution-setup.md#9-automated-workflows)
   - PR Labeler
   - Size Labeler
   - Stale Issue Handler
   - Dependabot Settings

10. [Release Process](advanced-github-contribution-setup.md#10-release-process-documentation)
    - Versioning Guidelines
    - Release Steps
    - Release Checklist

11. [Local Development Guide](advanced-github-contribution-setup.md#11-local-development-setup)
    - Setup Instructions
    - Development Guidelines
    - Testing Process

12. [Branch Strategy](advanced-github-contribution-setup.md#development-guidelines)
    - Branch Types
      - `main`: Production code
      - `develop`: Integration branch
      - `feature/*`: New features
      - `bugfix/*`: Bug fixes
      - `hotfix/*`: Urgent fixes
      - `release/*`: Release preparation
    - Workflow Steps

### ⚙️ Configuration Files Location
```
.github/
├── workflows/
│   ├── pr-labeler.yml
│   └── stale.yml
├── ISSUE_TEMPLATE/
│   └── bug_report.md
├── pull_request_template.md
├── dependabot.yml
└── CODEOWNERS

Root/
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── SECURITY.md
├── RELEASING.md
└── README.md
```

### 🔨 Quick Start Commands
```bash
# 1. Clone and Setup
git clone https://github.com/username/repo.git
cd repo

# 2. Install Dependencies
npm install

# 3. Setup Pre-commit Hooks
npx husky install

# 4. Create Feature Branch
git checkout -b feature/your-feature

# 5. Development Cycle
npm test         # Run tests
npm start        # Start development server
npm run build    # Build for production
npm run lint     # Run linting
```

### 📄 License
MIT License - See [LICENSE](LICENSE) file for details

### 📞 Contact
- Maintainer: Rodgers Chayuga
- Email: chayugarodgers@gmail.com
- LinkedIn: [https://github.com/username/repo](https://linkedin.com/in/rodgerschayuga)](https://linkedin.com/in/rodgerschayuga)
- Website: [https://rodgerschayuga.com](https://rodgerschayuga.com)
