# PomAROS

**AROS on Apple Silicon Macs.** Choose a macOS-hosted system or an independent AROS virtual machine.

PomAROS builds on [AROS](https://github.com/aros-development-team/AROS), with shared operating-system sources and different ways to run them on a Mac.

| | [PomAROS Hosted](https://github.com/pomaros/pomaros-hosted) | [PomAROS VM](https://github.com/pomaros/pomaros-vm) | [PomAROS QEMU](https://github.com/pomaros/pomaros-qemu) |
| --- | --- | --- | --- |
| How it runs | AROS runs as a macOS process, using macOS drivers and host bridges. | An independent AROS guest using Apple's built-in Virtualization.framework. No QEMU required to run the app. | An independent AROS guest using QEMU, with HVF hardware acceleration or explicitly selected TCG software emulation. |
| Host integration | Native host bridges, including files, clipboard and CoreAudio. | Integrated file exchange, clipboard and coordinated guest shutdown. | QEMU networking; host file/clipboard bridges and coordinated guest shutdown are not implemented. |
| Desktop | [![PomAROS Hosted desktop and live monitor](https://raw.githubusercontent.com/pomaros/pomaros-hosted/main/docs/images/pomaros-hosted.png)](https://github.com/pomaros/pomaros-hosted) | [![PomAROS VM desktop and live monitor](https://raw.githubusercontent.com/pomaros/pomaros-vm/main/docs/images/pomaros-vm.png)](https://github.com/pomaros/pomaros-vm) | [![PomAROS QEMU desktop and live monitor](https://raw.githubusercontent.com/pomaros/pomaros-qemu/main/docs/images/pomaros-qemu.png)](https://github.com/pomaros/pomaros-qemu) |

Start with the README in the project that matches how you want to run AROS. Each repository includes build instructions, measured results and current limitations. These are development projects, not finished releases; QEMU is not yet qualified for safe persistence across an ordinary window close.

All three targets use the same reviewed source revision from [the public shared AROS core](https://github.com/pomaros/aros-core), a fork retaining official AROS history. VM and QEMU share the same guest kernel build; Hosted has a separate build for macOS that preserves its host ABI. Each product pins its core revision and documents the build prerequisites. The longer-term goal is to reuse the kernel work across native Apple Silicon and Raspberry Pi targets.

## Software for AROS

Native AROS programs and the tools that build them, for PomAROS and native AROS on AArch64:

| Repository | What |
| --- | --- |
| [rust-aros](https://github.com/pomaros/rust-aros) | Rust for native AROS with the official, unmodified compiler: target, standard library patch, native adapters and crate patches. |
| [gpui-aros](https://github.com/pomaros/gpui-aros) | The AROS platform backend for GPUI, the UI framework of the Zed editor: Intuition windows, CPU rendering, menus, requesters and clipboard. |
| [gpui-kit](https://github.com/pomaros/gpui-kit) | The gpui-kit component library with its AROS port (branch `aros-port-0.7.1`). |

Bug reports and contributions are welcome through the relevant repository's issues and pull requests. General AROS improvements are submitted upstream as focused changes.

[PomAROS](https://github.com/pomaros) · [jonx](https://github.com/jonx)
