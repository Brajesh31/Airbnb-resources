# Airbnb-style Web Page

This repository is a static HTML/CSS interface inspired by an accommodation marketplace. It includes a navigation bar, search controls, filter artwork, listing cards, and local image/SVG assets.

## Contents

- `index.html` - page markup and listing content.
- `airbnbstyle.css` - layout, responsive styling, and visual treatment.
- `*.svg`, `*.jpeg`, and `*.webp` - interface and listing assets.

This is an educational reproduction and is not affiliated with Airbnb. Branding and third-party imagery should be replaced or used only with appropriate permission.

## Run locally

No build system is required. Open `index.html` in a browser, or serve the directory:

```powershell
python -m http.server 8000
```

Then visit `http://localhost:8000`. A local server is recommended so asset paths behave consistently.

## Development

Keep asset paths relative, test the page at narrow and wide viewport sizes, and check keyboard focus, readable contrast, image alternatives, and layout overflow. Avoid adding third-party tracking or collecting user input without a documented purpose.

See [docs/development.md](docs/development.md) and [docs/accessibility.md](docs/accessibility.md).

## Ownership

Maintained by Brajesh Kumar (`brajesh31`).

Last updated: 2026-10-30 00:43 UTC
