# AstraOS v1.0 — ARM64 firmware

AstraOS is distributed here as a prebuilt firmware binary. The repository currently contains documentation only; it does not include the kernel source code, build instructions, or tests. Consequently, the implementation and the security and performance claims in the release cannot be independently verified from this repository.

## Download and run

Download `aura-kernel.bin` from the [v1.0.0 release](https://github.com/rishisingh221208-bit/astra-os-firmware-/releases/tag/v1.0.0). If you have QEMU's AArch64 system emulator installed, try:

```sh
qemu-system-aarch64 -M virt -cpu cortex-a57 -nographic -kernel aura-kernel.bin
```

This command assumes the downloaded binary is compatible with QEMU's `virt` machine and `-kernel` loader. The repository does not provide source or build metadata to verify the binary format or reproduce the build. Compatibility with physical ARM64 hardware is not documented here; do not assume the image is safe or suitable for production use.

## Features advertised by the v1.0.0 release

The release notes describe the following features and shell commands. These are release claims and have not been independently verified in this source-free repository:

- Task management: `ps`, `spawn <name>`, `kill <pid>`
- Message passing: `send <pid> <msg>`, `recv <pid>`
- Capabilities: `caps`, `grant`, `revoke`
- Storage and display: `save <data>`, `read`, `dark`, `light`
- System: `clear`, `ver`, `mem`, `uptime`, `sleep`, `reboot`

## Contributing and verification

To make the firmware auditable and reproducible, add the source code, target/toolchain requirements, build and test instructions, and a description of how release binaries are produced. Until then, this repository can only document and link to the prebuilt release.
