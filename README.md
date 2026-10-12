# Android 16 for Orange Pi 5 Plus

This is a development repository for porting Android 16 to the Orange Pi 5 Plus with a mainline Linux kernel.

## Android and kernel versions

Versions read from the running tablet image on 2026-10-13:

| Component | Version |
| --- | --- |
| Android | Android 16 (API level 36) |
| Android build ID | `BP3A.250905.014` |
| Reported Android security patch level | `2025-09-05` |
| Build type | `userdebug`, signed with development `test-keys` |
| Linux kernel | `6.18.55-opi5plus-googlebook-native` |

The build ID identifies the Android platform revision used by this image. The security patch date is the value reported by Android; it is not an independent verification of patch coverage across the kernel and vendor components. The kernel suffix is its build identifier; this image runs Android 16 for Orange Pi 5 Plus.

## Preinstalled apps

The Android 16 tablet image includes Aurora Store, Rockchip Video Player, Jelly browser, Gallery, Camera, Files, Calendar, Contacts, Clock, Search, Settings, Launcher3 and the Android keyboard. Rockchip HDMI-IN, HDMI input audio and TV input components are also included.

See the [verified app list and update notes](docs/preinstalled-apps.md) and [complete system package inventory](docs/system-packages.tsv).
