# Contributing

Mikoto is an educational project, so a strong contribution makes the implementation easier to understand as well as more capable.

## Before opening a change

- Build the branch on your target platform.
- Read the nearby system before introducing a new abstraction.
- Keep changes scoped to one behavior or subsystem.
- Run with validation enabled for Vulkan-facing changes.
- Update docs when a setup command, option, or workflow changes.

## Suggested workflow

```bash
git checkout develop
git pull --ff-only
cmake -S . -B build-debug -DCMAKE_BUILD_TYPE=Debug
cmake --build build-debug
```

Use a focused branch or worktree for larger experiments. Include the platform, compiler, CMake generator, and validation/profiling options in a bug report so the result is reproducible.

## What makes a useful issue?

Include:

- the commit or branch you tested
- operating system and compiler version
- exact configure/build command
- the smallest scene or asset that reproduces the issue
- full Vulkan validation or shader compiler output
- whether Tracy or GPU-assisted validation was enabled

## Keep the learning visible

Prefer names and boundaries that explain the concept being implemented. A clever shortcut that hides a synchronization rule may be fast today and expensive to teach tomorrow.
