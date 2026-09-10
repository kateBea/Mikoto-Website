# First look

The editor is the fastest way to see Mikoto's systems working together. It sits on top of the engine runtime and exposes scene editing, rendering, asset inspection, and scripting-oriented workflows.

## A useful first session

1. Build the project in `Release` or `Debug`.
2. Open a sample scene from `Resources/`.
3. Use the transform gizmo to select and move an entity.
4. Inspect the world grid and the rendered lighting.
5. Change an asset or script and watch the hot-reload path respond.

## Mental model

```text
Editor application
        |
        +-- scene and entity authoring
        +-- ImGui panels and gizmos
        +-- asset browser / hot reload
        |
Engine runtime
        |
        +-- ECS + scene graph
        +-- asset and resource lifetime
        +-- physics / audio / scripting / networking
        |
Graphics platform
        |
        +-- Vulkan device and queues
        +-- render passes + clustered lighting
        +-- shaders, images, buffers, synchronization
```

## Keep validation close

When something goes wrong, reduce the problem to the smallest scene and run with Vulkan validation enabled. The validation layer message is usually more valuable than the symptom on screen, especially for resource lifetime and synchronization issues.

!!! tip "The source is part of the tutorial"
    Mikoto is intentionally educational. When a system feels opaque, trace the editor call into the runtime and then down to the renderer. The boundaries are designed to be readable.
