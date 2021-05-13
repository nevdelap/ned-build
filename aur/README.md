# `ned-aur` Build

1. Install `docker`, add yourself to the `docker` group.
2. Update the version number and checksum for the release in `ned-aur/.SRCINFO` and `ned-aur/pkgver`.
3. Run `./build` to build the docker images.
4. Run `./run` to run the build container to build and test the AUR repository.
6. Run `./test` to run the vanilla test container and test installing using yay.
5. Push the ned-aur repo to the AUR.
7. Commit and push the version and checksum updates in `ned-aur`.

The repository is the primary artifact. It also copies the bin and man file to the `artifacts` directory.
