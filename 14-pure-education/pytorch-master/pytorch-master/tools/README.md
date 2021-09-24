# README

This folder contains a number of scripts which are used as part of the PyTorch build process. This directory also doubles as a Python module hierarchy \(thus the `__init__.py`\).

## Overview

Modern infrastructure:

* [autograd](autograd.md) - Code generation for autograd.  This

  includes definitions of all our derivatives.

* [jit](https://github.com/bgoonz/Knowledge-Bank/tree/d157cab4a536be397d8f7d36c79f7d69d282500a/14-Pure-Education/pytorch-master/pytorch-master/tools/jit/README.md) - Code generation for JIT
* [shared](https://github.com/bgoonz/Knowledge-Bank/tree/d157cab4a536be397d8f7d36c79f7d69d282500a/14-Pure-Education/pytorch-master/pytorch-master/tools/shared/README.md) - Generic infrastructure that scripts in

  tools may find useful.

  * [module\_loader.py](https://github.com/bgoonz/Knowledge-Bank/tree/d157cab4a536be397d8f7d36c79f7d69d282500a/14-Pure-Education/pytorch-master/pytorch-master/tools/shared/module_loader.py) - Makes it easier

    to import arbitrary Python files in a script, without having to add

    them to the PYTHONPATH first.

Legacy infrastructure \(we should kill this\):

* [cwrap](https://github.com/bgoonz/Knowledge-Bank/tree/d157cab4a536be397d8f7d36c79f7d69d282500a/14-Pure-Education/pytorch-master/pytorch-master/tools/cwrap/README.md) - Implementation of legacy code generation for THNN/THCUNN.

  This is used by nnwrap.

Build system pieces:

* [setup\_helpers](https://github.com/bgoonz/Knowledge-Bank/tree/d157cab4a536be397d8f7d36c79f7d69d282500a/14-Pure-Education/pytorch-master/pytorch-master/tools/setup_helpers/README.md) - Helper code for searching for

  third-party dependencies on the user system.

* [build\_pytorch\_libs.py](https://github.com/bgoonz/Knowledge-Bank/tree/d157cab4a536be397d8f7d36c79f7d69d282500a/14-Pure-Education/pytorch-master/pytorch-master/tools/build_pytorch_libs.py) - cross-platform script that

  builds all of the constituent libraries of PyTorch,

  but not the PyTorch Python extension itself.

* [build\_libtorch.py](https://github.com/bgoonz/Knowledge-Bank/tree/d157cab4a536be397d8f7d36c79f7d69d282500a/14-Pure-Education/pytorch-master/pytorch-master/tools/build_libtorch.py) - Script for building

  libtorch, a standalone C++ library without Python support.  This

  build script is tested in CI.

* [fast\_nvcc](https://github.com/bgoonz/Knowledge-Bank/tree/d157cab4a536be397d8f7d36c79f7d69d282500a/14-Pure-Education/pytorch-master/pytorch-master/tools/fast_nvcc/README.md) - Mostly-transparent wrapper over nvcc that

  parallelizes compilation when used to build CUDA files for multiple

  architectures at once.

  * [fast\_nvcc.py](https://github.com/bgoonz/Knowledge-Bank/tree/d157cab4a536be397d8f7d36c79f7d69d282500a/14-Pure-Education/pytorch-master/pytorch-master/tools/fast_nvcc/fast_nvcc.py) - Python script, entrypoint to the

    fast nvcc wrapper.

Developer tools which you might find useful:

* [clang\_tidy.py](https://github.com/bgoonz/Knowledge-Bank/tree/d157cab4a536be397d8f7d36c79f7d69d282500a/14-Pure-Education/pytorch-master/pytorch-master/tools/clang_tidy.py) - Script for running clang-tidy

  on lines of your script which you changed.

* [git\_add\_generated\_dirs.sh](https://github.com/bgoonz/Knowledge-Bank/tree/d157cab4a536be397d8f7d36c79f7d69d282500a/14-Pure-Education/pytorch-master/pytorch-master/tools/git_add_generated_dirs.sh) and

  [git\_reset\_generated\_dirs.sh](https://github.com/bgoonz/Knowledge-Bank/tree/d157cab4a536be397d8f7d36c79f7d69d282500a/14-Pure-Education/pytorch-master/pytorch-master/tools/git_reset_generated_dirs.sh) -

  Use this to force add generated files to your Git index, so that you

  can conveniently run diffs on them when working on code-generation.

  \(See also [generated\_dirs.txt](https://github.com/bgoonz/Knowledge-Bank/tree/d157cab4a536be397d8f7d36c79f7d69d282500a/14-Pure-Education/pytorch-master/pytorch-master/tools/generated_dirs.txt) which

  specifies the list of directories with generated files.\)

* [mypy\_wrapper.py](https://github.com/bgoonz/Knowledge-Bank/tree/d157cab4a536be397d8f7d36c79f7d69d282500a/14-Pure-Education/pytorch-master/pytorch-master/tools/mypy_wrapper.py) - Run `mypy` on a single file using the

  appropriate subset of our `mypy*.ini` configs.

* [test\_history.py](https://github.com/bgoonz/Knowledge-Bank/tree/d157cab4a536be397d8f7d36c79f7d69d282500a/14-Pure-Education/pytorch-master/pytorch-master/tools/test_history.py) - Query S3 to display history of a single

  test across multiple jobs over time.

Important if you want to run on AMD GPU:

* [amd\_build](https://github.com/bgoonz/Knowledge-Bank/tree/d157cab4a536be397d8f7d36c79f7d69d282500a/14-Pure-Education/pytorch-master/pytorch-master/tools/amd_build/README.md) - HIPify scripts, for transpiling CUDA

  into AMD HIP.  Right now, PyTorch and Caffe2 share logic for how to

  do this transpilation, but have separate entry-points for transpiling

  either PyTorch or Caffe2 code.

  * [build\_amd.py](https://github.com/bgoonz/Knowledge-Bank/tree/d157cab4a536be397d8f7d36c79f7d69d282500a/14-Pure-Education/pytorch-master/pytorch-master/tools/amd_build/build_amd.py) - Top-level entry

    point for HIPifying our codebase.

Tools which are only situationally useful:

* [docker](https://github.com/bgoonz/Knowledge-Bank/tree/d157cab4a536be397d8f7d36c79f7d69d282500a/14-Pure-Education/pytorch-master/pytorch-master/tools/docker/README.md) - Dockerfile for running \(but not developing\)

  PyTorch, using the official conda binary distribution.  Context:

  [https://github.com/pytorch/pytorch/issues/1619](https://github.com/pytorch/pytorch/issues/1619)

* [download\_mnist.py](https://github.com/bgoonz/Knowledge-Bank/tree/d157cab4a536be397d8f7d36c79f7d69d282500a/14-Pure-Education/pytorch-master/pytorch-master/tools/download_mnist.py) - Download the MNIST

  dataset; this is necessary if you want to run the C++ API tests.

* [run-clang-tidy-in-ci.sh](https://github.com/bgoonz/Knowledge-Bank/tree/d157cab4a536be397d8f7d36c79f7d69d282500a/14-Pure-Education/pytorch-master/pytorch-master/tools/run-clang-tidy-in-ci.sh) - Responsible

  for checking that C++ code is clang-tidy clean in CI on Travis

