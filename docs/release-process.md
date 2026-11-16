# Release and Change Management

## Release model
The project is a static site with no build artifact or package release process. A release generally means selecting a reviewed commit and publishing its static files. Keep the process proportionate to the repository's size.

## Before release
- Confirm intended changes are committed.
- Review the complete diff.
- Confirm documentation matches implementation.
- Confirm local asset references resolve.
- Review image and logo permissions.
- Check the non-affiliation disclaimer.
- Confirm CI passes for the intended commit.
- Complete manual browser checks for visual changes.
- Remove temporary files and local-only content.

## Versioning
If tagged releases are adopted, use a consistent versioning approach and explain what a version represents. Do not create a tag merely because a workflow ran. A tag should identify a reviewed repository state.

## Changelog
Update `CHANGELOG.md` for meaningful user-visible, technical, or maintenance changes. Group changes under Added, Changed, Fixed, Removed, and Security. Do not list routine timestamp-only updates as major product changes.

## Release notes
Explain what changed, why it changed, visible effects, validation performed, known limitations, and deployment steps if any. Do not claim a feature is available if the change only adds a placeholder or design proposal.

## Deployment verification
Publish the selected commit using the static hosting process. Verify the root page, stylesheet, images, HTTPS, and responsive layout. Record the deployed commit so rollback is possible.

## Rollback
If a release introduces a serious issue, redeploy the previous known-good commit. Verify the rollback and document the cause. Fix the issue in a new change rather than silently modifying release history.

## Automation
The static validation workflow checks repository integrity. The README timestamp workflow is maintenance automation, not a release workflow. Neither workflow deploys the site.

See [Deployment](deployment.md), [Quality Assurance](quality-assurance.md), and the root [CHANGELOG](../CHANGELOG.md).
