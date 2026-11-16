# Assets and Content Management

## Purpose
This repository contains local SVG, JPEG, and WebP assets used by the static interface. This guide explains how to identify, replace, reference, and review those files. The presence of an asset in the repository does not prove that it is owned by the maintainer or licensed for redistribution.

## Current organization
Assets are stored at the repository root rather than in a dedicated assets directory. HTML references them through relative paths. Do not move or rename files casually. Update every reference and test the complete page after any reorganization.

## Naming and replacement
Use filenames that describe an asset's purpose. Avoid unexplained abbreviations and temporary ordering names. When replacing an image:
1. identify all references to the old filename;
2. verify the replacement's format and dimensions;
3. optimize it without unacceptable visual loss;
4. update references;
5. check cropping and aspect ratio;
6. test mobile and desktop layouts;
7. verify source and license.

## Format guidance
- **SVG:** scalable logos and simple vector icons. Review SVG source, especially when obtained externally.
- **JPEG:** photographic imagery where lossy compression is acceptable.
- **WebP:** web photography that benefits from efficient compression.

Choose format and dimensions based on rendered use. Avoid serving oversized originals when optimized versions are sufficient.

## Alternative text
Informative photographs need concise descriptions of relevant visible information. Decorative icons should generally use empty alternative text when they add no content. Functional images should describe the action or destination. Do not invent details or repeat nearby captions without a reason.

## Licensing and brand review
For each asset, determine its creator or source, license or permission, whether modification and commercial reuse are allowed, attribution requirements, and whether trademarks are present. Public availability is not permission to reuse. If rights cannot be established, replace the asset with original or suitably licensed media.

This project is an independent educational interface and must not imply endorsement by Airbnb. Brand marks and branded imagery require particular care.

## Content accuracy
Listing-like content is sample material. Do not publish it as real inventory, verified pricing, or current availability. Keep the non-affiliation disclaimer accurate. Do not include real people's personal information or private contact details without a legitimate basis and permission.

## SVG safety
Review externally sourced SVG files. SVG can contain more than static paths. Avoid untrusted embedded scripts, foreign content, or unnecessary external references. Prefer simple sanitized artwork.

## Validation checklist
- [ ] File is tracked and filename capitalization matches references.
- [ ] Asset opens directly in a browser.
- [ ] Network panel shows no failed request.
- [ ] Dimensions and crop are appropriate.
- [ ] Alternative text is meaningful.
- [ ] Source and reuse rights are known.
- [ ] Sample content is not represented as a real listing.

## Future inventory
If the collection grows, maintain an inventory with filename, content type, intended use, dimensions, source or creator, license, attribution requirement, and review date. Do not guess unknown sources; mark unresolved rights as unresolved.
