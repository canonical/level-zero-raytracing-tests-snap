# Level Zero Unit Tests Snap

This snap provides a way to build and run Intel's Level Zero unit tests
from the Level Zero repository tag `v1.16.1`.

## Build

```bash
snapcraft pack
```

## Install

```bash
snap install --dangerous level-zero-tests_1.16.1_<your_arch>.snap
```

## Run

### List available tests

```bash
level-zero-tests.list-tests
```

### Run a single test binary

```bash
level-zero-tests.test <binname> [args...]
```

Example:

```bash
level-zero-tests.test test_sysman_events
```
