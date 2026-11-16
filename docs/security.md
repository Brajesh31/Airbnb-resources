# Security Practices

## Current security scope
This repository is a static HTML and CSS project. It has no backend, authentication, database, payment processing, user accounts, or API. Security work therefore focuses on repository integrity, asset safety, hosting configuration, and avoiding accidental publication of sensitive material.

## Secrets
No secrets are required to run the current project. Never commit API keys, access tokens, passwords, private keys, production credentials, database connection strings, or private user data.

If a secret is committed, deleting it in a later commit does not make it safe. Revoke or rotate the exposed credential and follow the provider's incident process.

## Static content and scripts
The page does not require JavaScript application code. Before adding scripts, review source, purpose, permissions, maintenance status, and update process. Avoid unnecessary third-party scripts.

If user-controlled content is introduced, do not insert it into HTML as trusted markup. Define safe encoding and validation rules before implementation.

## SVG and media
Review externally sourced SVG files. SVG can contain active or externally referenced content. Prefer simple static artwork and avoid untrusted embedded scripts or unnecessary references. Verify rights and source for media.

## Hosting security
For public deployment, use HTTPS, protect hosting account access, grant deployment workflows minimum permissions, review domain and DNS configuration, and configure appropriate security headers where supported. Test a Content Security Policy against actual resources before enforcing it.

## GitHub Actions
Workflows should use minimum required permissions. Review third-party actions and their pinning strategy. Do not expose secrets to untrusted pull-request code. The static CI workflow requires read access to repository contents; the README timestamp workflow requires write access to commit its update.

## Vulnerability reporting
Report suspected vulnerabilities privately to the maintainer through GitHub. Include affected file, impact, and sanitized reproduction steps. Do not publish exploit details or credentials in a public issue. See the root [SECURITY.md](../SECURITY.md).
