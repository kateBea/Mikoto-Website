# Profiling with Tracy

Mikoto integrates [Tracy](https://github.com/wolfpld/tracy) for CPU, GPU, and memory profiling. Profiling is disabled by default.

## Enable instrumentation

Enable `MIKOTO_ENABLE_TRACY_PROFILING` in the relevant CMake configuration. The editor CMake file is the reference point for the current option wiring.

Build, then launch the Tracy Profiler GUI before running the instrumented editor.

!!! warning "Keep Tracy connected"
    When instrumentation is enabled but the profiler is not connected, Tracy continues to run internally. The project notes that this can lead to memory leaks, so use the profiler GUI during instrumented sessions.

## What to measure

- **CPU zones:** frame stages, asset loading, scene traversal, and editor panels
- **GPU zones:** expensive passes and synchronization points
- **Memory:** resource churn, hot reload behavior, and transient allocations

Mikoto currently uses Tracy Profiler v3.3.0. Match the version used by the engine when reproducing profiling behavior.
