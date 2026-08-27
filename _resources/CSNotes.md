---
title: CS Notes
layout: page
toc: true
category: collections
tag: resources
description: Short random notes I have.
---

## Advanced Red Teaming, EDR Evasion & Identity Warfare
1. Advanced EDR Evasion & Windows Internals
    1.1 User-Mode Hooking & Syscall Architectures
            Direct vs. Indirect Syscalls:

            -  Direct syscalls: Resolving System Service Numbers (SSNs) at runtime dynamically via Export Address Table (EAT) sorting (Hell's Gate, Halo's Gate, Tartarus Gate, SysWhispers3).

            -   Indirect syscalls: Executing the syscall instruction within the memory space of ntdll.dll to ensure valid execution context, clean rip pointers, and unflagged kernel callback telemetry.

    **AMSI & ETW Neutralization:**

    In-memory patching of AmsiScanBuffer and EtwEventWrite.
        - Hardware Breakpoints & Vectored Exception Handling (VEH): Setting debug registers (DR0-DR3, DR7) to hook and suppress security telemetry without modifying code section permissions (RX to RWX).
    
        - DLL Unhooking: Fresh copy extraction via KnownDlls, direct disk read with manual PE parsing, or suspended process mapping (Perun's Fart).

    1.2 Process Injection & Execution Flow Hijacking
        Advanced Loaders & Injection Vectors:

        - Early Bird APC & QueueUserAPC: Injecting shellcode into suspended threads before EDR telemetry hooks initialize.

        - Module Stomping / Ghosting / Herpaderping / Transacted Hollowing: Hiding memory payloads behind legitimate, on-disk signed binaries to defeat memory scanning (e.g., VirtualQueryEx validation).

        - Threadless Injection: Utilizing hook points in execution loops without creating dedicated threads.

        - Fiber-based Execution: Switching thread contexts to execute shellcode within fiber structures.

        - Call Stack Spoofing & Synthetic Frames:
            Bypassing kernel-level stack walking by crafting synthetic stack frames that mimic legitimate Windows API call chains (e.g., SilentMoonwalk, TitanLdr).
    
        - Sleep Obfuscation (Ekko, Foliage, Cronos): Encrypting heap/stack memory and modifying page protections to NOACCESS during sleep states via timers (NtCreateTimer2, ROP chains).