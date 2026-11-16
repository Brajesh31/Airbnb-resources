# Architecture

## Current architecture
```text
Browser
  |
  +-- index.html
  |     +-- airbnbstyle.css
  |     +-- SVG icons and logo
  |     +-- JPEG category assets
  |     +-- WebP property-card assets
  |
  +-- No backend, database, API, or client-side application bundle
```

The HTML contains the sample navigation, category strip, filter area, and listing cards. The stylesheet controls presentation and responsive layout. Assets are local files referenced with relative paths.

## Not implemented
- Search or filtering logic.
- User accounts and profile management.
- Listing data service or owner dashboard.
- Favorites persistence.
- Booking, availability, checkout, or payments.
- Authentication, authorization, or server-side validation.

Treat property names, dates, distance labels, and prices as sample presentation content only. If dynamic data is required, define feature and privacy requirements before selecting a backend or database. Never imply that a static mockup is a real accommodation marketplace.
