# zmk-config

A personal ZMK firmware configuration for left and right `nice_nano_v2` Corne halves.
The build matrix selects `corne_left` and `corne_right` without an additional display shield.

This is a firmware configuration repository. It has no desktop application,
terminal command database or man page to install.

## Files

| File | Purpose |
|---|---|
| [config/corne.keymap](config/corne.keymap) | Layers, behaviors and key positions |
| [config/corne.conf](config/corne.conf) | Firmware feature settings |
| [config/west.yml](config/west.yml) | ZMK source/dependency selection |
| [build.yaml](build.yaml) | Board/shield build matrix |
| [.github/workflows/build.yml](.github/workflows/build.yml) | GitHub Actions firmware build |

The source selection currently follows ZMK `v0.2` through the manifest defaults. The workflow itself uses
ZMK's reusable build-user-config workflow. These are the settings in this
snapshot, rather than an instruction to upgrade firmware dependencies.

## Observed build status

The pinned v0.2 firmware compiles to UF2, but the current reusable workflow fails its board-compatibility check with `KeyError: 'qualifiers'`. This is a workflow/tooling compatibility issue to investigate before relying on published artifacts.
See the [CI run](https://github.com/WaltRudyJabsco/zmk-config/actions/runs/41268297006).
The documentation change leaves the keymap, firmware settings, dependency
selection and workflow bytes unchanged; it does not repair this existing setup.

## Build and use

1. Edit the keymap or feature settings, then commit the configuration.
2. Open this repository's **Actions** tab and inspect the firmware build.
3. Download the successful run's firmware artifact and select the image matching
   the keyboard half and hardware in `build.yaml`.
4. Follow the [official ZMK setup and flashing guide](https://zmk.dev/docs/user-setup)
   for the controller's bootloader workflow.

The documentation refresh does not claim a new hardware build or flashing test.
The keymap file remains the exact source of truth for bindings and layers.

## Related configurations

[5-col-view](https://github.com/WaltRudyJabsco/5-col-view),
[corne-5-plus](https://github.com/WaltRudyJabsco/corne-5-plus), and
[zmk-config](https://github.com/WaltRudyJabsco/zmk-config) are separate snapshots.
Their keymaps and feature settings differ, even where build targets look similar.
