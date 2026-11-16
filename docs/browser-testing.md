# Browser Testing Guide

## Purpose and scope
This guide describes manual browser testing for the static page. The repository's automated workflow checks file existence and local references. It does not launch a browser, execute user journeys, test screen readers, or certify accessibility. Manual testing is required for visual and interaction-related changes.

## Test environment
Record browser name and version, operating system, viewport dimensions, browser zoom, device emulation or physical device, extensions in use, and the commit being tested. Use a clean browser profile when extensions or cache may affect results.

## Core smoke test
1. Start a local static server from the repository root.
2. Open the root page.
3. Confirm the page title and main content.
4. Confirm the stylesheet loads.
5. Confirm all referenced local images and icons load.
6. Scroll through the complete page.
7. Resize the viewport.
8. Check Console and Network for errors.
9. Navigate with the keyboard.
10. Confirm the page does not imply that a booking or transaction can be completed.

## Viewport coverage
Review at 320, 360, 390, 768, 1024, and 1440 CSS pixels or equivalent responsive widths. Look for horizontal scrolling, clipped content, overlapping elements, awkward wrapping, and inconsistent card widths. These are practical review points, not proof of coverage for every device.

## Keyboard test
Use Tab and Shift+Tab to move through controls. Activate links with Enter and buttons with Enter or Space. Verify focus is visible, focus order follows reading order, and no keyboard trap exists. Current visual-only controls should not be assumed to have implemented behavior.

## Developer tools
**Console:** inspect errors, missing resources, invalid markup warnings, and unexpected external requests.

**Network:** filter failed requests. Check status, URL, content type, and initiator. A missing local image usually indicates a bad path or incomplete deployment.

**Elements and computed styles:** inspect DOM structure and computed values when layout differs from expectation. Identify which CSS rule wins.

**Responsive mode:** test narrow widths and orientation changes. Check long text and zoom.

## Visual comparison
When changing layout or typography, compare before and after at the same viewport and zoom. Review the entire page for unintended changes to spacing, image crop, alignment, overflow, and focus visibility. Screenshots support review but do not replace keyboard or assistive-technology testing.

## Accessibility-oriented checks
Zoom to 200%, test keyboard navigation, inspect alternative text, check reduced-motion behavior, and use at least one screen reader for substantial semantic changes. See [Accessibility](accessibility.md).

## Compatibility
Use standard HTML and CSS. Avoid browser-specific features without a fallback or documented support decision. Do not claim broad compatibility based on a single browser.

## Test report template
```text
Browser and version:
Operating system:
Viewport:
Zoom:
Commit:
Steps:
Expected result:
Actual result:
Console / Network evidence:
Reproduces in another browser:
```

## Exit criteria
A visual change is ready for review when the page loads, local assets resolve, no unintended overflow appears at target widths, keyboard focus remains visible, and no new browser errors are introduced. Accessibility-sensitive changes require the additional checks in the accessibility guide.
