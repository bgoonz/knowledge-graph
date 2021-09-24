# libopencl-stub

A stub opecl library that dynamically dlopen/dlsyms opencl implementations at runtime based on environment variables. Will be useful when opencl implementations are installed in non-standard paths \(say pocl on android\)

LIBOPENCL\_SO\_PATH -- Path to opencl so that will be searched first

LIBOPENCL\_SO\_PATH\_2 -- Searched second

LIBOPENCL\_SO\_PATH\_3 -- Searched third

LIBOPENCL\_SO\_PATH\_4 -- Searched fourth

Default paths will be searched otherwise

