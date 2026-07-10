# CLAUDE.md

GitHub Action that installs Godot in CI. The repo is `lihop/godot-setup`; the
published action name is `lihop/setup-godot` (same repo, GitHub redirects).
`lib/*.js` is the shipped code — there is no build step.

## Releases

1. CHANGELOG entry under a new `## [vX.Y.Z](compare link) - YYYY-MM-DD`
   heading, and update the Unreleased compare link. Entry format matches
   existing entries exactly — issue link first:
   `- [#NN](https://github.com/lihop/setup-godot/issues/NN): Description.`
2. Bump version in `package.json` (commit: `chore: bump version to vX.Y.Z`).
3. Wait for a green Build run on the exact release commit
   (push triggers `.github/workflows/demo.yml`; there is no manual trigger).
4. Tag `vX.Y.Z`, then re-point the floating major-version tag (`vX`) to the
   same commit — consumers use `@vX` and get nothing until it moves.
5. GitHub Release for the tag; body is the CHANGELOG sections verbatim.
