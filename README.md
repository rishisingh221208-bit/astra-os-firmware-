# 🚀 AstraOS v1.0 — ARM64 Bare-Metal Security Microkernel

**AstraOS** is an ultra-lightweight, zero-trust 64-bit ARM (`aarch64-unknown-none`) microkernel written in bare-metal Rust (`no_std`). This repository distributes the official pre-compiled binary firmware (`aura-kernel.bin`) while the core source architecture remains proprietary.

### ⚡ Core Capabilities
* **Instant Cold Boot (<50ms):** Executes directly from the ARM64 reset vector.
* **6-Slot Process Control Block (PCB):** Hardware-isolated task table (`PID 0–5`).
* **Fast-IPC Engine:** Synchronous per-PID message mailboxes.
* **Capability-Based Security:** Bitmask privilege enforcement (`caps`, `grant`, `revoke`).
* **1080p Framebuffer UI & RAM Vault:** Dark/Light terminal and volatile zero-trace RAM disk.

### 💻 Quick Start (Run in QEMU on PC or Android Termux)
Download `aura-kernel.bin` from the **Releases** page and run:
`qemu-system-aarch64 -M virt -cpu cortex-a57 -nographic -kernel aura-kernel.bin`

### 🛠️ Interactive Shell Commands (AURA-SHELL)
* **Tasks:** `ps` • `spawn <name>` • `kill <pid>`
* **IPC:** `send <pid> <msg>` • `recv <pid>`
* **Security:** `caps` • `revoke` • `grant`
* **System:** `save <data>` • `read` • `dark` • `light` • `clear` • `ver` • `mem` • `uptime` • `sleep` • `reboot`
