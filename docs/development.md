# Development Guide

## 1. Development model

Airbnb-resources is maintained as a static HTML and CSS project. A developer edits source files directly and previews the result in a browser. There is currently no compilation, bundling, package installation, transpilation, or backend startup.

The absence of a build tool is intentional. Keep the workflow simple unless the project develops a concrete requirement that justifies additional tooling.

## 2. Files to know

| Path | Responsibility | Change it when |
|---|---|---|
| `index.html` | Page structure and sample content | Changing sections, labels, links, or listing markup |
| `airbnbstyle.css` | Layout and visual styling | Changing spacing, typography, colors, responsive behavior, or focus |
| Root SVG files | Logo and interface artwork | Replacing or correcting vector assets |
| Root JPEG/WebP files | Sample imagery | Replacing sample images |
| `docs/` | Technical and operational guides | Changing how the project works or is maintained |
| `.github/workflows/` | Automated repository checks | Changing validation or scheduled maintenance |

## 3. Recommended workflow

1. Pull the latest `main` branch.
2. Read the relevant documentation.
3. Inspect the existing HTML and CSS before editing.
4. Make one focused change at a time.
5. Preview through a local static server.
6. Test desktop and narrow viewport behavior.
7. Test keyboard navigation and visible focus.
8. Check Console and Network panels.
9. Run or allow GitHub Actions static checks.
10. Update documentation if behavior, paths, or project requirements changed.
11. Review the final diff before committing.

Useful Git commands:

```bash
git switch main
git pull --ff-only origin main
git status --short
git diff
```

## 4. HTML practices

- Keep a valid document structure with a language attribute, character encoding, viewport metadata, and a meaningful title.
- Use headings in a logical hierarchy.
- Use semantic landmarks where appropriate, such as `header`, `nav`, `main`, and `footer`.
- Use buttons for actions and anchors for navigation.
- Give controls an accessible name.
- Use descriptive alternative text for informative images and empty alt text for decorative images.
- Avoid duplicate IDs.
- Keep content understandable when CSS is unavailable.
- Do not create controls that appear functional but have no defined action without clearly communicating their demonstration-only nature.

## 5. CSS practices

- Keep styling in `airbnbstyle.css`.
- Prefer class selectors with clear, stable names.
- Avoid excessive specificity and repeated override blocks.
- Use responsive units where they improve reflow.
- Check flex and grid children for overflow and unintended minimum widths.
- Keep focus styles visible.
- Respect the user's reduced-motion preference.
- Avoid relying on color alone to convey meaning.
- Test long text, large zoom, and narrow widths.

Before appending a CSS rule, search for the existing selector and determine whether the original declaration should be updated instead. Repeatedly appending override blocks makes the cascade difficult to maintain.

## 6. Asset changes

Before adding an image or icon:
1. Confirm the asset is needed.
2. Confirm its source and permission to use it.
3. Prefer optimized, appropriately sized files.
4. Use a descriptive filename.
5. Match the file extension to its actual format.
6. Update the HTML reference.
7. Add suitable alt text or mark it decorative.
8. Check that the image loads from a local server.
9. Document material licensing restrictions.

See [Assets and content](assets-and-content.md).

## 7. JavaScript and feature additions

There is no JavaScript application in the current repository. Do not describe visual controls as functional. If interaction is proposed, define the exact behavior first, including keyboard operation, focus management, empty states, errors, and persistence expectations.

A small browser-native behavior may be possible without a framework, but it still requires tests and documentation. Any new script must be reviewed for security, privacy, accessibility, and maintenance cost. Update the architecture, installation, testing, and deployment guides if the runtime changes.

## 8. Local validation

Start the server:

```bash
python -m http.server 8000
```

Then test:
- the page at desktop and mobile widths;
- all local images and icons;
- visible focus with keyboard navigation;
- text wrapping and horizontal overflow;
- browser console and network requests;
- 200% zoom and reduced-motion settings.

The repository CI performs static checks. It does not replace visual or assistive-technology testing.

## 9. Git hygiene

- Keep commits focused and use messages that explain the change.
- Do not commit editor caches, operating-system metadata, build output, credentials, or local server logs.
- Do not add generated files unless they are required deliverables.
- Review `git status` before committing.
- Review `git diff --check` for whitespace errors.
- Confirm the commit contains only intended files.

## 10. Documentation obligations

If a change adds a dependency, environment variable, script, route, external service, or deployment requirement, update the relevant guides in the same change. If a feature remains planned, keep it in the roadmap rather than documenting it as current behavior.
