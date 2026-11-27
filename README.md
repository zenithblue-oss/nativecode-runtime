# NativeCode runtime assets

Release assets downloaded at runtime by the F-Droid build of [NativeCode](https://github.com/zenithblue-oss/nativecode)
(`com.zenithblue.nativecode.fdroid`). This repository holds no source code: only GitHub Releases.

The app downloads these files only after an in-app opt-in and accepts each one only if its size and SHA-256 match the
pins compiled into the app (`ReleasePins.kt`). A published asset is never overwritten: new bytes get a new file name and a new pin.

## Release `runtime-1.8.0`

| file | bytes | sha256 |
|---|---:|---|
| `alpaquita_rootfs.tar.zst` | 1,356,467,533 | `edeec26af1c7d7dedd490c99473733ad90b8fff16aab27c63c6f43d467ff0698` |
| `nativecode_update.tgz` | 316,974,152 | `fa9f25582d523fa36c3fc93e260aabafa1762842a6dd65bfa71ee093de778a01` |
| `nativecode_android_dev.tar.xz` | 69,451,708 | `f4d4aad5b8f78cd68b0254718626576c547ca187cb5c682faaa8b2e0fbc10a2d` |
| `panvk-26.3.1-libvulkan_panfrost_kbase.so` | 33,917,432 | `063bcf0cacd6605458f01530e7fc4f4de43cda7d7a995d9518e1a6e38f5d0db6` |
| `turnip-27.0.0-r2-libvulkan_freedreno.so` | 16,912,208 | `33b4acfbc04205d34e57178301b32f06df1539568fcb1e9b37688a3e777163ab` |

`SHA256SUMS` in this repository (and attached to the release) verifies all five: `sha256sum -c SHA256SUMS`.

## Contents and licenses

* `panvk-26.3.1-libvulkan_panfrost_kbase.so`: Mesa PanVK (Mali), MIT license plus patches under Mesa's license; vendored kbase UAPI headers GPL-2.0 WITH Linux-syscall-note.
  Source and NOTICE: https://github.com/zenithblue-oss/panvk-kbase-android/releases/tag/panvk-kbase-v26.3.1
* `turnip-27.0.0-r2-libvulkan_freedreno.so`: Mesa Turnip (Adreno), MIT license, taken from LFDev
  https://github.com/lfdevs/mesa-for-android-container/releases/tag/mesa-27.0.0-devel-20261025-r2
* `alpaquita_rootfs.tar.zst`: the guest root filesystem (Alpaquita Linux, glibc, aarch64) with the Linux desktop and developer tools. Packages keep their own licenses.
  It includes third-party command-line tools (AI coding agent and developer CLIs) that are distributed under their own vendors' licenses and terms, not under this project's license.
* `nativecode_update.tgz`: runtime update pack applied on top of the root filesystem. It contains OpenSSH, zsh and the third-party command-line tools `grok`, `agy` (Antigravity), `opencode` and `gh`, each under its own vendor's license and terms.
* `nativecode_android_dev.tar.xz`: Android SDK components (for building Android apps inside the guest). These are Google's software, provided under the Android SDK License Agreement, not under this project's license.

Use of any of the third-party tools is subject to the vendor's own terms.
