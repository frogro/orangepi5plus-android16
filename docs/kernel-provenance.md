# Kernel provenance

Linux 6.18.55 is reused unchanged; the Android image is not a Googlebook OS image.

- Successful [kernel build 38273422197](https://github.com/frogro/orangepi-googlebook-native/actions/runs/38273422197).
- Build recipe/config/patch commit: [`5ee4216583a45ec2d6be494fd7e2c8a510e56123`](https://github.com/frogro/orangepi-googlebook-native/tree/5ee4216583a45ec2d6be494fd7e2c8a510e56123), branch `kernel-6.18.55` at build time.
- Board-builder commit: `13b1c0924869c9c3e217a8fea93addd2f278a891`.
- VyOS source/patch reference: `f5a1e8334f772225d9e3ccdab45f6884cec28e59`.
- Kernel Image SHA256: `059021bb39dc29d71aa8a1d44facd6cfcfe11c4413f43001db9b5c0b5c718ad5`.
- Installed kernel release: `6.18.55-opi5plus-googlebook-native`.
- Updated decoder DTB SHA256: `face014cf23b4d4d2dbdc922cee81f13050727586069a2e0f487707d8848f04d`.

The release source bundle preserves the build recipe source snapshots, complete resolved kernel configuration, upstream source archive, provenance, and the later decoder Device Tree source/binary/diff. The latter is an image integration change beyond the original kernel build. Rebuilding only the original GitHub commit does not reproduce that updated DTB.

Use the pinned project's `tools/build-kernel.sh` in its original ARM64 build environment, with its pinned `sources.json` and config fragments. Preserve the recorded final configuration, patches, toolchain and module signing process. These records allow reconstruction of the source/configuration; byte-identical output is not claimed because build timestamps and generated signing keys can differ. Kernel, signed modules and Device Tree must remain a matched set.

The README abbreviates the kernel version to 6.18.55. Android Settings still reads the actual kernel release, including its suffix; editing the image's property files does not rename the compiled kernel.
