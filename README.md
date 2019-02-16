# `ned-build`

This repository includes the `ned-aur`, `ned-deb`, and `ned-rpm` repository as submodules and provides the Docker container builds and scripts for building and testing the AUR repository, and building the Debian, RPM, and unpackaged deployment artifacts for a `ned` release.

1. Install `docker`, add yourself to the `docker` group.
2. Run `./buildall`.
3. Deploy the artifacts built into the `artifacts` directory.
