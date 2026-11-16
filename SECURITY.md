# Security Policy

## Supported project scope

Airbnb-resources is a static HTML and CSS learning project. It currently has no backend, authentication, database, payment processing, user accounts, or API. This policy focuses on repository integrity, static content, media, hosting configuration, and accidental publication of sensitive material.

## Reporting a vulnerability

Please report suspected vulnerabilities privately to the maintainer, **Brajesh Kumar** (GitHub: [@Brajesh31](https://github.com/Brajesh31)), through GitHub. Do not publish exploit details, credentials, access tokens, or personal information in a public issue.

A useful report includes a concise description, affected file or workflow, impact and realistic attack scenario, sanitized reproduction steps, browser/environment/commit information, and suggested mitigation if known. Do not attach live secrets or private production data.

## Response expectations

The maintainer will review the report, attempt to reproduce the issue, assess impact, and determine an appropriate fix or clarification. Response time depends on availability and severity. No formal service-level agreement is promised.

Please allow a reasonable opportunity to investigate and address a confirmed issue before public disclosure. If the report is not reproducible, additional details may be requested.

## Security expectations for contributors

- Never commit API keys, passwords, tokens, private keys, or production credentials.
- Do not add client-side collection of passwords, payment data, or sensitive personal information.
- Review external scripts and dependencies before adding them.
- Inspect externally sourced SVG files for active or unexpected content.
- Verify media source and reuse rights.
- Keep GitHub Actions permissions limited to what each workflow requires.
- Do not expose secrets to untrusted pull-request code.
- Use HTTPS for public deployment.
- Avoid publishing private logs, personal information, or database exports.

## Credential exposure

If a credential is accidentally committed, removing it in a later commit is not sufficient. Revoke or rotate the credential immediately, review access logs where available, and follow the provider's incident response instructions.

## Scope limitations

The repository does not implement a production marketplace. The absence of booking, account, or payment features is not a security vulnerability. If such functionality is proposed, it requires a separate architecture and threat-model review.

## Additional guidance

See [docs/security.md](docs/security.md), [docs/privacy.md](docs/privacy.md), and [SUPPORT.md](SUPPORT.md).
