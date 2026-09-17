# Level Zero Raytracing Tests Snap

This snap provides a way to build and run Intel's Level Zero raytracing tests
from the [level-zero-raytracing-support](https://github.com/intel/level-zero-raytracing-support)
repository. It targets the SYCL nightly toolkit from `2026-06-12`.

> **Hardware requirement:** Intel GPU with ray tracing support (Xe HPG or later).

## Build

```bash
snapcraft pack
```

This produces `level-zero-raytracing-tests_2026-06-12_amd64.snap`.

## Install

```bash
snap install --dangerous level-zero-raytracing-tests_2026-06-12_amd64.snap
```

## Run

### List available tests

```bash
level-zero-raytracing-tests.list-tests
```

### Check for a capable GPU

```bash
level-zero-raytracing-tests.check-gpu
```

Checks that an Intel GPU (PCI vendor `0x8086`) with a DRM render node is
present, which is the hardware precondition for the tests. It prints the
detected device(s) and exits `0` if an Intel GPU is found, non-zero otherwise,
making it suitable as a Checkbox resource/precondition.

This is a presence check only — confirming actual Level Zero raytracing
support requires running a test binary (see below).

### Run a single test binary

```bash
level-zero-raytracing-tests.test [--no-confinement] <binname> [args...]
```

Example:

```bash
level-zero-raytracing-tests.test embree_raytracing_test
```

Pass `--no-confinement` to skip the snap-bundled Level Zero drivers and use
the host Level Zero raytracing drivers exclusively. This is intended for use
with the Checkbox framework when snap sandboxing is removed.
