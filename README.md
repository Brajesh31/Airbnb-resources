# 🏡 Airbnb-Inspired Accommodation UI

A static, educational accommodation marketplace interface built with **HTML and CSS**. The page demonstrates a marketplace-style navigation bar, category browsing, filter controls, and sample accommodation cards.

<p align="center">
  <img src="logo.svg" alt="Project logo" width="200">
</p>

> [!NOTE]
> This is an independent learning project. It is not affiliated with, endorsed by, or an official product of Airbnb. All property details, distances, dates and prices are sample content. The interface does not support real bookings or live availability.

## ✨ Project Overview

The repository contains a single-page static UI exercise with locally stored SVG, JPEG and WebP assets. It is intended for practicing page structure, CSS layout, responsive behavior, and asset organization.

### Current capabilities

| Area | Current state |
|---|---|
| Navigation and search bar appearance | Static presentation |
| Category strip | Static presentation |
| Filter controls | Visual only |
| Accommodation cards | Static sample content |
| Favorite icons | Visual only, not saved |
| Responsive layout | CSS refinements included |
| API / Backend | Not implemented |
| Database | Not implemented |
| Booking / Availability / Payment | Not implemented |
| Authentication / User accounts | Not implemented |
| JavaScript application | Not included |

## 🖥️ Preview

The site is composed from `index.html`, `airbnbstyle.css`, and local assets. Run it locally to inspect the complete page.

## 🧰 Technology Stack

- **HTML5** for page structure.
- **CSS3** for layout and responsive presentation.
- **SVG** for icons and logo artwork.
- **JPEG / WebP** for local category and listing images.

There is no framework, bundler, package manager, server-side runtime, or database dependency.

## 🚀 Run Locally

### 1. Clone the repository

```bash
git clone https://github.com/Brajesh31/Airbnb-resources.git
cd Airbnb-resources
```

### 2. Start a local static server

Using Python:

```bash
python -m http.server 8000
```

### 3. Open the site

Visit:

```text
http://localhost:8000
```

Stop the server with `Ctrl+C`.

You can also open `index.html` directly, but a local server provides a more representative static-hosting environment.

## 📁 Repository Structure

```text
Airbnb-resources/
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md
│   │   ├── config.yml
│   │   ├── documentation.md
│   │   └── feature_request.md
│   ├── workflows/
│   │   ├── ci.yml
│   │   └── update-readme.yml
│   ├── dependabot.yml
│   └── PULL_REQUEST_TEMPLATE.md
├── docs/
│   ├── README.md
│   ├── accessibility.md
│   ├── api.md
│   ├── architecture.md
│   ├── database.md
│   ├── deployment.md
│   ├── development.md
│   ├── faq.md
│   ├── installation.md
│   └── troubleshooting.md
├── assets (root-level SVG, JPEG and WebP files)
├── index.html
├── airbnbstyle.css
├── .editorconfig
├── .env.example
├── .gitattributes
├── .gitignore
├── CHANGELOG.md
├── CITATION.cff
├── CODEOWNERS
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── LICENSE
├── README.md
├── ROADMAP.md
├── SECURITY.md
└── SUPPORT.md
```

Assets are currently stored at the repository root, rather than in a dedicated `assets/` folder. The tree label above describes their role, not an actual directory.

## 🧪 Validation

The GitHub Actions workflow `.github/workflows/ci.yml` checks that key files exist, local HTML/CSS asset references resolve, the page has required metadata, and Markdown files are non-empty with valid local links.

This is a static repository check, not a browser integration test or a guarantee of accessibility.

For manual checks:

- Test at phone, tablet and desktop widths.
- Navigate using the keyboard and confirm visible focus.
- Check browser console and network errors.
- Test 200% zoom and reduced-motion settings.
- Review image rights before publishing.

## ♿ Accessibility and Responsive Design

The stylesheet includes responsive refinements, visible keyboard focus styling, and reduced-motion handling. Accessibility still requires manual review. See [docs/accessibility.md](docs/accessibility.md).

## 📚 Documentation

Start with [docs/README.md](docs/README.md) for the full documentation index.

| Guide | Description |
|---|---|
| [Installation](docs/installation.md) | Local setup and preview |
| [Development](docs/development.md) | Editing and validation workflow |
| [Architecture](docs/architecture.md) | Static project structure |
| [Accessibility](docs/accessibility.md) | Accessibility practices and limitations |
| [API](docs/api.md) | API status |
| [Database](docs/database.md) | Data persistence status |
| [Deployment](docs/deployment.md) | Static hosting |
| [FAQ](docs/faq.md) | Common questions |
| [Troubleshooting](docs/troubleshooting.md) | Common local issues |

## 🗺️ Roadmap

See [ROADMAP.md](ROADMAP.md). Planned work is not implemented functionality.

## 🤝 Contributing

Contributions are welcome for focused improvements to HTML semantics, CSS, responsive layouts, accessibility, asset organization, and documentation.

Read [CONTRIBUTING.md](CONTRIBUTING.md) before opening a pull request. Do not add unlicensed media, private data, credentials, or unnecessary third-party tracking.

## 🔐 Security

This is a static project and does not process accounts, payments, bookings, or personal data. Read [SECURITY.md](SECURITY.md) before reporting a security issue.

## 📄 License

Released under the [MIT License](LICENSE).

## 👨‍💻 Maintainer

**Brajesh Kumar**  
GitHub: [@Brajesh31](https://github.com/Brajesh31)

---

*Independent educational project. Airbnb is a trademark of its respective owner. This repository does not claim affiliation or endorsement.*

Last updated: 2026-11-16 02:20 UTC
