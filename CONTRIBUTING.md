# Contributing to Rygnal

Thanks for your interest in contributing to Rygnal.

Rygnal is building local-first runtime governance and security controls for AI-agent tool actions.
Contributions that improve safety, auditability, developer experience, or documentation are welcome.

---

## Table of contents

- [Before you start](#before-you-start)
- [Development setup](#development-setup)
- [Development principles](#development-principles)
- [Validation](#validation)
- [Pull request process](#pull-request-process)
- [Reporting bugs](#reporting-bugs)
- [Requesting features](#requesting-features)
- [Security issues](#security-issues)

---

## Before you start

- **Search existing issues** before opening a new one.
- **For significant changes**, open an issue first to discuss the approach before writing code.
- **For security vulnerabilities**, see [SECURITY.md](./SECURITY.md) — do not open a public issue.
- **For questions**, use [GitHub Discussions](https://github.com/orgs/Rygnal/discussions).

---

## Development setup

```bash
# Clone the repo
git clone https://github.com/Hi-ben-the-coder/rygnal-core.git
cd rygnal-core

# Create and activate a virtual environment
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate

# Install dev dependencies
pip install -e ".[dev]"

# Confirm it works
rygnal --help
pytest -q
```

See the project README for Docker-based setup if you prefer a containerized environment.

---

## Development principles

**Local-first**
The system must work without cloud services, without external APIs, and without vendor dependencies by default. Cloud integrations are opt-in.

**Policy-driven behavior**
Behavior is controlled by explicit, inspectable policy — not hardcoded logic. When in doubt, add a policy primitive rather than a special case.

**Auditable runtime decisions**
Every decision the runtime makes should produce a log entry. Silent decisions are not acceptable in a governance system.

**Human approval for higher-risk actions**
The system should know when to stop and ask. Approval workflows are a first-class feature, not an edge case.

**Secure defaults**
Default-block is the correct default for a security-focused tool. Opt-in to allow, not opt-in to deny. Never weaken defaults in a PR without explicit justification and review.

**Clear and minimal interfaces**
Prefer small, composable APIs over large, monolithic ones. Make the right thing easy and the wrong thing obvious.

---

## Validation

Run the full validation suite before requesting review:

```bash
# Format
ruff format src tests demo examples

# Lint
ruff check src tests demo examples

# Tests
pytest -q

# Security scan
bandit -r src demo examples -c pyproject.toml

# Dependency audit
pip-audit -r requirements-dev.txt
```

All checks must pass before a PR will be reviewed. CI enforces the same checks.

---

## Pull request process

1. **Fork the repository** and create a feature branch.
   ```bash
   git checkout -b fix/describe-your-change
   ```

2. **Make your change** — keep it focused. One problem per PR.

3. **Write or update tests** if you change behavior. Untested changes to core policy or risk logic will not be merged.

4. **Update documentation** if you change public behavior, CLI commands, or configuration.

5. **Run validation** (see above) and paste output in the PR template.

6. **Open the pull request** with a clear title and filled-out template.

7. **Respond to review feedback** promptly. Stale PRs may be closed.

### What makes a good PR

- Solves one clear problem
- Includes tests when behavior changes
- Updates docs when usage changes
- Preserves secure defaults
- Avoids unrelated formatting changes or large rewrites
- Is easy to review in a single sitting

---

## Reporting bugs

Use the [bug report template](./.github/ISSUE_TEMPLATE/bug_report.md).

Include:
- Exact steps to reproduce
- Environment details (OS, Python version, project version)
- Relevant logs or output
- The policy or config that was active

---

## Requesting features

Use the [feature request template](./.github/ISSUE_TEMPLATE/feature_request.md).

Include:
- The problem you're trying to solve
- The behavior you want
- Any alternatives you've considered

Small, focused requests are easier to evaluate and act on.

---

## Security issues

**Do not open public issues for security vulnerabilities.**

Report them privately using GitHub Security Advisories. See [SECURITY.md](./SECURITY.md) for details.
