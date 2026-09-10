# Repository map

The source repository keeps the engine, editor, and shared content in separate top-level areas.

| Directory | Purpose |
| --- | --- |
| `Mikoto/` | Core engine implementation: rendering, ECS, physics, assets, scripting, and runtime systems |
| `Mikoto-Editor/` | Editor application for creating and managing scenes |
| `Resources/` | Models, textures, scripts, screenshots, installation helpers, and other project assets |
| `CMakeLists.txt` | Root build configuration |
| `BUILDING.md` | Full platform-specific build guide |
| `THIRD_PARTY.md` | Dependency inventory and attribution |

## Source of truth

These docs are a guide over the source repository, not a replacement for it. When implementation and prose disagree, trust the current code and build files, then update the docs with the change.
