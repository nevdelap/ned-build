# `ned-build`

This repository includes the `ned-aur`, `ned-deb`, and `ned-rpm` repositories as submodules and provides the Docker container builds and scripts for building and testing the AUR repository, and building the Debian, RPM, and unpackaged deployment artifacts for a `ned` release.

1. Clone this repo with `--recursive`. (Or update the sub-repos.)
2. Install `docker`, add yourself to the `docker` group.
3. Create a release, or at least a pre-release, tagged `release.#.#.#`.
4. Update the version numbers according the the README.md in the sub-repos. (TODO: make this an update in one place only.)
5. Run `./buildall nuke` to nuke everything back to square one and build from scratch.
6. Deploy the artifacts that were built into the `artifacts` directory.
