# Changelog

All notable changes to the DevMesh extension are documented in this file.

## [0.1.7] - 2026-05-22

### Changed

- Added clear instructions to dev docs.

## [0.1.6] - 2026-05-21

### Changed

- Switched the marketplace publish flow to the dedicated `scripts/package-marketplace.mjs` packager so the slim manifest, dev-command filtering, and `--allow-missing-repository` behaviour are applied consistently for every build.
- Moved `posthog-node` from runtime `dependencies` to `devDependencies`. Telemetry is bundled at build time, so it doesn't need to be declared as a runtime dependency in the shipped manifest.

## [0.1.5] - 2026-05-21

### Changed

- Hardened marketplace metadata. The shipped manifest now contains only the fields the marketplace reads — no build scripts, devDependencies, lint-staged config, or workspace settings. Internal/dev-only commands (`devmesh.mcpButtonClicked`, `devmesh.dev.*`, `devmesh.reconstructTaskHistory`, `devmesh.reviewComment.*`) are filtered out of the published `contributes`.
- Added `bugs` and `qna` fields to the shipped manifest.
- README trimmed and focused on what the extension does, what it captures, and the privacy policy.
- Categories reduced to `AI` and `Education`; keyword set trimmed.

### Fixed

- Removed dead `staging` environment configuration. The extension only reaches `https://www.devmesh.live/api` in production; references to internal `*.staging.int.devmesh.live` hostnames no longer appear in the bundle.
- Stripped `posthog-node`'s unused Sentry integration module from the bundle so the `sentry.io/organizations/` URL string is no longer carried as dead code.

## [0.1.3] - 2026-05-21

### Changed

- Removed unused third-party model SDKs from the bundle. All model calls in DevMesh route through the DevMesh backend relay, so direct provider SDKs were dead weight. Bundle size dropped ~25%.

## [0.1.1] - 2026-05-21

### Fixed

- Activity bar container registration so the DevMesh icon appears reliably after install (previously fell back into Explorer in some hosts).
- Removed a redundant stylesheet reference that produced a benign load error in the webview.
- Production builds now point at the hosted DevMesh API by default.

## [0.1.0] - 2026-05-20

### Added

- Initial DevMesh release.
- Coding challenges integration: invite-token workflow and self-serve challenges feed.
- Server-side model relay with per-session budget (no candidate API keys required).
- Session evidence pipeline streamed to the DevMesh backend for evaluation.
- Sandbox submission flow with isolated test execution and evidence-backed reports.
- DevMesh-branded activity bar icon and onboarding walkthrough.
