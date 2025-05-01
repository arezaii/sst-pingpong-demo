# SST PingPong

This is a demonstration of using SST in a container to build and run a simulation.

The intention is that it can serve as an example of reusing a container with SST
installed to develop an SST element library.


## Caveats

This is a WIP and there are known issues:

Currently the git submodule sst-pingpong is not cloning in Codespaces.
 - workaround is to manually clone the repo from https://github.com/brandon-neth/sst-pingpong

The docker image is very large ~10GB so it takes a long time to load.
  - no workaround. TODO: reduce image size

## Usage

1. Load the devcontainer either in VSCode or in a Github Codespace
2. From the terminal, cd into the sst-pingpong directory
3. Run make
4. Run sst pingpong.py -- --corners --verbose
