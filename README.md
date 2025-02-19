# AMD AIE Plugin for IREE

This repository contains an early-phase IREE compiler and runtime plugin for
interfacing the AMD AIE accelerator to IREE.

## Developer Setup

These instructions assume that you have an appropriate IREE checkout side by side
with this repository have an IREE build setup in an `iree-build` directory that
is also a sibling. This is not a requirement, but instructions will need to be
changed for different paths.

Preparing repostiory:

```
git submodule update --init
```

## Enabling in IREE

```
cd ../iree-build
cmake -DIREE_CMAKE_PLUGIN_PATHS=../iree-amd-aie .
ninja
```

Note for the time being building the amd-aie backend requires
Headers-only Boost library. On Ubuntu you can do this with

```
sudo apt-get install libboost-dev
```

Lit tests specific to AIE can be run with something like:

```
ctest -R amd-aie
```

## Runtime driver setup

The runtime driver is currently just a stub and is not enabled by default.
Enable with:

```
-DIREE_AMD_AIE_ENABLE_XRT_DRIVER=ON -DIREE_EXTERNAL_HAL_DRIVERS=xrt
```

You will probably also need to add XRT on your PATH so that it can
be found by cmake
e.g
```
export PATH="/opt/xilinx/xrt/share/cmake/XRT:$PATH"
```
