# Repository Maintenance Guide

## 1. Purpose

This guide describes routine maintenance for the repository and its automation. Maintenance should preserve a small, understandable static project rather than add infrastructure without a need.

## 2. Routine review

Periodically review:
- whether README instructions still work;
- whether documentation matches the actual files;
- whether all local links and asset references resolve;
- whether media reuse rights are known;
- whether issue templates still request useful information;
- whether GitHub Actions workflows still run;
- whether workflow permissions remain minimal;
- whether ignored files or generated artifacts have entered version control;
- whether the roadmap reflects realistic, relevant work.

## 3. GitHub Actions maintenance

The static CI workflow checks repository file integrity and local references. The README automation updates a timestamp. Neither workflow deploys the site or performs browser testing.

When modifying a workflow:
1. understand its trigger and permissions;
2. keep permissions to the minimum needed;
3. use a stable runner and maintained actions;
4. review third-party action changes;
5. avoid exposing secrets to untrusted code;
6. run the workflow and inspect job logs;
7. document any new required secret or permission.

A green workflow only confirms the checks that workflow actually performs.

## 4. Dependency review

The current project has no application package manifest. Dependabot is configured for GitHub Actions dependencies. Do not add package dependency updates or package-manager configuration unless the repository introduces actual application dependencies.

Review action updates and workflow changes rather than accepting automated changes blindly.

## 5. File hygiene

Do not commit operating-system metadata, editor caches, temporary screenshots, local server logs, build output, or credentials. Review `git status --short` and `git diff --check` before committing.

Do not delete editor configuration or repository metadata solely because it looks unfamiliar. Confirm whether contributors rely on it and whether it is intentionally tracked.

## 6. Documentation maintenance

When the implementation changes, update every affected guide. Examples:
- adding JavaScript changes development, architecture, testing, and security guidance;
- adding an API changes architecture, API, privacy, and security guidance;
- adding persistence changes database, privacy, backup, and deployment guidance;
- changing the publish root changes installation and deployment instructions;
- adding new documentation requires updating this index and README links.

Remove stale claims rather than leaving contradictory instructions.

## 7. Incident and rollback readiness

For a broken public deployment, identify the deployed commit and redeploy the last known-good commit if necessary. For an exposed credential, revoke or rotate it immediately. For a suspected vulnerability, use the private reporting process in SECURITY.md.

## 8. Maintenance record

For significant maintenance work, record the date, affected files, reason, validation performed, and unresolved risks in the changelog or release notes. Avoid creating ceremonial records for every trivial edit.

## 9. Maintenance checklist

- [ ] Main page and stylesheet load.
- [ ] Local asset references resolve.
- [ ] Documentation links resolve.
- [ ] README matches repository structure.
- [ ] Workflows pass or have understood, documented failures.
- [ ] No secrets or unnecessary generated files are tracked.
- [ ] Asset rights are reviewed.
- [ ] Known limitations are accurately stated.
- [ ] Roadmap and changelog reflect the actual state.
