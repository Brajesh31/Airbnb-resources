# Architecture and Repository Design

## 1. Purpose

This document describes the actual structure of Airbnb-resources. The repository is a static browser-rendered page, not a full accommodation marketplace. The architecture is intentionally small: HTML provides content and structure, CSS provides presentation, and local files provide visual assets.

## 2. High-level architecture

```text
Visitor's browser
  |
  | HTTP GET /
  v
Static file host or local development server
  |
  +-- index.html
  |     |
  |     +-- references airbnbstyle.css
  |     +-- references local SVG artwork
  |     +-- references local JPEG / WebP images
  |
  +-- airbnbstyle.css
  |     +-- layout and typography
  |     +-- responsive presentation
  |     +-- focus and reduced-motion rules
  |
  +-- static media files
        +-- logo and interface icons
        +-- category and listing imagery

No application server
No API
No database
No authentication
No client-side application bundle
```

## 3. Main components

### 3.1 HTML document

`index.html` is the entry point. It contains the page's navigation presentation, search-like area, category strip, filter presentation, and accommodation-card content. The document is delivered to the browser as a static file.

The markup should remain responsible for meaningful structure and content. Avoid adding large blocks of inline CSS or duplicating the same content unnecessarily. Use semantic elements when they accurately describe the role of the content.

### 3.2 Stylesheet

`airbnbstyle.css` controls the visual layout. It includes the original component styles and responsive refinements. CSS does not fetch listing data, save favorites, submit forms, or perform business operations.

When changing the stylesheet, inspect the cascade. A later selector may override an earlier rule even when the earlier rule appears correct. Keep related rules together and avoid repeatedly appending new override blocks.

### 3.3 Static assets

The repository stores SVG, JPEG, and WebP files at the root. HTML references these files through relative paths. The filename and capitalization must match exactly, especially on case-sensitive hosting systems.

The assets are not a remotely synchronized image library. Changing a filename requires updating every reference and checking all rendered pages.

### 3.4 Documentation and repository automation

The `docs/` directory describes the project and its maintenance. GitHub Actions validates selected files and local references. The README timestamp workflow updates a maintenance timestamp. These workflows do not build or deploy the website.

## 4. Request and rendering lifecycle

1. A visitor requests the hosted site root.
2. The static host returns `index.html`.
3. The browser parses the HTML.
4. The browser requests the linked stylesheet and referenced media.
5. CSS is applied to the document.
6. The browser renders the static page.

There is no application-level request to retrieve live inventory. There is no server-side session or persistent browser state managed by this project.

## 5. Data model and content

Listing information is embedded directly in the HTML. It is presentation content, not a validated listing database. Names, locations, distances, dates, and prices must not be represented as real inventory or current market information.

If the project later needs structured local content, first define the data format and rendering approach. A JSON file alone does not create an API or persistence layer. If user-generated or live content is introduced, the architecture, security, privacy, accessibility, and testing requirements must be redesigned and documented.

## 6. Architectural boundaries

| Capability | Current status | Architectural implication |
|---|---|---|
| Static page rendering | Implemented | Browser plus static host |
| Responsive styling | Implemented in CSS | CSS media queries |
| Local image delivery | Implemented | Relative asset paths |
| Search and filters | Not implemented | No filtering logic |
| Favorites persistence | Not implemented | No storage layer |
| Authentication | Not implemented | No identity provider |
| Booking and availability | Not implemented | No inventory service |
| Checkout and payments | Not implemented | No payment provider |
| API integration | Not implemented | No API client |
| Database persistence | Not implemented | No database connection |

## 7. Dependency policy

The current page has no runtime package dependencies. This is a useful property: there is no dependency installation, dependency vulnerability surface from an application package tree, or build pipeline to maintain.

Do not add a framework or dependency for a small isolated visual change. If a dependency becomes necessary, record:
- the problem it solves;
- why browser-native HTML and CSS are insufficient;
- package name and version policy;
- license and maintenance status;
- security update process;
- impact on install, build, test, and deployment steps.

## 8. Hosting architecture

The page can be hosted on a static file platform. The host must publish the repository root or another directory that contains the entry HTML and all referenced assets. No server-side runtime is required.

Do not configure server rewrites to nonexistent application routes. If client-side routing is introduced later, document route fallback behavior and test direct navigation and refresh.

## 9. Architecture change checklist

Before changing the architecture:
- State the user problem and expected behavior.
- Identify the files and systems affected.
- Consider accessibility, privacy, security, performance, and maintenance.
- Update this document and the documentation index.
- Update installation and deployment instructions if prerequisites change.
- Update CI to validate the new behavior.
- Avoid describing a planned component as implemented until it is committed and tested.
