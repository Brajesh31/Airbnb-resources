# Troubleshooting

## Images or icons do not load
- Start the local server from the repository root.
- Check filename case and spelling.
- Confirm the referenced asset exists in the repository.
- Inspect the browser Network panel for 404 responses.

## CSS changes are not visible
- Hard-refresh the browser.
- Confirm the stylesheet link points to `airbnbstyle.css`.
- Check the browser console for stylesheet errors.
- Verify that a later CSS rule is not overriding the change.

## Layout overflows on mobile
- Inspect fixed widths and large horizontal padding.
- Check flex items for missing wrapping or minimum-width constraints.
- Test at 360px and 390px viewport widths.
- Inspect long headings and text labels.

## Page opens but controls do nothing
This is expected. Search, category, filter, profile, menu, and favorite items are visual-only. There is no JavaScript behavior or backend.

## Local server command is unavailable
Install Python or use another static file server. Opening `index.html` directly is also possible for this project.
