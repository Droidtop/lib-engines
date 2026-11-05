# Changelog

All notable changes to lib-engines. Versions follow [Semantic Versioning](https://semver.org/)
(in 0.x, only a new minor version may break the interface; CI's `semver` job enforces it).

## [Unreleased]

### Added
- CI's `semver` job: `cargo-semver-checks` against the last release, so a breaking change fails unless its version and
  this CHANGELOG say so (Droidtop/tracker#867).

## [0.1.0]

### Added
- `engines-detect`: the database's rules and builtin probes, with the database at the commit `crates/detect/data/UPSTREAM` names. Moved from droidtop-agent `0ec4110` `crates/scan/src/engines.rs and crates/scan/data/engines-database.json` unchanged but for its package name (Droidtop/tracker#867 step 1).
