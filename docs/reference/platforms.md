# Platforms & requirements

Mikoto is developed and tested on Windows and Ubuntu 24.04 LTS.

| Platform | Architecture | Compiler | Generators | Graphics API |
| --- | --- | --- | --- | --- |
| Windows 10+ | x86_64 | MSVC | Visual Studio, Ninja | Vulkan, Direct3D 12 |
| Linux | x86_64 | GCC 13.3.0+ | Ninja, Make | Vulkan |

## Baseline requirements

- CMake 3.22+
- Vulkan SDK and validation tooling
- C++20-compatible compiler
- Visual Studio 2022+ on Windows
- Lua 5.1+ on Linux

Other distributions, architectures, compilers, and generators may work, but are not formally tested. See [Install & build](../getting-started/build.md) for setup commands.
