Packaging
=========

This file contains quick reminders and notes on how to package Raider.

We consider here the packaging flow of Raider version `1.0.0` for Linux.

1. **How to bump Raider version before a release:**
    1. Bump version in `Cargo.toml` to `1.0.0`
    2. Execute `cargo update` to bump `Cargo.lock`

2. **How to update Raider on Crates:**
    1. Publish package on Crates: `cargo publish --no-verify`

3. **How to build Raider, package it and release it on GitHub and Docker Hub (multiple architectures):**
    1. Tag the latest Git commit corresponding to the release with tag `v1.0.0`, and push the tag
    2. Wait for all release jobs to complete on the [actions](https://github.com/valeriansaliou/raider/actions) page on GitHub
    3. Download all release archives, and sign them locally using: `./scripts/sign_binaries.sh --version=1.0.0`
    4. Publish a changelog and upload all the built archives, as well as their signatures on the [releases](https://github.com/valeriansaliou/raider/releases) page on GitHub
