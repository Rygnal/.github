# Security Policy

Rygnal builds runtime governance and security controls for AI-agent tool actions.
We take security seriously and appreciate responsible disclosure from the community.

## Supported versions

| Repository | Supported |
|---|---|
| `rygnal-core` | ✅ Latest main branch |

## Reporting a vulnerability

**Do not open public GitHub issues for suspected security vulnerabilities.**

Report security concerns privately through one of these channels:

1. **GitHub Security Advisories** (preferred)
   Use the "Report a vulnerability" button on the Security tab of the affected repository.
   This creates a private advisory visible only to maintainers.

2. **Direct contact**
   If you have an established private channel with the maintainers, use that.

We aim to acknowledge reports within **48 hours** and provide an initial assessment within **7 days**.

## What to include

The more detail you provide, the faster we can triage and respond.

- Clear description of the vulnerability
- Affected repository, file path, or component
- Minimal steps to reproduce
- Potential impact and attack surface
- Suggested mitigation or fix, if known
- Your contact preference for follow-up

## Scope

Security-sensitive areas in Rygnal include:

| Area | Why it matters |
|---|---|
| **Policy enforcement** | Bypass could allow unauthorized tool actions |
| **Risk scoring** | Manipulation could suppress required approvals |
| **Runtime interception** | In-process bypass defeats the governance layer |
| **Approval workflows** | Circumvention removes human oversight |
| **Audit logging** | Tampering removes accountability |
| **Secrets handling** | Exposure or unauthorized access |
| **Role-based access** | Privilege escalation |
| **Brokered execution** | Execution boundary violations |
| **CI and dependencies** | Supply chain attacks |

## Out of scope

- Issues in dependencies that have already been publicly disclosed and are being tracked upstream
- Theoretical attacks with no practical path to exploitation
- UI or UX issues with no security impact

## Responsible disclosure

We ask researchers to:

1. Give maintainers reasonable time to investigate and fix confirmed issues before public disclosure.
2. Not exploit the vulnerability beyond what is necessary to confirm it.
3. Not access, modify, or delete data that is not yours.

In return, we commit to:

1. Acknowledging your report promptly.
2. Keeping you informed of progress.
3. Crediting you in the fix disclosure, if you choose.

## Known security architecture decisions

The following are intentional security design choices in Rygnal:

- **Default-block** — tool actions are blocked unless explicitly allowed by policy.
- **Requester ≠ approver** — the agent that requests an action cannot approve it.
- **Immutable audit log** — runtime decisions are logged and cannot be retroactively altered.
- **Out-of-process execution** — the brokered execution model prevents in-process bypass of the governance layer.

If you believe any of these create a security risk, we want to hear from you.
