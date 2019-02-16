# `ned-aur` Build

1. Install `docker`, add yourself to the `docker` group.
2. Run `./build` to build the docker images.
3. Run `./run` to run the build container to build and test the AUR repository.
4. Push the ned-aur repo to the AUR.
5. Run `./test` to run the vanilla test container and test installing using yaourt.

The repository is the primary artifact. It also copies the bin and man file to the `artifacts` directory.
