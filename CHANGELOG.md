# Changelog

All notable changes to the DevMesh extension are documented in this file.

## [0.1.16] - 2026-08-18

### Added

- Multi-day assessments. Long-running work now shows the time left in hours and days rather than a session timer, and the deadline shown is always the one the assessment actually runs on.
- Pick up where you left off. Closing VS Code, restarting it, or losing your connection no longer costs you your session: reopening restores the workspace and the work you had done.
- A link straight back to the DevMesh site after you submit, so finishing in the editor lands you where the next step happens.
- A confirmation before submitting when part of your work could not be captured, so nothing is sent silently incomplete.

### Changed

- The screen you see after submitting now tells you exactly what happens next, and only promises a report when one is actually coming.
- If your assessment ends while you are still working, the editor now says so instead of leaving you typing into a finished session.
- Pausing has been removed. Assessment time runs continuously, which is what the timer and the deadline always reflected.

### Fixed

- AI file edits that get cut off part-way are now refused and rolled back instead of being written to disk. Previously a truncated edit could be saved and reported as successful, which meant later edits built on a damaged file.
- A dropped connection mid-assessment no longer signs you out; your session is preserved and reconnects on its own.

## [0.1.15] - 2026-07-14

Release packaging fix. No user-facing changes.

## [0.1.14] - 2026-07-14

### Added

- A complete DevMesh look and feel. The panel now has its own dark identity, brand typography, and a responsive AI orb at its centre, instead of inheriting whatever theme the editor happened to be using.
- Clear notice when DevMesh is undergoing maintenance, so it is obvious the platform is unavailable rather than the extension being broken.

### Changed

- DevMesh branding throughout, replacing the last of the upstream artwork.
- Onboarding, submission and scoring screens are centred and width-constrained so they read comfortably at any panel width.

### Fixed

- The extension now tells you when your version is too old to continue and walks you through updating, instead of failing partway through an assessment.

## [0.1.13] - 2026-05-28

Release and packaging maintenance. No user-facing changes.

## [0.1.12] - 2026-05-28

Release and packaging maintenance. No user-facing changes.

## [0.1.11] - 2026-05-28

Release and packaging maintenance. No user-facing changes.

## [0.1.10] - 2026-05-28

Release and packaging maintenance. No user-facing changes.

## [0.1.9] - 2026-05-28

### Added

- Published to the Visual Studio Marketplace, so DevMesh can be installed and updated the usual way.

## [0.1.8] - 2026-05-22

Release packaging. No user-facing changes.

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
