# Contributing Guide

Thank you for considering a contribution to Airbnb-resources. This repository is an independent educational static interface. Contributions should improve clarity, maintainability, accessibility, responsive presentation, asset handling, or documentation without implying that it provides real accommodation services.

## 1. Project scope

The current implementation uses plain HTML and CSS with local SVG, JPEG, and WebP assets. It has no JavaScript application, backend, API, database, authentication, booking, availability, or payment service.

Good contribution areas include semantic HTML, responsive CSS, keyboard focus, accessibility, image optimization, asset organization, accurate metadata, documentation, and repository automation. Do not add infrastructure or dependencies without explaining the concrete requirement and maintenance cost.

## 2. Before starting

1. Read the [documentation index](docs/README.md).
2. Check existing issues to avoid duplicate work.
3. Identify the exact behavior or defect being addressed.
4. Confirm that proposed assets can legally be redistributed.
5. Keep the change focused and avoid unrelated formatting churn.

## 3. Local setup

```bash
git clone https://github.com/Brajesh31/Airbnb-resources.git
cd Airbnb-resources
python -m http.server 8000
```

Open `http://localhost:8000`. No npm installation, build command, or database is required.

## 4. Code and content standards

- Keep page structure in `index.html`.
- Keep presentation rules in `airbnbstyle.css`.
- Prefer semantic elements and meaningful headings.
- Use buttons for actions and anchors for navigation.
- Provide suitable alternative text.
- Preserve visible keyboard focus.
- Respect reduced-motion preferences.
- Avoid duplicated CSS rules and unnecessary overrides.
- Use accurate sample content and preserve the independent-project disclaimer.
- Do not imply that static controls perform real search, booking, or payment operations.

See [HTML and CSS Style Guide](docs/html-css-style-guide.md).

## 5. Asset requirements

Before adding or replacing an asset, confirm its source, license, modification rights, attribution requirements, dimensions, and intended use. Publicly accessible does not mean freely reusable. Review SVG source before committing externally sourced files.

Do not add copyrighted brand assets or third-party media without permission. See [Assets and Content](docs/assets-and-content.md).

## 6. Validation expectations

For a visual or structural change, run the page through a local HTTP server, check phone/tablet/desktop widths, verify local images and stylesheet requests, inspect Console and Network panels, test keyboard navigation and visible focus, check 200% zoom and reduced motion, and verify changed documentation links.

GitHub Actions performs static file and link checks. It does not replace manual browser review. See [Browser Testing](docs/browser-testing.md) and [Quality Assurance](docs/quality-assurance.md).

## 7. Pull request content

Explain the problem, approach, affected files, visible behavior changes, tests performed, known limitations, and asset licensing details. Use the repository pull request template. Include screenshots for visual changes where practical, but do not use screenshots as a substitute for functional and keyboard checks.

## 8. Commit hygiene

Use focused commits with clear messages. Do not commit editor caches, OS metadata, build output, local logs, secrets, or private data. Review `git status` and `git diff --check` before committing.

## 9. Security and privacy

Never commit credentials, tokens, private keys, customer data, or sensitive personal information. Do not add forms that collect passwords or payment details to this static demonstration. Report suspected vulnerabilities privately according to [SECURITY.md](SECURITY.md).

## 10. Review principles

Contributions are reviewed for correctness, scope, readability, accessibility, maintainability, licensing, and consistency with the documented project. Changes may be requested when a contribution introduces unsupported claims, unnecessary dependencies, inaccessible controls, or unverified media.

## 11. Maintainer

Repository maintainer: **Brajesh Kumar**  
GitHub: [@Brajesh31](https://github.com/Brajesh31)
