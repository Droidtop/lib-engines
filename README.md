# lib-engines

Which engine a game folder was made with, by droidtop-platforms' engines database. One of the shared library families of Droidtop/tracker#867: the libraries belong to no program;
each program has its own scaffold and pins a tagged release of each library it uses (#867 D2).

| Crate | Where | Holds |
|---|---|---|
| `engines-detect` | [`crates/detect`](crates/detect) | the database's rules and builtin probes, with the database at the commit `crates/detect/data/UPSTREAM` names |

Used by: lib-games' scanner, and through it droidtop-agent and droidtop; droidtop's and Enginehost's Kotlin detectors move onto it in #867 step 5.

Licence: GPL-3.0-only (see `LICENSE`).

## Where the code came from

#867 step 1 moves existing code before changing it ("reuse and contract first, rewrites second"). These
crates are droidtop-agent's, moved as they were:
  - `engines-detect` from droidtop-agent `0ec4110` `crates/scan/src/engines.rs and crates/scan/data/engines-database.json`

Only the package names changed. Code still imports each crate by its old name (`droidtop_agent_*`), so
nothing that uses it had to be edited; renaming the imports is a later, mechanical change.

## Build and test

```bash
cargo fmt --all -- --check
cargo clippy --workspace --all-targets -- -D warnings
cargo test --workspace
```

CI (`.github/workflows/ci.yml`) runs those on Linux, Windows and macOS. It then builds and tests every
program that uses this library against the commit (#867 D2). Work lands on `main` from `ci/*` branches
once CI is green.

## Versions

A release is a tag `vX.Y.Z`. Programs, and the other libraries, depend on a tag:

```toml
droidtop-agent-core = { package = "sync-core", git = "https://github.com/Droidtop/lib-sync", tag = "v0.1.0" }
```
