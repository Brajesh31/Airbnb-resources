# Deployment

## Hosting model
The current project is suitable for static hosting. Publish the repository's HTML, CSS, and asset files without a build step.

Examples include GitHub Pages, Netlify, Cloudflare Pages, or any web server configured to serve static files. Configure the site root to the repository root, where `index.html` is located.

## Pre-deployment checklist
- [ ] Open the site using a local static server.
- [ ] Confirm all images, stylesheets and SVGs load.
- [ ] Test mobile, tablet and desktop widths.
- [ ] Check keyboard focus and page semantics.
- [ ] Remove OS metadata and editor-only files from version control.
- [ ] Confirm visual assets are owned or appropriately licensed.
- [ ] Confirm the page does not imply real booking or availability.
- [ ] Enable HTTPS on the hosting provider.
- [ ] Configure suitable security headers where supported.

There is no server-side application, environment-specific build, database migration, deployment secret, or production booking functionality to configure.
