# `ned-deb` Build

1. Install `docker`, add yourself to the `docker` group.
2. Update the version number for the release in `ned-deb/bbuild`.
3. Update the change log in `ned-deb/ned-debian/debian/changelog`.
4. Run `./build` to build the docker images.
5. Run `./run` to run the build container to build the deb.
6. Run `./test` to run the vanilla test container to test installing the deb with dpkg -i.
7. Commit and push the version and changelog updates in `ned-deb`.

The `deb` package is copied to the `artifacts` directory.
