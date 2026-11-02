# NZ:P Android Touch Prototype (0.1)

This is a **native Android Java prototype** that demonstrates the requested classic World at War Zombies-style landscape HUD and multi-touch input. It includes a simple original placeholder arena, targets, ammo/reload and wave counters.

## Important scope note
This is **not yet an NZ:P port** and does not contain NZ:P's Quake engine, QuakeC game code, maps, models, sounds or other game assets. The upstream NZ:P README says the hub points to separate `assets`, `vril-engine`, and `quakec` repositories, and lists Linux/handheld/console/WebGL/Windows targets but not Android. See https://github.com/nzp-team/nzportable and https://github.com/nzp-team.

The project is intentionally an independently authored Android shell/prototype. Integrating NZ:P requires adapting an engine backend (likely FTEQW/Vril or another suitable Quake sourceport), compiling native ARM64 libraries with the Android NDK, then wiring the engine's input/render lifecycle to this activity. The upstream engine fork has historically stated it does not support Android/touch devices, so this is substantial engineering, not a one-line build option.

## Build
Requirements: Android Studio (or Android SDK + JDK 17), Android Gradle Plugin 8.7.3.

1. Open this folder in Android Studio.
2. Allow Gradle sync.
3. Connect an Android device with USB debugging enabled, or use an emulator.
4. Run `app`.

To build an APK from a terminal with Gradle installed:
`gradle assembleDebug`

APK output:
`app/build/outputs/apk/debug/app-debug.apk`

## Controls
- Left bottom: movement stick
- Right lower: fire
- Right middle/lower: reload
- Right upper: jump / grenade
- Lower center-right: weapon switch
- Drag elsewhere: look input area (placeholder)

## Next engineering milestone
Replace `GameView`'s placeholder Canvas renderer/game loop with an engine bridge and a real 3D game renderer; retain the Android Activity and redesign input routing to deliver analog movement/look plus action events to the engine.
