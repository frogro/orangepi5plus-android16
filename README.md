# Android 16 for Orange Pi 5 Plus

This is a development repository for porting Android 16 with a tablet interface to the Orange Pi 5 Plus with a mainline Linux kernel.

## Android and kernel versions

Versions read from the running system on 2026-10-13:

| Component | Version |
| --- | --- |
| Android | Android 16 (API level 36) |
| Android build ID | `BP3A.250905.014` |
| Reported Android security patch level | `2025-09-05` |
| Build type | `userdebug`, signed with development `test-keys` |
| Linux kernel | `6.18.55` |

The build ID identifies the Android platform revision used by this image. The security patch date is the value reported by Android; it is not an independent verification of patch coverage across the kernel and vendor components. The kernel suffix is its build identifier; this image runs Android 16 for Orange Pi 5 Plus.

## Video decoding and Wi-Fi

The image supports hardware-accelerated video decoding at HD, Full HD and up to **4K (3840×2160)** using the RK3588 V4L2 stack and `rkvdec`. **H.264 (AVC), H.265 (HEVC) and VP9** each passed a 4K/30 fps decode-only test on the fresh image, with all 300 frames decoded. Smooth ongoing playback is expected for compatible content, but sustained playback and 60 fps have not been validated. These tests do not verify 4K HDMI output or AV1 hardware decoding.

Streaming quality also depends on the app, subscription, provider policies and device certification. Hardware decoding support alone does not guarantee HD or 4K access from a streaming service. **Widevine DRM is not included in this image**, and secure DRM decoding and HDCP support are not established; protected services may restrict quality or refuse playback.

The installed Wi-Fi card uses a **Realtek RTL8852BE** chipset (PCI ID `10ec:b852`) with the Linux **`rtw89_8852be`** driver. The running image detects the card and exposes `wlan0`. This identifies the tested chipset, not a compatibility guarantee for other Wi-Fi cards; connection and throughput tests on the fresh image remain pending.

## Preinstalled apps

The Android 16 tablet image includes Aurora Store, Rockchip Video Player, Jelly browser, Gallery, Camera, Files, Calendar, Contacts, Clock, Search, Settings, Launcher3 and the Android keyboard. Rockchip HDMI-IN, HDMI input audio and TV input components are also included.

See the [verified app list and update notes](docs/preinstalled-apps.md) and [complete system package inventory](docs/system-packages.tsv).
