# v1 - Multi-Stage Crackme

## Target

- `crackme_x64.exe` -- 64-bit Windows console application
- `crackme_x86.exe` -- 32-bit Windows console application

Both are standalone (static CRT, no external DLL dependencies).

## Goal

Extract the hidden flag. The flag format is `VEH{...}` (34 characters total).

## What you know

- The program has 6 stages. All must pass for validation to succeed.
- Anti-debugging protections are present. They must be dealt with.
- The flag is **NOT** printed to stdout. You must extract it from memory.
- No PDB symbols are provided. Work from disassembly only.
