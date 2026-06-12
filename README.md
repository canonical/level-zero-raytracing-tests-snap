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

### Run a single test binary

```bash
level-zero-raytracing-tests.test <binname> [args...]
```

Example:

```bash
level-zero-raytracing-tests.test embree_raytracing_test
```
