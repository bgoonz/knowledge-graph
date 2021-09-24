# GLOSSARY

## PyTorch Glossary

* [PyTorch Glossary](glossary.md#pytorch-glossary)
* [Operation and Kernel](glossary.md#operation-and-kernel)
  * [ATen](glossary.md#aten)
  * [Operation](glossary.md#operation)
  * [Native Operation](glossary.md#native-operation)
  * [Custom Operation](glossary.md#custom-operation)
  * [Kernel](glossary.md#kernel)
  * [Compound Operation](glossary.md#compound-operation)
  * [Composite Operation](glossary.md#composite-operation)
  * [Non-Leaf Operation](glossary.md#non-leaf-operation)
  * [Leaf Operation](glossary.md#leaf-operation)
  * [Device Kernel](glossary.md#device-kernel)
  * [Compound Kernel](glossary.md#compound-kernel)
* [JIT Compilation](glossary.md#jit-compilation)
  * [JIT](glossary.md#jit)
  * [TorchScript](glossary.md#torchscript)
  * [Tracing](glossary.md#tracing)
  * [Scripting](glossary.md#scripting)

## Operation and Kernel

### ATen

Short for "A Tensor Library". The foundational tensor and mathematical operation library on which all else is built.

### Operation

A unit of work. For example, the work of matrix multiplication is an operation called aten::matmul.

### Native Operation

An operation that comes natively with PyTorch ATen, for example aten::matmul.

### Custom Operation

An Operation that is defined by users and is usually a Compound Operation. For example, this [tutorial](https://pytorch.org/docs/stable/notes/extending.html) details how to create Custom Operations.

### Kernel

Implementation of a PyTorch operation, specifying what should be done when an operation executes.

### Compound Operation

A Compound Operation is composed of other operations. Its kernel is usually device-agnostic. Normally it doesn't have its own derivative functions defined. Instead, AutoGrad automatically computes its derivative based on operations it uses.

### Composite Operation

Same as Compound Operation.

### Non-Leaf Operation

Same as Compound Operation.

### Leaf Operation

An operation that's considered a basic operation, as opposed to a Compound Operation. Leaf Operation always has dispatch functions defined, usually has a derivative function defined as well.

### Device Kernel

Device-specific kernel of a leaf operation.

### Compound Kernel

Opposed to Device Kernels, Compound kernels are usually device-agnostic and belong to Compound Operations.

## JIT Compilation

### JIT

Just-In-Time Compilation.

### TorchScript

An interface to the TorchScript JIT compiler and interpreter.

### Tracing

Using `torch.jit.trace` on a function to get an executable that can be optimized using just-in-time compilation.

### Scripting

Using `torch.jit.script` on a function to inspect source code and compile it as TorchScript code.

