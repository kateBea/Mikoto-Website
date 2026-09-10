# Rendering

Mikoto's renderer is built around Vulkan and a scene-oriented frame pipeline. Its current feature set is aimed at modern real-time rendering while keeping the implementation available for study.

## Render path

1. The world supplies visible entities and their renderable data.
2. Resources resolve models, materials, images, and shader programs.
3. The renderer builds work for the active render passes.
4. Clustered Forward+ handles light assignment and shading.
5. HDR output is presented through the Vulkan swapchain.

## Current capabilities

- Vulkan device and swapchain management
- Clustered Forward+ lighting and light culling
- HDR images and equirectangular environment conversion
- Procedural infinite grid for editor/world space
- MSDF-based text rendering
- GLTF loading through tinygltf, with Assimp for additional formats
- Runtime shader compilation with Slang

## A useful way to debug a frame

!!! tip "Walk from the outside in"
    Start with the visible symptom, then check the render pass, descriptor/resource bindings, image layout transitions, and finally the underlying asset. This keeps a shader issue from turning into an unfocused search through the whole engine.

```cpp
// Pseudocode for the shape of a frame
begin_frame();
update_world();
collect_visible_renderables();
record_shadow_and_scene_passes();
record_post_process();
present();
```

The exact API is evolving with the `develop` branch, so treat this as a conceptual map rather than a stable public interface.

## GPU-assisted validation

When validation reports a GPU-assisted error, preserve the full message and the draw/dispatch context that produced it. Small changes to resource access or shader bindings can move the visible failure away from its cause.

See [Profiling](../workflows/profiling.md) and [Shaders with Slang](../workflows/slang.md) for two complementary ways to inspect the frame.
