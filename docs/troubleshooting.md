# Troubleshooting Guide

This guide covers common problems when previewing, editing, and publishing the static page. Start by reproducing the issue with a local HTTP server and checking the browser's Console and Network panels.

## 1. Page does not load

**Possible causes**
- The local server is not running.
- The browser is using the wrong port.
- The server was started from a different directory.
- The requested path is incorrect.

**Checks**
1. Confirm the terminal still shows the server running.
2. Confirm the URL uses the correct port.
3. Run `pwd` or `cd` to verify the repository root.
4. Confirm `index.html` exists in that directory.

Start again from the repository root:

```bash
python -m http.server 8000
```

## 2. Images or icons do not load

**Possible causes**
- Incorrect filename spelling or capitalization.
- The asset is not present in the deployed directory.
- The reference path is incorrect.
- The file extension does not match the actual file.
- The server is publishing the wrong directory.

**Resolution**
- Compare the exact HTML path with the tracked filename.
- Remember that many production hosts use case-sensitive paths.
- Open the asset URL directly in the browser.
- Inspect the failed request in the Network panel.
- Confirm the full repository was published, not just `index.html`.

## 3. CSS changes are not visible

1. Hard-refresh the page.
2. Inspect the stylesheet request in Network.
3. Confirm the link points to `airbnbstyle.css`.
4. Check for a 404 or MIME-type error.
5. Inspect the affected element's computed styles.
6. Search for later selectors that override the declaration.
7. Confirm you edited the same clone and branch being served.

Avoid fixing every cascade problem by appending another override block. Update the original rule where practical.

## 4. Layout overflows on mobile

Inspect:
- fixed widths;
- large horizontal padding;
- flex items with restrictive minimum widths;
- long text and unbroken strings;
- images without a constrained maximum width;
- elements with absolute positioning;
- grid columns that cannot shrink.

Test at 320, 360, and 390 CSS pixels. Use the browser's responsive design mode and inspect the element causing horizontal overflow.

## 5. Controls do nothing

This is expected for current visual-only controls. Search, category, filter, profile, menu, and favorite elements do not have implemented application behavior. Do not report this as a regression unless a specific interaction was previously implemented and then broke.

If implementing behavior is proposed, create a feature request describing the expected action, keyboard behavior, focus management, and state handling.

## 6. Keyboard focus is difficult to see

- Confirm the element is a real interactive control.
- Check whether a CSS selector removes the outline.
- Inspect the computed `:focus-visible` styles.
- Check the outline against the actual background.
- Ensure sticky or overlapping elements do not cover the focused item.

Do not remove the outline merely to match a screenshot.

## 7. CI reports a missing file

The static validation workflow checks required project files and local references. Check the exact path from the workflow log. Confirm filename case and whether the referenced file is committed.

If a reference is intentionally external, ensure the workflow's external-reference handling is appropriate. Do not suppress a real missing local asset by weakening the check.

## 8. CI reports a broken Markdown link

Markdown links are resolved relative to the Markdown file containing the link. For example, a link from `docs/faq.md` to the root README should use `../README.md`, not `README.md`.

Check:
- relative path;
- filename capitalization;
- URL encoding for spaces;
- whether the link points to a real file;
- whether the link is intentionally external.

## 9. Deployment shows an old version

- Confirm the latest deployment completed successfully.
- Verify the host is publishing the intended branch and directory.
- Inspect the deployed commit or artifact.
- Hard-refresh and inspect cache headers.
- Check whether a CDN is serving a cached response.
- Confirm the changed asset was included in the deployment.

## 10. Port 8000 is already in use

Use another port:

```bash
python -m http.server 8080
```

Open `http://localhost:8080`.

## 11. Browser console contains errors

The current static page should not require application API requests. Inspect the failing resource and determine whether it is a local file, browser extension, or external resource. Record the exact error and reproduction steps before changing code.

## 12. Reporting a new issue

A useful bug report includes:
- a short title;
- the exact page or file;
- browser and version;
- operating system;
- viewport dimensions and zoom;
- numbered reproduction steps;
- expected and actual results;
- sanitized screenshots or console/network details;
- whether the issue reproduces in a clean browser session.

Never attach passwords, access tokens, private personal information, or production secrets.
