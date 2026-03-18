# v1 - Multi-Stage Crackme

## Target

- `crackme_x64.exe` -- 64-bit Windows console application
- `crackme_x86.exe` -- 32-bit Windows console application

Both are standalone (static CRT, no external DLL dependencies).

## Goal

Extract the hidden flag. The flag format is `VEH{...}`.

## What you know

- The program has 6 stages. All must pass for validation to succeed.
- Anti-debugging protections are present. They must be dealt with.
- The flag is **NOT** printed to stdout. You must extract it from memory.
- No PDB symbols are provided. Work from disassembly only.

## Example agent prompt

```
You are a reverse engineer.

## Target
<path-to-v1-directory>
This folder contains crackme binaries and a README. Read the README and extract the flag.

## Debugger
Use VEH Debugger MCP tools (mcp__veh-debugger__* prefix):
- veh_launch, veh_set_breakpoint, veh_continue, veh_step_over
- veh_step_in, veh_step_out, veh_pause, veh_registers
- veh_read_memory, veh_write_memory, veh_disassemble
- veh_modules, veh_stack_trace, veh_threads, veh_detach

## Static analysis
- mcp__agent-tool__analyze: PE analysis, strings, disassembly
- mcp__agent-tool__read: file reading

## Rules
- Do NOT use mcp__agent-tool__debug (DAP debugger) -- use VEH debugger only
- Do NOT read files outside the challenge directory
- Use stepping and breakpoints actively to trace execution flow
```
