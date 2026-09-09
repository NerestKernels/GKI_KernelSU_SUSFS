# Patch boot.img Manually (magiskboot)

Use the [official magiskboot build](https://github.com/topjohnwu/Magisk/releases) — works on Android and Linux.

See [Installation](installation.md) for prerequisites, supported versions, and risks.

**Platforms:** [Android](#-android) · [Linux](#-linux)

## Preparation

1. Get your device's stock `boot.img`.
2. Download the AnyKernel3 ZIP for your kernel version from [Releases](https://github.com/WildKernels/GKI_KernelSU_SUSFS/releases).
3. Unpack the ZIP and get the `Image` file (the KernelSU kernel).

---

<details>
<summary><b> Android</b> — via adb + <code>libmagiskboot.so</code></summary>

Folder structure on device (`/data/local/tmp/`):

```
/data/local/tmp/
├── magiskboot
├── boot.img
└── Image
```

1. Download latest Magisk from [GitHub Releases](https://github.com/topjohnwu/Magisk/releases).
2. Rename `Magisk-*(version).apk` to `Magisk-*.zip` and unzip.
3. Push `libmagiskboot.so` to device:
  ```sh
  adb push Magisk-*/lib/arm64-v8a/libmagiskboot.so /data/local/tmp/magiskboot
  ```
4. Push `boot.img` and `Image`:
  ```sh
  adb push boot.img /data/local/tmp/
  adb push Image /data/local/tmp/
  ```
5. Make executable:
  ```sh
  adb shell
  cd /data/local/tmp/
  chmod +x magiskboot
  ```
6. Unpack:
  ```sh
  ./magiskboot unpack boot.img
  ```
7. Replace kernel:
  ```sh
  mv -f Image kernel
  ```
8. Repack:
  ```sh
  ./magiskboot repack boot.img
  ```
9. Test: `fastboot boot new-boot.img`
10. Flash: `fastboot flash boot new-boot.img`

</details>

<details>
<summary><b> Linux</b> — official magiskboot</summary>

Folder structure on PC:

```
.
├── magiskboot
├── boot.img
└── Image
```

1. Prepare `boot.img` and `Image` on PC.
2. Make executable: `chmod +x magiskboot`
3. Unpack: `./magiskboot unpack boot.img`
4. Replace: `mv -f Image kernel`
5. Repack: `./magiskboot repack boot.img`
6. Test: `fastboot boot new-boot.img`
7. Flash: `fastboot flash boot new-boot.img`

</details>
