# Project Roadmap

This roadmap records possible improvements to the independent static interface. It is not a commitment to build a commercial accommodation marketplace. Planned work must be reviewed for scope, value, accessibility, licensing, and maintenance cost before implementation.

## Current baseline

The project currently contains a static HTML page, a CSS stylesheet, local SVG/JPEG/WebP assets, repository documentation, issue templates, and GitHub Actions checks. There is no JavaScript application, API, database, authentication, booking, or payment capability.

## Completed repository foundations

- [x] Document the static project scope and non-affiliation statement.
- [x] Provide local installation and preview instructions.
- [x] Document architecture, development, deployment, and troubleshooting.
- [x] Add accessibility and responsive design guidance.
- [x] Add browser testing and quality assurance guidance.
- [x] Document asset handling, content accuracy, and licensing review.
- [x] Document privacy, security, SEO metadata, and release practices.
- [x] Add issue and pull request templates.
- [x] Add static file and local-reference validation.
- [x] Configure Dependabot for GitHub Actions dependencies.
- [x] Remove tracked operating-system metadata files.

## Potential improvements

### Content and asset quality
- [ ] Review every bundled image, icon, and logo for source and reuse permission.
- [ ] Replace any asset whose rights cannot be established.
- [ ] Create a verified asset inventory if the media collection grows.
- [ ] Review sample listing content for consistency and clear labeling.

### Frontend quality
- [ ] Perform a documented browser review at phone, tablet, and desktop widths.
- [ ] Complete a manual accessibility review with keyboard and assistive technology.
- [ ] Review image dimensions and optimize oversized files where necessary.
- [ ] Consolidate legacy CSS declarations if a verified visual comparison can be maintained.

### Automation
- [ ] Consider an HTML validator if it provides useful signal beyond current checks.
- [ ] Consider browser smoke tests if the project gains meaningful interactive behavior.
- [ ] Review workflow action versions and permissions periodically.
- [ ] Add deployment automation only after a hosting target and release process are confirmed.

## Conditional feature exploration

These ideas should be considered only when there is a clear learning objective:
- [ ] Add accessible client-side category or filter behavior.
- [ ] Add a local data source for sample cards if content duplication becomes difficult to maintain.
- [ ] Add a small JavaScript interaction with documented keyboard behavior and tests.

Any such work changes the current implementation and must update architecture, installation, testing, privacy, and security documentation.

## Explicitly out of scope for the current repository

- Real accommodation inventory or availability.
- User accounts and identity verification.
- Reservations, checkout, or payment processing.
- Owner dashboards or listing management.
- Production customer data or personal-data collection.
- Claims of affiliation with Airbnb.

## Prioritization principles

Prioritize correctness, accessibility, asset rights, and maintainability over adding features for appearance alone. Do not mark an item complete until the implementation is committed and validated. Keep this roadmap synchronized with actual repository state.
