# Vulkan CTS Snap

This snap provides an easy way to install and run the tests found in
[Khronos's Vulkan Conformance Test Suite](https://github.com/KhronosGroup/VK-GL-CTS)

## Build

```
snapcraft pack
```

# Install

```
snap install --classic --dangerous vulkan-cts_1.0_<your_arch>.snap
```

# Run
To list possible tests, run:
```
vulkan-cts.list-tests
```

Then run your chosen test from the previous list like this:
```
vulkan-cts.test basic/test_basic
```
