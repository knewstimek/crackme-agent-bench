# crackme-agent-bench

Reverse engineering benchmark for AI agents.

## What is this?

A collection of crackme binaries designed to test an AI agent's ability to **autonomously reverse engineer** and extract hidden flags using debugger and static analysis tools.

Unlike traditional CTF challenges aimed at humans, these are specifically crafted to evaluate how well AI agents can:

- Analyze unknown binaries through disassembly and static analysis
- Operate a debugger (set breakpoints, step, read memory, patch registers)
- Identify and bypass anti-debugging protections
- Chain multi-step reasoning to solve staged challenges
- Extract secrets that are never printed to stdout

## Why?

As AI agents gain access to development tools via protocols like MCP (Model Context Protocol), we need benchmarks that go beyond text-based reasoning. Reverse engineering is a uniquely demanding task -- it requires tool mastery, low-level systems knowledge, and creative problem-solving all at once.

This benchmark answers the question: **"Can your AI agent actually use a debugger to solve a real reverse engineering challenge?"**

## Tools

These challenges are designed to be solved using MCP-based tools:

| Tool | Description |
|------|-------------|
| [veh-debugger](https://github.com/knewstimek/veh-debugger) | VEH-based in-process debugger exposed as MCP tools (launch, breakpoints, step, memory read/write, registers, disassembly) |
| [agent-tool](https://github.com/knewstimek/agent-tool) | General-purpose MCP toolkit with static binary analysis (PE info, disassembly, strings, hex dump, entropy) |

You can also use any other debugger or analysis tool your agent has access to.

## Challenges

| Challenge | Difficulty | Architecture | Description |
|-----------|-----------|--------------|-------------|
| [v1](v1/) | Medium | x86 / x64 | Multi-stage crackme with anti-debug, stage chaining, and memory-only flag |

## How to Use

### 1. Set up tools

Ensure your AI agent has access to a debugger and static analysis tools (MCP-based or otherwise).

### 2. Give your agent the challenge

Point your agent to a challenge directory. Each challenge has its own README with instructions.

### 3. Evaluate

The agent succeeds if it extracts the correct flag in `VEH{...}` format.

## Challenge Design Principles

- **No source code provided** -- agents must work from binaries only
- **No PDB symbols** -- disassembly and pattern recognition required
- **Flag is never printed** -- must be extracted from memory via debugging
- **Anti-debug protections** -- agents must identify and bypass them
- **Standalone binaries** -- static CRT, no external dependencies

## Contributing

Have an idea for a new challenge? Open an issue or PR. Challenges should:

1. Be solvable with standard debugging/analysis tools
2. Test a specific reverse engineering skill
3. Include both x86 and x64 versions
4. Never require internet access or external services

## License

The challenge binaries are provided as-is for educational and benchmarking purposes. No source code is included.
