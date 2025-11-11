# 598APE-HW3

This repository contains code for homework 3 of 598APE.

The main branch contains all optimizations. To run each of the optimizations, checkout to its branch!
### Optimization Branches

| Branch | Description |
|:-------|:-------------|
| **opt-1** | Localized energy calculation to reduce redundant lattice traversals and minimize repeated function calls. |
| **opt-2** | Applied compiler-level optimizations (`-Ofast`, `-march=native`) to leverage CPU-specific vectorization and fast math. Inlined the Metropolis–Hastings function to reduce function call overhead. |
| **main** | Cached probability threshold in metropolis hastings function. |

### Test Cases

| Input |
|:--------------------------------------------------------------|
| `./main.exe 100 2.269 100000` |
| `./main.exe 1024 2.269 100000` |
| `./main.exe 1024 2.269 100000000` |
| `./main.exe 1024 2.269 10000000000` |


This assignment is relatively simple in comparison to HW1 and HW2 to ensure you have enough time to work on the course project.

In particular, this repository implements a 2D Ising model Monte Carlo simulator (with Metropolis–Hastings algorithm) on an L×L lattice with periodic boundary conditions.

To compile the program run:
```bash
make -j
```

To clean existing build artifacts run:
```bash
make clean
```

This program assumes the following are installed on your machine:
* A working C compiler (gcc is assumed in the Makefile)
* make
* ImageMagick `convert` for PNG output

Usage (after compiling):
```bash
./main.exe <L> <temperature> <steps>
```

In particular, consider speeding up simple run like the following (which runs ~5 seconds on my local laptop under the default setup):
```bash
./main.exe 100 2.269 100000
```

Exact bitwise reproducibility is not required; sanity checks on energy/magnetization bounds must pass. In addition, at the critical temperature (T ≈ 2.269) the energy per spin should approach -1.414 in equilibrium.
