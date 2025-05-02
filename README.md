# SST PingPong

This is a demonstration of using SST in a container to build and run a simulation.

The intention is that it can serve as an example of reusing a container with SST
installed to develop an SST element library.


## Caveats

This is a WIP and there are known issues:

Currently the git submodule sst-pingpong is not cloning in Codespaces.
 - workaround is to manually clone the repo from https://github.com/brandon-neth/sst-pingpong

The docker image is large ~3GB so it takes a while to load.
  - no workaround.

## Usage

1. Load the devcontainer either in VSCode or in a Github Codespace
2. From the terminal, cd into the sst-pingpong directory
3. Run make
4. Run sst pingpong.py -- --corners --verbose


## Usage w/Checkpoint enabled

1. From the sst-pingpong directory do `git checkout add-pingpong-checkpoint`
2. edit Makefile, comment out empty `PARAMS` line and uncomment `-DENABLE_SSTCHECKPOINT` line
3. `make`
4. `sst pingpong.py --checkpoint-period=10s -- --corners`
5. see `checkpoint/` folder created with checkpoints for each 10s of simulated time (note that subsequent runs will create `checkpoint_1/` etc.)


## Restart from a checkpoint

1. Have previously ran simulation with checkpointing enabled as above
2. locate checkpoint file to restart from in `checkpoint/` directory
3. start the simulation from a checkpoint, e.g. `sst --load-checkpoint checkpoint/checkpoint_0_10000000000000/checkpoint_0_10000000000000.sstcpt`
