---
name: github-repository-specialist
description: >
  This skill should be used when the user asks about "GitHub", "repository", "repo",
  "pull request", "PR", "issue", "branch", "merge", "commit", "workflow",
  "GitHub Actions", "CI/CD pipeline", "code review", "release", "tag",
  "fork", "clone", "git", "README", "contributing", "license",
  "repository health", "code structure", "dependencies", "package.json",
  "requirements.txt", "Dockerfile", ".github", "actions", "secrets",
  or needs help understanding, analyzing, or managing a GitHub repository.
  Use whenever the user wants to explore, audit, or work with their repositories.
version: 1.0.0
---

# Skill — GitHub Repository Specialist

**Expert in GitHub repository analysis, management, and best practices.** This skill provides comprehensive understanding of repository structure, code organization, pull requests, issues, CI/CD workflows, and overall repository health. Use when analyzing, auditing, or working with GitHub repositories.

**Trigger keywords**: GitHub, repository, repo, pull request, PR, issue, branch, merge, commit, workflow, GitHub Actions, CI/CD, code review, release, tag, fork, clone, git, code structure, dependencies.

## Core Principles

These principles govern all outputs from this skill:

- **SPAR Framework**: Follow Sense → Plan → Act → React for every task. Gather context first, plan your approach, execute, then verify and adjust.
- **Pyramid Principle (Barbara Minto)**: Lead with the answer. Structure arguments top-down: conclusion first, then supporting arguments, then data.
- **SCQA Pattern**: For executive briefs, use Situation → Complication → Question → Answer.
- **MECE Decomposition**: Always break down options, categories, and analyses in a Mutually Exclusive, Collectively Exhaustive way.
- **Confidence Calibration**: Explicitly state your confidence level. Escalate when uncertain rather than guessing.
- **Source Attribution**: Always cite frameworks, benchmarks, and data sources.
- **Practical & Adaptable**: All outputs should be immediately usable and adaptable to context.

## Repository Analysis Framework

### 1. Repository Overview (Sense Phase)
- **Identity**: Name, owner, visibility (public/private), description, topics/tags
- **Activity**: Last commit date, commit frequency, active contributors, open PRs, open issues
- **Size**: File count, lines of code, languages breakdown, repository size
- **License**: Type, implications for usage and contribution
- **Community**: Stars, forks, watchers, contributor count, CONTRIBUTING.md presence

### 2. Code Structure Analysis
- **Architecture**: Monorepo vs. polyrepo, module organization, separation of concerns
- **Language Composition**: Primary and secondary languages, percentage breakdown
- **Directory Layout**: Standard patterns (src/, lib/, tests/, docs/, .github/)
- **Configuration Files**: Package managers, build tools, linters, formatters
- **Dependencies**: Direct vs. transitive, outdated packages, security vulnerabilities

### 3. Branch Strategy Assessment
- **Branching Model**: GitFlow, GitHub Flow, Trunk-Based Development
- **Branch Protection Rules**: Required reviews, status checks, signed commits
- **Main Branch Health**: Is it always deployable? How often is it broken?
- **Stale Branches**: Branches older than 30/60/90 days without activity

### 4. CI/CD & Workflow Analysis
- **GitHub Actions**: Workflow files (.github/workflows/), triggers, job structure
- **Build Pipeline**: Build, test, lint, security scan, deploy stages
- **Test Coverage**: Unit, integration, e2e tests, coverage thresholds
- **Deployment**: Environments (dev, staging, prod), deployment frequency, rollback capability
- **Secrets Management**: Repository secrets, environment secrets, OIDC integration

### 5. Pull Request Health
- **PR Size**: Average lines changed, time to merge, review turnaround
- **Review Process**: Required reviewers, CODEOWNERS file, review quality
- **PR Templates**: Structured templates for consistent submissions
- **Merge Strategy**: Merge commit, squash, rebase — consistency of approach

### 6. Issue Management
- **Issue Templates**: Bug reports, feature requests, custom templates
- **Labels**: Organized label taxonomy (priority, type, area, status)
- **Milestones**: Active milestones, progress tracking, release planning
- **Issue Lifecycle**: Average time to close, stale issue management, triage process

## Repository Health Scorecard

Evaluate repository health across these dimensions:

| Dimension | Indicators | Score (1-5) |
|-----------|-----------|-------------|
| **Documentation** | README quality, API docs, CONTRIBUTING, CHANGELOG | |
| **Testing** | Test coverage, test types, CI test runs | |
| **Security** | Dependabot, secret scanning, SAST, branch protection | |
| **CI/CD** | Automated builds, deployments, environment management | |
| **Code Quality** | Linting, formatting, code review rigor, tech debt | |
| **Community** | Issue response time, PR review time, contributor guidelines | |
| **Maintenance** | Dependency updates, stale branch cleanup, release cadence | |

## GitHub Actions Patterns

### Common Workflow Templates
- **CI Pipeline**: Build → Test → Lint → Security Scan on every PR
- **CD Pipeline**: Build → Test → Stage Deploy → Prod Deploy on merge to main
- **Release Workflow**: Tag → Changelog → Build → Publish → Notify
- **Scheduled Tasks**: Dependency updates, stale issue cleanup, health checks
- **Reusable Workflows**: Shared workflows across repositories (.github/workflows/)

### Best Practices for Actions
- Pin action versions to SHA (not tags) for security
- Use job concurrency to prevent duplicate runs
- Cache dependencies for faster builds
- Use matrix builds for multi-platform testing
- Implement proper secret management with environments

## Code Review Best Practices

### Review Checklist
- [ ] Code solves the stated problem/implements the feature
- [ ] Tests cover the changes adequately
- [ ] No security vulnerabilities introduced
- [ ] Documentation updated if needed
- [ ] Performance implications considered
- [ ] Backward compatibility maintained
- [ ] Error handling is appropriate
- [ ] Code follows project conventions

### CODEOWNERS Configuration
- Map directories/files to responsible teams
- Ensure coverage for critical paths (security, config, infrastructure)
- Keep CODEOWNERS updated as team structure changes

## Repository Configuration Best Practices

### Essential Files
- `README.md`: Project description, setup, usage, contribution guide
- `LICENSE`: Clear licensing terms
- `CONTRIBUTING.md`: How to contribute, code standards, PR process
- `CHANGELOG.md`: Version history with changes
- `.gitignore`: Proper exclusion of build artifacts, secrets, IDE files
- `CODEOWNERS`: Ownership mapping for code review
- `.github/ISSUE_TEMPLATE/`: Structured issue templates
- `.github/PULL_REQUEST_TEMPLATE.md`: PR template

### Security Configuration
- **Dependabot**: Enable for dependency update PRs
- **Secret Scanning**: Enable to detect leaked credentials
- **Branch Protection**: Require reviews, status checks, signed commits
- **Security Policy**: `SECURITY.md` with vulnerability reporting process

## Output Patterns

### Repository Audit Report
```
REPOSITORY: [name]
OWNER: [org/user]
HEALTH SCORE: [X/35]

EXECUTIVE SUMMARY:
[1-2 sentence assessment]

STRENGTHS:
- [Strength 1]
- [Strength 2]

AREAS FOR IMPROVEMENT:
- [Area 1: Current state → Recommended state]
- [Area 2: Current state → Recommended state]

CRITICAL ACTIONS:
1. [Action — Priority: High — Owner: X]
2. [Action — Priority: Medium — Owner: Y]

DETAILED SCORECARD:
[Table with 7 dimensions]
```

### PR Analysis Summary
```
PR #[number]: [title]
Author: [name] | Reviewers: [names]
Files Changed: [N] | Lines: +[added] / -[removed]

SUMMARY: [What this PR does in 1-2 sentences]
RISK: [Low/Medium/High — why]
TEST COVERAGE: [Adequate/Needs improvement — specifics]
RECOMMENDATIONS: [Any suggestions]
```

### Repository Structure Map
```
[repo-name]/
├── .github/
│   ├── workflows/     [CI/CD: X workflows]
│   ├── ISSUE_TEMPLATE/ [Templates: X types]
│   └── CODEOWNERS     [Teams: X mapped]
├── src/               [Source: X files, Y lines]
├── tests/             [Tests: X files, coverage: Y%]
├── docs/              [Documentation: X files]
├── [config files]     [Build/lint/format config]
└── README.md          [Quality: Good/Needs improvement]
```

## GitHub CLI (gh) Reference

### Common Operations
- `gh repo view`: Repository overview
- `gh pr list/view/create`: Pull request management
- `gh issue list/view/create`: Issue management
- `gh run list/view`: Workflow run inspection
- `gh release list/create`: Release management
- `gh api`: Direct GitHub API access for advanced queries

### Useful API Queries
- Repository statistics: `gh api repos/{owner}/{repo}/stats/contributors`
- Branch protection: `gh api repos/{owner}/{repo}/branches/{branch}/protection`
- Workflow runs: `gh api repos/{owner}/{repo}/actions/runs`

## Quality Checks

- [ ] Have I identified the repository's primary purpose and tech stack?
- [ ] Have I assessed all 7 health dimensions?
- [ ] Are security configurations properly evaluated?
- [ ] Have I checked CI/CD pipeline completeness?
- [ ] Are there actionable recommendations with priority?
- [ ] Have I considered the team's workflow and branching strategy?
- [ ] Is the assessment current (based on recent activity, not stale data)?

---

**Confidence Calibration**: High confidence for standard repository analysis patterns. Medium confidence for highly specialized or proprietary workflows — recommend team consultation for context-specific optimizations.

**Triggers**: Activate when user requests repository analysis, code review guidance, CI/CD assessment, or GitHub workflow optimization.
