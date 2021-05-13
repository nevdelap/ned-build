# `ned-rpm` Build

1. Install `docker`, add yourself to the `docker` group.
2. Update the version number for the release is `ned-rpm/rpmbuild/SPECS/ned.spec`.
3. Run `./build` to build the docker images.
4. Run `./run` to run the build container to build the deb.
5. Run `./test` to run the vanilla test container to test installing the rpm with rpm -i.
6. Commit and push the version update in `ned-rpm`.

The `rpm` package is copied to the `artifacts` directory.
