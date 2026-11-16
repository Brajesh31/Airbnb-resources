# Accessibility Guide

## 1. Accessibility objective

The page should be understandable and operable by people using different devices, input methods, and assistive technologies. Accessibility is a quality requirement, not a final visual adjustment.

This guide provides development and review practices. It does not claim that the current page has been audited or certified against a formal accessibility standard.

## 2. Current limitations

The interface is a static visual demonstration. Search-like controls, filters, category items, profile controls, menus, and favorite artwork may look interactive but do not implement the corresponding behavior. A control that appears actionable but does nothing creates a confusing experience for mouse, keyboard, and screen-reader users.

Do not claim complete accessibility while these limitations remain. Before turning a visual sample into a real control, define its action, accessible name, keyboard behavior, focus behavior, state announcement, and error handling.

## 3. Semantic structure

Use HTML elements according to their purpose:
- `header` for introductory or site-wide header content;
- `nav` for navigation links;
- `main` for the page's primary content;
- headings to communicate hierarchy;
- lists for collections where list semantics are meaningful;
- `button` for actions;
- `a` for navigation to another location.

Avoid using generic containers for everything. Semantic elements help assistive technology users understand page regions and content relationships.

## 4. Keyboard operation

Every genuine interactive element must be reachable and operable using a keyboard. Test:
- Tab to move forward;
- Shift+Tab to move backward;
- Enter to activate links and buttons;
- Space to activate buttons;
- Escape to close dismissible overlays, if any are added.

Do not remove the browser's focus outline without providing a visible replacement. The stylesheet includes focus-visible styling, but it must be checked against actual backgrounds and surrounding elements.

A keyboard user should not become trapped in a control or be forced to use a mouse to continue.

## 5. Focus and interaction states

For every future interactive component, define:
- default state;
- hover state;
- keyboard focus state;
- pressed or selected state;
- disabled state, where appropriate;
- error and empty states, where relevant.

Focus must be visually distinguishable and must not be obscured by sticky content. Do not use hover as the only way to reveal important information.

## 6. Images and alternative text

Alternative text should communicate the purpose of an image in its context:
- Informative image: describe the relevant information.
- Decorative image: use empty alternative text (`alt=""`) so it is ignored by screen readers.
- Functional image: describe the action or destination, not merely the visual appearance.

Do not repeat nearby captions verbatim unless the image conveys additional information. Avoid keyword stuffing and speculative descriptions.

## 7. Color and contrast

Text and important interface elements should remain distinguishable from their backgrounds. Check contrast using a reliable contrast analyzer rather than judging by appearance alone. Do not rely on color alone to communicate selection, errors, availability, or status.

The current stylesheet includes visual styling that should be reviewed against actual rendered combinations. A focus outline existing in CSS does not automatically prove adequate contrast.

## 8. Reflow, zoom, and responsive behavior

Test at narrow widths and increased zoom. Content should not require two-dimensional scrolling for ordinary reading, except for content that inherently requires it. Check:
- 320 CSS pixel width;
- common phone widths such as 360 and 390 pixels;
- tablet and desktop widths;
- 200% browser zoom;
- long labels and unusually long content;
- text enlargement and browser font overrides.

Do not hide essential content simply to make a mobile screenshot look cleaner.

## 9. Motion

The stylesheet includes a reduced-motion media query. Avoid adding unnecessary parallax, autoplay animation, flashing, or large motion effects. When motion is not essential, provide a reduced-motion alternative.

## 10. Screen-reader review

At minimum, inspect the page with one desktop screen reader when making substantial semantic or interaction changes. Confirm:
- page title is meaningful;
- landmarks are discoverable;
- heading levels make sense;
- links and buttons have clear names;
- informative images have useful alternative text;
- decorative icons are not announced;
- content order matches visual reading order.

Automated tools can detect some issues, but they cannot determine whether labels and descriptions make sense in context.

## 11. Practical review checklist

- [ ] HTML uses a meaningful language and title.
- [ ] Page regions and headings communicate structure.
- [ ] All real controls have accessible names.
- [ ] Keyboard focus is visible and not obscured.
- [ ] All actions work without a pointer.
- [ ] Images have appropriate alternative text.
- [ ] Contrast is checked for text and controls.
- [ ] Content reflows at narrow widths and 200% zoom.
- [ ] Motion respects reduced-motion settings.
- [ ] No information is conveyed by color alone.
- [ ] Visual-only controls are not misrepresented as functional.

## 12. Further work

A future accessibility audit should record the browser, assistive technology, viewport, test date, issue severity, reproduction steps, and remediation status. Do not label the project WCAG conformant without a documented assessment of the applicable success criteria.
