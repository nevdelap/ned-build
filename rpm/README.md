# `ned-rpm` Build

1. Install `docker`, add yourself to the `docker` group.
2. Run `./build` to build the docker images.
3. Run `./run` to run the build container to build the deb.
4. Run `./test` to run the vanilla test container to test installing the rpm with rpm -i.

The `rpm` package is copied to the `artifacts` directory.
