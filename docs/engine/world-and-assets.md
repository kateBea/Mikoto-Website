# World & assets

Mikoto uses an entity-component model for scene and game-object management, powered by [EnTT](https://github.com/skypjack/entt). The goal is to keep world state composable while letting systems query the data they need.

## World systems

- **Entities and components** describe objects without forcing every object into one inheritance tree.
- **Scene graph data** connects transforms and spatial relationships.
- **Resource pools** centralize ownership and reuse for GPU-facing assets.
- **Automatic cleanup** reduces lifetime bookkeeping across the renderer and editor.

## Asset types

| Asset | Current path |
| --- | --- |
| Models | GLTF through tinygltf; additional formats through Assimp |
| Images | stb_image, including HDR input |
| Environments | Equirectangular images converted to cube maps |
| Materials | GPU-facing material data assembled by the renderer |
| Shaders | Slang runtime compilation with SPIR-V reflection |
| Scripts | Lua through sol2 |

## Hot reload

The editor can reload supported assets and scripts without restarting. When developing an importer or resource type, test both the first-load path and the update path: a resource that loads correctly once can still leave stale GPU state after a file change.

!!! note "Asset sources"
    Demonstration models include assets from [Morgan McGuire's Computer Graphics Archive](https://casual-effects.com/data/). Check the upstream terms before redistributing content outside the repository.
