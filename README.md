# dxvk-gplasync
https://github.com/Sporif/dxvk-async updated for newer dxvk versions

# Improvements
- Compatible with dxvk 2.1
- Async can be used at same time as graphics pipeline library.
- Shader cache works with async (async+gpl is unknown as radv does not support shader cache with gpl currently)

# Shader cache
While shader cache works with this patch, i noticed issue that may be caused by async. Shader cache grows larger, and at some point it starts to cause stutter. This may not be problem in every game.

This issue should be fixed in now, i added check that stops it from writing to cache if its still compiling. This makes shader cache stay smaller, maybe even smaller than no async, so it may not cache all shaders but cache still reduces graphics glitching that happens when shaders are compiling.