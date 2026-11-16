# Frequently Asked Questions

## Is this the official Airbnb website?

No. This is an independent educational interface inspired by accommodation marketplace layouts. It is not affiliated with or endorsed by Airbnb. Airbnb is a trademark of its respective owner.

## Can a visitor book a property?

No. The property cards are static samples. There is no booking flow, inventory, availability lookup, reservation management, checkout, or payment processing.

## Are the prices and locations real?

They are sample presentation content. They should not be treated as current, verified, or bookable travel information.

## Do search and filters work?

No. The visible search-like area, category strip, and filter controls are presentation elements. The current repository does not include JavaScript behavior for search or filtering.

## Do favorites save?

No. Favorite artwork is visual only. There is no account system, browser persistence, or server-side favorites service.

## What technologies are used?

The project uses plain HTML and CSS with local SVG, JPEG, and WebP files. There is no frontend framework, JavaScript application, API, or database.

## Do I need Node.js or npm?

No. A browser is sufficient to open the page. Python 3 is a convenient optional local static server. See [Installation](installation.md).

## Why use a local server instead of opening the HTML file?

A local server more closely matches static hosting and makes relative asset paths and network errors easier to inspect. Opening the file directly is possible for a quick preview.

## Is there an environment file?

The repository includes an example file that states no runtime environment variables are currently required. Do not add secrets or credentials.

## Can I deploy it?

Yes. It can be hosted as a static site. Publish the root HTML, CSS, and asset files together. See [Deployment](deployment.md).

## Can I use the bundled images and logos commercially?

Do not assume that an image or logo is free to reuse because it is present in the repository. Verify ownership, license, and permission for each asset before redistribution or commercial use. See [Assets and content](assets-and-content.md).

## Why do some controls look clickable if they do nothing?

The page is a visual learning exercise. Some controls imitate familiar marketplace UI patterns but have no action behind them. This limitation should be clear to anyone viewing or evaluating the project.

## Is the site accessible?

The stylesheet includes some accessibility-oriented refinements, including visible focus styling and reduced-motion handling. That does not establish full conformance. Review [Accessibility](accessibility.md) and complete manual testing.

## Does CI test the page in a browser?

No. The current CI workflow checks required files, local references, basic HTML metadata, and Markdown links. It is not a browser test or accessibility audit. See [Quality assurance](quality-assurance.md).

## How do I report a bug?

Use the GitHub bug report issue template. Include exact reproduction steps, browser, operating system, viewport size, expected behavior, actual behavior, and sanitized evidence.

## How do I propose an improvement?

Read [CONTRIBUTING.md](../CONTRIBUTING.md), check existing issues, and submit a focused proposal. Explain the user benefit and how you validated the change.

## Where can I find the project structure?

See [Architecture](architecture.md) and the repository README.
