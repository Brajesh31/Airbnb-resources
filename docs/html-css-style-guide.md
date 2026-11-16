# HTML and CSS Style Guide

## Purpose
This guide establishes consistent practices for editing the static page. Prefer readable browser-native HTML and CSS over introducing tooling without a concrete need.

## HTML document standards
Keep the document's basic metadata complete: HTML5 doctype, correct language, UTF-8 encoding, responsive viewport declaration, meaningful title, and valid local stylesheet references. Use lowercase element names, quoted attributes, consistent indentation, and avoid unnecessary inline styles.

## Semantic markup
Choose elements based on meaning. Use headings for hierarchy, paragraphs for prose, lists for collections, anchors for navigation, buttons for actions, and landmarks for page regions. Do not use a button as a generic styled container or an anchor without a meaningful destination. Avoid clickable generic elements unless full keyboard semantics are implemented.

## IDs and classes
Use IDs only for unique identification, fragment targets, or relationships. Use classes for reusable styling. Before adding a class, search for an existing selector with the same responsibility. Avoid near-duplicate class names that differ only in presentation detail.

## CSS organization
Group rules in a predictable order: document defaults, shared layout and typography, component styles, responsive adjustments, then accessibility preferences such as reduced motion. Keep each component's rules together. Do not repeatedly append override blocks at the end of the stylesheet.

## Specificity and cascade
Prefer simple class selectors. Avoid ID selectors, long descendant chains, and unnecessary `!important`. When a declaration does not take effect, inspect computed styles, identify the winning selector, and update the original rule or remove the conflict. Do not blindly add another override.

## Responsive layout
Design for content reflow rather than one screenshot size. Use flexible widths, grid and flex layouts where appropriate, and media queries when content needs a layout change. Test phone, tablet, desktop, increased zoom, long labels, and translated text. Avoid fixed heights for text containers unless clipping is intentional and accessible.

## Images
Constrain images to their containers and preserve suitable aspect ratios. Use `object-fit` when cropping is intended. Ensure source resolution suits the rendered size. Provide alternative text according to purpose. See [Accessibility](accessibility.md) and [Assets and content](assets-and-content.md).

## Focus and motion
Never hide keyboard focus without a clear replacement. Use a visible focus style with sufficient contrast. Respect `prefers-reduced-motion` for nonessential animation and smooth scrolling.

## Maintainability
Keep selectors understandable, remove obsolete declarations, avoid duplicated rules, and comment only when the reason is not obvious. Avoid broad global selectors that cause unexpected side effects. Do not use CSS hacks without documenting the browser issue they address.

## Review checklist
- [ ] HTML remains structurally valid.
- [ ] No duplicate IDs were introduced.
- [ ] Links and asset paths resolve.
- [ ] CSS rules are not duplicated unnecessarily.
- [ ] Mobile and desktop layouts are checked.
- [ ] Focus and reduced-motion behavior remain intact.
- [ ] Documentation reflects structural changes.
