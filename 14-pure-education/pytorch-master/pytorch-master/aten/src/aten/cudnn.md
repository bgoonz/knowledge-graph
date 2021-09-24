# README

All files living in this directory are written with the assumption that cuDNN is available, which means that these code are not guarded by `#if AT_CUDNN_ENABLED()`. Therefore, whenever you need to use definitions from here, please guard the `#include<ATen/cudnn/*.h>` and definition usages with `#if AT_CUDNN_ENABLED()` macro, e.g. [native/cudnn/BatchNorm.cpp](https://github.com/bgoonz/Knowledge-Bank/tree/d157cab4a536be397d8f7d36c79f7d69d282500a/14-Pure-Education/pytorch-master/pytorch-master/aten/src/ATen/cudnn/native/cudnn/BatchNorm.cpp).

