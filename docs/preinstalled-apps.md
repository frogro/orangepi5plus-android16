# Preinstalled apps

Inventory read through ADB from the running Orange Pi 5 Plus Android 16 vanilla tablet image on 2026-10-13. Kernel: `6.18.55-opi5plus-googlebook-native`.

Installation is verified; inclusion alone does not confirm every app or hardware function works. HDMI-IN camera/HAL and input-audio integration remain incomplete.

| App or component | Package | Purpose / notes |
| --- | --- | --- |
| Aurora Store | `com.aurora.store` | 4.8.4; app download and update client |
| Rockchip Video Player | `android.rk.RockVideoPlayer` | 3.5-20220208-8.0; configured default video player |
| Orange Pi / Rockchip HDMI-IN | `com.android.rockchip.camera2` | HDMI capture app; integration still under test |
| Jelly browser | `org.lineageos.jelly` | Web browser |
| Gallery | `com.android.gallery3d` | Photos and albums |
| Camera | `com.android.camera2` | AOSP camera app; requires a working camera HAL |
| Files | `com.android.documentsui` | File browser and document picker |
| Calendar | `com.android.calendar` | Calendar |
| Contacts | `com.android.contacts` | Address book |
| Clock | `com.android.deskclock` | Clock, alarms and timer |
| Search | `com.android.quicksearchbox` | Search interface |
| Settings | `com.android.settings` | Android settings |
| Launcher3 Quickstep | `com.android.launcher3` | Home screen |
| Android keyboard | `com.android.inputmethod.latin` | On-screen keyboard |
| Music | `com.android.music` | Bundled music app; no launcher activity returned in this snapshot |
| MusicFX | `com.android.musicfx` | Audio effects component |
| Android WebView | `com.android.webview` | Embedded web content |
| HDMI-IN Audio | `com.rockchip.rkhdmiinaudio` | Rockchip HDMI input audio component; integration still under test |
| TV Input | `com.example.partnersupportsampletvinput` | Rockchip TV input component; integration still under test |
| Provision | `com.android.provision` | AOSP initial provisioning component |

## Updates

Aurora is the app-store client for installing and updating compatible store apps. Availability depends on the selected device profile; the earlier YouTube installation used Aurora's Pixel Tablet profile. That profile is not asserted to be preconfigured in this fresh image.

AOSP system apps, Jelly, and board-specific Rockchip components are maintained with the image unless a compatible, identically signed update is provided. Do not assume Aurora can update these packages. Aurora Store updates also require a compatible signature and an available update source.

## Google and streaming apps

Google Play services, Google Services Framework and Google Play Store are absent from this inventory. YouTube, Gmail and Prime Video are not preinstalled. Apps obtained through Aurora may still depend on Google services or device certification.

## Complete inventory

[system-packages.tsv](system-packages.tsv) lists all system APK packages reported by `pm list packages -s -f --show-versioncode`, including background services, resource overlays and APKs within APEX modules. These are not all launcher apps. This is an APK inventory, not a list of native libraries, kernel modules or every APEX container.

The launcher query returned 12 activities: Aurora Store, Rockchip Video Player, HDMI-IN, Jelly, Gallery, Camera, Files, Calendar, Contacts, Clock, Search and Settings. No third-party user-installed packages were reported by `pm list packages -3` at collection time.
