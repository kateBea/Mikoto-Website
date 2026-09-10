# Editor

Mikoto-Editor is the application layer built on top of the engine. It is where the runtime becomes inspectable: scenes, transforms, assets, and debug views are all brought into one working surface.

## Editor toolkit

- **ImGui integration** for panels and runtime tooling
- **ImGuizmo transform tools** for move, rotate, and scale operations
- **Infinite grid** for spatial orientation
- **Asset hot reloading** for shorter iteration loops
- **Scene authoring** over the same runtime entities used during execution

## Working with editor changes

Keep editor features thin where possible. A panel should ask the engine for state or issue a focused command; it should not duplicate resource ownership or renderer decisions. This keeps the same feature usable from a game/runtime entry point later.

## A good contribution shape

1. Find the runtime system that owns the behavior.
2. Add or expose the smallest command/state surface needed by the editor.
3. Build the editor affordance around that surface.
4. Test with a small scene and validation enabled.

The [repository map](../reference/repository-map.md) shows where the editor and engine projects live.
