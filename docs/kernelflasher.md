# Install with Kernel Flasher

> [!NOTE]
> This method is more convenient when upgrading KernelSU and can be done without a computer.

See [Installation](installation.md) for prerequisites, supported versions, and risks.

## Prerequisites

- Root access already granted to the flashing app (for first install from stock without root, use recovery/fastboot — see [magiskboot](magiskboot.md))
- AnyKernel3 ZIP matching your kernel version from [Releases](https://github.com/WildKernels/GKI_KernelSU_SUSFS/releases)

## Steps

1. **Download the AnyKernel3 ZIP** from the latest [Releases](https://github.com/WildKernels/GKI_KernelSU_SUSFS/releases) page.
2. **Open the Kernel Flasher app**, grant root permissions when prompted.
3. **Select the AnyKernel3 ZIP** and flash. Do not interrupt.
4. **Reboot** when prompted and verify the manager shows the expected version.

## Supported flashing apps

| App | Notes |
|-----|-------|
| [Kernel Flasher](https://github.com/fatalcoder524/KernelFlasher) | Recommended, actively maintained |

## After flashing

See [Post-Install — Verify & Finish Setup](post-install.md).
