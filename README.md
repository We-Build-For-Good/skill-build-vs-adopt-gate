# Build-vs-Adopt Gate: Pre-Code Engineering Discipline

> **An open-source AI engineering protocol from [We Build for Good](https://webuildforgood.com)**  
> *Stop AI agents from reinventing wheels.*

---

## Overview

`build-vs-adopt-gate` is an operational protocol for AI coding assistants (Claude Code, Cursor, Antigravity, OpenAI Codex).

It prevents the common failure mode where an AI coding agent writes hundreds of lines of custom code for utilities, algorithms, or components that already have mature, battle-tested open-source libraries available.

---

## The Verdict Rule

Before writing code, the AI must search package registries and GitHub, issuing an explicit one-line verdict:
* **ADOPT [Package]**: Use the existing library directly.
* **FORK / EXTEND [Package]**: Wrap or extend an existing library.
* **BUILD**: Only permitted when existing libraries fail a hard, non-negotiable constraint.

---

## Installation

### For Claude Code
```bash
git clone https://github.com/We-Build-For-Good/skill-build-vs-adopt-gate.git ~/.claude/skills/build-vs-adopt-gate
```

### For Cursor
```bash
mkdir -p .cursor/skills
git clone https://github.com/We-Build-For-Good/skill-build-vs-adopt-gate.git .cursor/skills/build-vs-adopt-gate
```

### For Antigravity / Open Agent Skills
```bash
mkdir -p .agents/skills
git clone https://github.com/We-Build-For-Good/skill-build-vs-adopt-gate.git .agents/skills/build-vs-adopt-gate
```

---

## License

MIT License. Developed and maintained by [We Build for Good](https://webuildforgood.com).
