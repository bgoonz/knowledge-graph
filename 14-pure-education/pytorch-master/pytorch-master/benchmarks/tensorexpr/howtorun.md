# HowToRun

From the root of pytorch repo, run:

```text
python -m benchmarks.tensorexpr --help
```

to show documentation.

An example of an actual command line that one might use as a starting point:

```text
python -m benchmarks.tensorexpr --device gpu --mode fwd --jit_mode trace --cuda_fuser=te
```

