# NativeCode runtime assets

Release assets downloaded at runtime by the F-Droid build of [NativeCode](https://github.com/zenithblue-oss/nativecode)
(`com.zenithblue.nativecode.fdroid`). This repository holds no source code: only GitHub Releases.

The app downloads these files only after an in-app opt-in and accepts each one only if its size and SHA-256 match the
pins compiled into the app (`ReleasePins.kt`). A published asset is never overwritten: new bytes get a new file name and a new pin.

## Release `runtime-1.8.0`

| file | bytes | sha256 |
|---|---:|---|
| `panvk-26.3.1-libvulkan_panfrost_kbase.so` | 33,917,432 | `063bcf0cacd6605458f01530e7fc4f4de43cda7d7a995d9518e1a6e38f5d0db6` |
| `turnip-27.0.0-r2-libvulkan_freedreno.so` | 16,912,208 | `33b4acfbc04205d34e57178301b32f06df1539568fcb1e9b37688a3e777163ab` |

`SHA256SUMS` in this repository (and attached to the release) verifies them: `sha256sum -c SHA256SUMS`.
The root filesystem, runtime update pack and Android SDK pack are not published yet: they are pending a license review of their contents and will be added (under new file names if their bytes change) in a later update.

## Contents and licenses

* `panvk-26.3.1-libvulkan_panfrost_kbase.so`: Mesa PanVK (Mali), MIT license plus patches under Mesa's license; vendored kbase UAPI headers GPL-2.0 WITH Linux-syscall-note.
  Source and NOTICE: https://github.com/zenithblue-oss/panvk-kbase-android/releases/tag/panvk-kbase-v26.3.1
* `turnip-27.0.0-r2-libvulkan_freedreno.so`: Mesa Turnip (Adreno), MIT license, taken from LFDev
  https://github.com/lfdevs/mesa-for-android-container/releases/tag/mesa-27.0.0-devel-20261025-r2

No proprietary software is shipped here.
