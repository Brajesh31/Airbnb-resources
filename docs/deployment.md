# Deployment Guide

## 1. Deployment model

The current project is a static website. Deployment consists of publishing the repository's HTML, CSS, SVG, JPEG, and WebP files to a static web host. There is no build command and no server-side process to start.

The published document root must contain `index.html` and all referenced assets. Publishing only the HTML file will result in missing styles and images.

## 2. Supported hosting models

The site can be served by GitHub Pages, Netlify, Cloudflare Pages, object storage configured for static website hosting, or a conventional web server. These are examples, not claims that the repository is already deployed to each provider.

Provider configuration changes over time. Follow the chosen host's current documentation for account setup, domain verification, TLS, and deployment permissions.

## 3. Deployment prerequisites

- A clean and reviewed `main` branch.
- The correct repository root as the publish directory.
- `index.html` at the published root.
- All relative media and stylesheet references present.
- No private credentials or local-only files.
- Asset reuse rights reviewed.
- README and documentation aligned with the release.
- CI checks passing.

## 4. Manual static deployment

A generic deployment procedure is:

1. Clone or download the intended commit.
2. Confirm `index.html` is in the directory to publish.
3. Upload the complete static site, preserving relative paths.
4. Configure the host's document root to that directory.
5. Enable HTTPS.
6. Open the deployed URL.
7. Inspect the browser Network panel for missing files.
8. Test a narrow and wide viewport.
9. Verify that the deployed content matches the intended commit.

Do not upload `.git`, editor metadata, local logs, or credentials.

## 5. GitHub Pages considerations

For GitHub Pages, configure the publishing source in repository settings according to the current Pages workflow. If publishing from a branch, select the correct branch and folder. If using a GitHub Actions deployment, grant only the permissions required by that workflow.

Because this repository uses relative paths from its root, verify asset paths when deploying under a project subpath. A path that works at a domain root may fail if it was written as an absolute root path.

## 6. Custom domains and DNS

A custom domain requires DNS configuration at the domain provider and matching configuration at the hosting provider. Do not guess DNS records. Use the exact records supplied by the provider and verify ownership before changing production DNS.

After configuration:
- verify HTTPS certificate issuance;
- confirm both preferred and alternate hostnames behave as intended;
- decide whether HTTP redirects to HTTPS;
- check that canonical metadata reflects the actual public URL, if added.

## 7. Security and transport

Use HTTPS for public hosting. Where supported, configure suitable response headers, including a carefully tested Content Security Policy, frame restrictions, content-type protections, and referrer policy. Do not copy a strict CSP blindly: the policy must match the actual assets and resource requirements.

A static site has a smaller server-side attack surface than an application with authentication and data processing, but it can still be affected by compromised hosting credentials, malicious dependencies, untrusted content, or unsafe third-party scripts.

## 8. Cache behavior

Static hosts and browsers may cache files. If an update appears not to deploy:
- confirm the deployment completed;
- inspect the deployed commit or artifact;
- hard-refresh the browser;
- inspect response headers;
- verify that the host is publishing the expected branch and directory.

Use content-hashed filenames if a future build process introduces fingerprinted assets. Do not add cache-busting query strings indiscriminately.

## 9. Rollback

A static release can generally be rolled back by redeploying a previously known-good commit. Record the deployed commit identifier and retain the previous successful deployment where the provider supports it.

After rollback, verify the public site and record why the release was reverted.

## 10. Post-deployment checklist

- [ ] Root URL returns the expected page.
- [ ] Stylesheet loads successfully.
- [ ] All local SVG, JPEG, and WebP assets load.
- [ ] No unexpected 404 or 500 responses.
- [ ] HTTPS works.
- [ ] Mobile and desktop layouts render correctly.
- [ ] Keyboard focus remains visible.
- [ ] No debug or local-only content is exposed.
- [ ] README and release notes describe the deployed state.
- [ ] The deployed commit is recorded.

## 11. What this workflow does not do

The repository's CI workflow validates static files and local references. It does not publish the website, run browser automation, provision a domain, configure DNS, or verify a live deployment. Do not describe CI success as a successful production deployment.
