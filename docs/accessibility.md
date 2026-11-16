# Accessibility

Accessibility should be considered part of the interface, not a final polish step.

## Current review points
- Use a single clear page title and logical heading hierarchy.
- Give informative images concise alternative text.
- Mark purely decorative icons as hidden from assistive technology.
- Ensure every interactive control has an accessible name.
- Provide visible focus indicators and keyboard access.
- Preserve meaningful text contrast and avoid conveying status through color alone.
- Allow layouts and text to reflow at narrow widths and browser zoom.
- Respect `prefers-reduced-motion`.

## Known limitations
The present page is a static visual reproduction. Search, filter, profile, menu, and favorite artwork do not implement their advertised behavior. A visual button without an action can mislead keyboard and screen-reader users. Before describing a control as functional, implement its behavior, accessible state, and keyboard interaction.

## Manual test checklist
- [ ] Navigate the page using Tab and Shift+Tab only.
- [ ] Confirm focus is visible and follows a sensible order.
- [ ] Test at 200% zoom and a narrow viewport.
- [ ] Check headings and landmarks in a screen reader.
- [ ] Confirm images have appropriate alternative text.
- [ ] Check color contrast for text and controls.
- [ ] Verify reduced-motion preferences are respected.
