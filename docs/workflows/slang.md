# Shaders with Slang

Mikoto uses the [Slang](https://github.com/shader-slang/slang) shading language for runtime shader compilation. Reflection is still performed with SPIRV-Reflect.

## Bundled setup

The repository ships with precompiled Slang binaries, so a normal checkout does not need a separate Slang installation. Mikoto discovers the bundled directory during its normal build/runtime setup.

If you replace the binaries, keep the existing Slang directory structure intact.

## A productive shader loop

1. Make the smallest shader change possible.
2. Rebuild or trigger the runtime compilation path.
3. Check validation output before judging the visual result.
4. Inspect reflection and resource bindings if the shader compiles but renders incorrectly.
5. Compare a known-good material or pass.

!!! note "Version context"
    The repository README currently points to Slang release `v2026.10` as the version used by Mikoto. Treat the repository's bundled binaries and build files as the source of truth if that changes.
