# Development Guide

## Project files
- `index.html`: current page structure and sample listing content.
- `airbnbstyle.css`: layout, colors, typography and responsive styling.
- Root SVG, JPEG and WebP files: local visual assets.
- `docs/`: project and maintenance documentation.

There is no JavaScript application, API, database, package manifest, build system, or test framework in the current repository.

## Working practices
1. Keep markup semantic and headings in a logical order.
2. Keep CSS in `airbnbstyle.css` rather than adding inline styles.
3. Keep local asset references relative to the repository root.
4. Use meaningful alt text for informative images and empty alt text for decorative images.
5. Use buttons only for real actions. Current controls are visual samples unless explicitly wired.
6. Never collect passwords, payment details, or personal data in a static demo.
7. Do not use Airbnb's brand assets or third-party images without appropriate rights.

## Local review
- Run a static server from the repository root.
- Inspect widths around 360px, 768px, 1024px and 1440px.
- Check browser console and network panel for missing files.
- Use keyboard-only navigation to check visible focus.
- Check zoom at 200% and reduced-motion settings.
- Confirm every changed image path exists and every documented link works.

Do not add a framework, backend, database, or API simply to make the repository look larger. Add infrastructure only when an implemented feature requires it.
