<!--
Before submitting:
  - Keep this PR focused. One problem, one solution.
  - If this is a large change, consider opening an issue first to discuss approach.
  - Security-sensitive changes (policy, risk, audit, approvals, secrets, execution)
    should include a review note below.
-->

## Summary

<!-- What does this PR change, and why? -->

## Type of change

- [ ] Bug fix
- [ ] Feature
- [ ] Refactor / cleanup
- [ ] Documentation
- [ ] Security hardening
- [ ] Test or CI update
- [ ] Dependency update
- [ ] Other: <!-- describe -->

## Related issues

<!-- Link any related issues. Use "Closes #N" to auto-close on merge. -->

Closes #

## Validation

<!--
Paste the commands you ran and their output.
At minimum, run the standard validation suite before requesting review:

  ruff format src tests demo examples
  ruff check src tests demo examples
  pytest -q
  bandit -r src demo examples -c pyproject.toml
  pip-audit -r requirements-dev.txt

Add any additional steps specific to this change.
-->

```text

```

## Checklist

- [ ] Change is focused — no unrelated edits
- [ ] Tests added or updated where behavior changed
- [ ] Documentation updated where usage changed
- [ ] Ran local validation suite (see above)
- [ ] Secure defaults preserved — this does not weaken policy enforcement, audit logging, risk checks, or approval controls
- [ ] No new hardcoded secrets, credentials, or sensitive values introduced

## Security impact

<!--
Does this change touch:
  - Policy enforcement logic
  - Risk scoring or action classification
  - Audit log generation or storage
  - Approval or role-based access control
  - Secrets access or handling
  - External tool execution or brokered execution boundaries
  - CI/CD pipelines or dependency chains

If yes, describe the impact and how it was reviewed.
-->

- [ ] No security impact
- [ ] Has security impact — reviewed and described above
- [ ] Needs security review before merge

## Notes for reviewers

<!-- Flag anything reviewers should pay close attention to. -->
