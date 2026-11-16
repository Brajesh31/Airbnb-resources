# Privacy and Data Handling

## Current scope
The current repository is a static HTML and CSS interface. It does not implement user accounts, login, booking, checkout, payment, favorites persistence, or a profile database. It has no application backend or database.

## Static delivery is not a universal privacy guarantee
A static site may still generate ordinary web server logs, and a hosting provider may process technical request metadata. Browser extensions, hosting analytics, or third-party resources may also affect privacy if introduced. The repository does not define a hosting provider's logging or retention practices. Review the provider's policies and settings before deployment.

## No sensitive data collection
Do not add forms that collect passwords, payment details, identity documents, precise location, or other sensitive information to this static demonstration. A frontend-only page is not an appropriate place to collect and store such data.

If a legitimate feature requires personal data, define its purpose, lawful basis where applicable, minimum necessary fields, access controls, retention, deletion, and user-facing notice before implementation.

## Third-party services
The current project does not require an external API or analytics provider. Avoid third-party scripts without a clear reason. They can introduce tracking, performance cost, security exposure, and additional privacy obligations.

Before adding a provider, document what data is sent, why it is sent, who receives it, where it is processed, how long it is retained, how users are informed, and how the integration can be disabled.

## Future data features
Any future account, booking, or preference feature requires a new privacy review covering data mapping, collection notices, access and correction, deletion, retention, security, backups, and incident response. A browser implementation is not automatically privacy-safe.

## Repository hygiene
Never commit passwords, API tokens, private keys, real customer data, personal contact details without permission, private production logs, or database exports containing personal data. Use sanitized examples in issues and documentation.

## Questions and reporting
For privacy concerns, contact the maintainer privately through GitHub. Do not publish personal information or sensitive evidence in a public issue. See [Security](security.md) and [Support](../SUPPORT.md).
