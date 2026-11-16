# Quality Assurance and Validation

## Quality model
Quality assurance for this static page focuses on file and reference correctness, browser rendering, responsive behavior, accessibility, asset rights, and documentation accuracy. The automated workflow is lightweight and does not prove visual correctness or full accessibility.

## Automated checks
The GitHub Actions workflow at `.github/workflows/ci.yml` checks that required files exist and are not empty, local HTML and CSS references resolve, the HTML includes a title and viewport metadata, Markdown files are non-empty, and local Markdown links resolve.

These checks do not constitute a complete HTML validator, CSS linter, browser test, security audit, or accessibility conformance assessment.

## Manual checks
Before a meaningful change is complete, review phone, tablet, and desktop rendering; image loading and cropping; text wrapping and overflow; keyboard focus; browser Console and Network panels; zoom and reduced-motion behavior; content accuracy; and asset reuse rights.

See [Browser Testing](browser-testing.md) and [Accessibility](accessibility.md).

## Change-based test selection
| Change | Required review |
|---|---|
| HTML content | Semantics, headings, links, alternative text |
| CSS layout | Phone, tablet, desktop, overflow, zoom |
| Image asset | Path, dimensions, crop, alt text, rights |
| Documentation | Local links, commands, implementation accuracy |
| CI workflow | YAML, permissions, run result, failure logs |
| Deployment config | Publish root, HTTPS, asset requests, deployed commit |
| New JavaScript | Behavior, keyboard, errors, security, compatibility |
| New API or data store | Contract, validation, privacy, security, integration tests |

## Failure handling
When CI fails, open the failed job, identify the exact step and error, reproduce locally where practical, fix the underlying problem, preserve meaningful checks, and rerun CI. Do not weaken validation simply to obtain a green result.

A cancelled run caused by concurrency is not equivalent to a failed validation. Check the latest completed run for the relevant commit.

## Quality gates
A change is not ready if it introduces broken local references, unusable narrow layouts, invisible keyboard focus, unlicensed assets, false claims about functionality, secrets, or materially inaccurate documentation.

## Future automation
If the project grows, consider standards-based HTML validation, CSS linting, link checking, and browser smoke tests. Add tools only when they solve a real maintenance problem. Document setup and failure interpretation before making them required.

## Evidence
For substantial changes, record the tested commit, browser, viewport, checks performed, and remaining known issues. "Tested" should refer to a specific check that actually occurred.
