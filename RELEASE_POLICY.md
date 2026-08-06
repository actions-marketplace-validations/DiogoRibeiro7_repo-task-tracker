# Release Policy

## Scope

This project publishes release tags as `v*` (for example `v1.1.0`).

## Requirements

- Release tags must be **annotated**.
- Release tags must be **signed** (PGP or SSH signature block in tag object).
- GitHub releases must be created from an existing signed tag.

## Enforcement

- CI workflow `Tag Signature Policy` validates every pushed `v*` tag.
- Manual release workflow validates tag signature before publishing release notes.

## Recommended process

1. Prepare release changes on `develop`.
2. Open and merge a PR from `develop` into `main`.
3. Check out the updated `main` branch locally.
4. Create a signed annotated tag on `main`.
5. Push the tag to origin.
6. Run the `Release` workflow and provide the existing tag name.
7. After Zenodo is connected to this GitHub repository, archive the published
   GitHub Release on Zenodo so it mints a software DOI using `.zenodo.json`.
