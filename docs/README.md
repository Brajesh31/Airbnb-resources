# Project Documentation

This documentation set is the operating manual for **Airbnb-resources**, an independent static accommodation-marketplace interface built with HTML and CSS. It describes the repository as it exists, explains how to work on it safely, and records the boundaries between current behavior and possible future work.

> **Project boundary:** This repository is not Airbnb, is not affiliated with Airbnb, and does not provide accommodation inventory or travel services. Property names, images, prices, dates, and distance labels are sample presentation content. There is no real search, booking, availability, account, payment, or listing-management service.

## 1. Start here

| Your goal | Read this |
|---|---|
| Preview the page locally | [Installation](installation.md) |
| Understand the files and page composition | [Architecture](architecture.md) |
| Change HTML, CSS, or assets | [Development](development.md) |
| Follow markup and stylesheet conventions | [HTML and CSS standards](html-css-style-guide.md) |
| Check the experience with keyboard and assistive technology | [Accessibility](accessibility.md) |
| Test the page before committing | [Browser testing](browser-testing.md) |
| Understand image and icon handling | [Assets and content](assets-and-content.md) |
| Publish the static files | [Deployment](deployment.md) |
| Check page metadata and discoverability | [SEO and metadata](seo-and-metadata.md) |
| Review security and privacy boundaries | [Security](security.md) and [Privacy](privacy.md) |
| Understand absent services | [API](api.md) and [Database](database.md) |
| Diagnose a problem | [Troubleshooting](troubleshooting.md) |
| Understand quality gates | [Quality assurance](quality-assurance.md) |
| Prepare a repository change or release | [Release process](release-process.md) |

## 2. Current implementation at a glance

| Concern | Current implementation |
|---|---|
| Entry point | `index.html` |
| Styling | `airbnbstyle.css` |
| Runtime | Browser rendering of static files |
| Assets | SVG, JPEG, and WebP files stored at repository root |
| JavaScript application | None |
| Package manifest / build system | None |
| API / backend | None |
| Database / persistence | None |
| Automated validation | GitHub Actions static checks |
| Deployment model | Static file hosting |

The project can be previewed without installing dependencies. A local HTTP server is recommended because it reproduces the URL and relative-path behavior of static hosting more accurately than opening the HTML file directly.

## 3. Repository map

- `index.html`: page structure and sample content.
- `airbnbstyle.css`: presentation, layout, responsive rules, focus styles, and motion preferences.
- Root-level SVG files: logo and interface artwork.
- Root-level JPEG and WebP files: sample category and accommodation imagery.
- `docs/`: technical and operational documentation.
- `.github/workflows/ci.yml`: static repository validation.
- `.github/workflows/update-readme.yml`: scheduled README timestamp maintenance.
- `.github/ISSUE_TEMPLATE/`: structured issue forms.
- `CONTRIBUTING.md`, `SECURITY.md`, `SUPPORT.md`: contribution, security, and support guidance.

See [Architecture](architecture.md) for the relationship between these parts.

## 4. How to use this documentation

Read the guide relevant to the change before editing. Treat statements about current behavior as authoritative only when they agree with the actual HTML, CSS, and asset files. A roadmap item is a proposal, not evidence that a feature exists.

When a change affects multiple areas, update the relevant documentation in the same commit. For example, changing the entry point or adding a build step requires updates to installation, architecture, development, deployment, and CI documentation.

## 5. Documentation maintenance rules

1. Use concrete repository paths and commands that work from the repository root.
2. Label future ideas as planned or proposed.
3. Do not document fictional endpoints, schemas, environment variables, or user flows as implemented.
4. Explain why a concern is not applicable when the repository does not contain that subsystem.
5. Prefer examples that can be copied and run.
6. Keep links relative for repository files and verify them before merging.
7. When a file or behavior changes, update this index and any affected guide.
8. Keep the README concise enough for the landing page; put operational detail in this documentation set.

## 6. Scope and non-goals

The current project is a frontend learning exercise. It is not intended to process personal information, accept payments, authenticate users, publish real listings, or make travel reservations. Implementing any of those capabilities would be a substantial product and architecture change, not a routine documentation update.

Before introducing a new subsystem, document its purpose, data flow, threat model, accessibility impact, operational ownership, and testing strategy. Do not add infrastructure merely to make a static demonstration appear more complex.
