# .github

Default community health files for the public repositories of
[@ValentinTorassa](https://github.com/ValentinTorassa). GitHub shows them in every repository that
doesn't have its own:

- [SECURITY.md](SECURITY.md): how to report a vulnerability privately.
- [CONTRIBUTING.md](CONTRIBUTING.md): how to propose a change.
- [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md): adapted from the Contributor Covenant 2.1.
- [Issue templates](ISSUE_TEMPLATE) and a [pull request template](PULL_REQUEST_TEMPLATE.md).

A repository with its own file keeps using its own.

## Shared workflows

Reusable GitHub Actions workflows, defined once so a runner or action bump is a single change:

- [`security-node.yml`](.github/workflows/security-node.yml): npm audit with a dated allowlist
  ([`scripts/npm-audit.mjs`](scripts/npm-audit.mjs)) plus CodeQL. Call it from a job with
  `uses: ValentinTorassa/.github/.github/workflows/security-node.yml@main`; private repositories pass
  `codeql: false`.
