# Install & build

Mikoto uses CMake and targets a C++20-compatible compiler. The verified development platforms are Windows 10+ and Ubuntu 24.04 LTS.

## Prerequisites

=== "Windows"

    - Visual Studio 2022 or newer with a C++ workload
    - Vulkan SDK from [LunarG](https://vulkan.lunarg.com/)
    - CMake 3.22 or newer
    - Git

    Precompiled Lua binaries are included for MSVC builds.

=== "Linux"

    - GCC 13.3.0 or newer
    - Vulkan development packages
    - CMake 3.22 or newer
    - Lua 5.1 or newer
    - Git

    Mikoto is currently tested on Ubuntu 24.04 LTS.

## Clone and configure

There are currently no Git submodules; dependencies are pulled through CMake.

```bash
git clone https://github.com/kateBea/Mikoto.git
cd Mikoto
cmake -S . -B build
```

## Build

```bash
cmake --build build --config Release
```

On Windows, CMake generates Visual Studio solution files by default. Open the generated solution in Visual Studio, or build from the command line as above.

On Linux, you can install the declared system dependencies from the build directory:

```bash
cmake --build build --target InstallDependencies --config Release
cmake --build build --config Release
```

!!! warning "Linux permissions"
    `InstallDependencies` may prompt for `sudo`. Review the package list in `Resources/installs.sh` before running it on a machine you maintain.

## Configure a development build

For day-to-day engine work, configure a separate build directory or use a named preset when one is available in your checkout. Keep generated files out of the source tree's tracked directories.

```bash
cmake -S . -B build-debug -DCMAKE_BUILD_TYPE=Debug
cmake --build build-debug
```

## What to try next

1. Launch the editor target produced by your generator.
2. Open one of the scenes in `Resources/`.
3. Keep Vulkan validation enabled while learning the renderer.
4. Read [First look](first-look.md) for the major editor surfaces.
