# Changelog

All notable changes to lib-engines. Versions follow [Semantic Versioning](https://semver.org/)
(in 0.x, only a new minor version may break the interface; CI's `semver` job enforces it).

## [Unreleased]

## [0.1.1]

### Added
- CI's `semver` job: `cargo-semver-checks` against the last release, so a breaking change fails unless its version and
  this CHANGELOG say so (Droidtop/tracker#867).

### Changed
- Builds with Rust 1.85 (`rust-version` 1.89 → 1.85): Pythia builds these crates with Ubuntu's rustc-1.85, as
  Launchpad does. 1.89 came from droidtop-agent b5e7094, only for std's `File::lock`, which lib-sync 0.1.5 no
  longer needs. A new `msrv` CI job checks the workspace with 1.85, resolving dependencies to versions 1.85 can
  build, as a consumer's lock would.

## [0.1.0]

### Added
- `engines-detect`: the database's rules and builtin probes, with the database at the commit `crates/detect/data/UPSTREAM` names. Moved from droidtop-agent `0ec4110` `crates/scan/src/engines.rs and crates/scan/data/engines-database.json` unchanged but for its package name (Droidtop/tracker#867 step 1).
