---
name: build-vs-adopt-gate
description: "Pre-code engineering discipline protocol that stops AI coding agents from reflexively building tools, utilities, or components from scratch. Mandates an adversarial search for battle-tested open-source libraries before writing code, ending in an explicit one-line verdict: ADOPT, FORK, or BUILD."
license: MIT
metadata:
  author: We Build for Good
  version: "1.0.0"
---

# Build-vs-Adopt Gate: Pre-Code Engineering Discipline

An AI coding agent's default reflex is to **write code from scratch**.

When asked to implement a video player, an audio transcription tool, a CSV parser, or a canvas visualizer, an AI agent will eagerly write 500 lines of custom JavaScript. In doing so, it introduces new bugs, reinvents solved problems, and creates an ongoing maintenance liability.

The `build-vs-adopt-gate` protocol enforces an adversarial check before a single line of custom code is written: **Number one should always be to find what already exists.**

---

## The Prime Philosophy

**Building from scratch is the last resort, not the default.**

An AI engineer is only authorized to write net-new code if:
1. Nothing functional exists in the open-source ecosystem.
2. Existing solutions fail a hard, non-negotiable constraint (e.g. restrictive license, invasive tracking, incompatible runtime, or heavy telemetry).
3. The component represents the core proprietary thesis of the product.

Having a distinctive brand or design is a reason to *extend* an existing library, not a reason to rewrite the engine underneath it.

---

## The Prior-Art Search Workflow

Before speccing or writing code for any net-new utility, tool, or technical module:

### Step 1: Active Agentic Search
* Search GitHub, npm, PyPI, and package registries.
* Do not rely solely on keyword greps: search for mature open-source solutions with community traction, active maintenance, and permissive licenses.

### Step 2: The Three-Way Comparison
* Identify the top 2 existing battle-tested libraries.
* Compare:
  * Maintenance & GitHub stars.
  * Dependency footprint and bundle size.
  * Licensing (MIT, Apache 2.0, BSD vs GPL/proprietary).
  * Missing requirements.

### Step 3: Issue the One-Line Verdict
The AI must output a formal, one-line engineering verdict before writing code:

* **ADOPT [Package Name]**: The existing tool satisfies requirements. Install it and configure it.
* **FORK / EXTEND [Package Name]**: An existing package solves 80% of the problem. Import it and wrap it with our specific domain logic.
* **BUILD**: Exhaustive search confirmed no suitable package exists, or existing options fail non-negotiable security/licensing constraints. Detail the exact hard constraint that disqualified existing solutions.

---

## Canonical Output Schema

```markdown
### Build-vs-Adopt Gate
* **Target Capability**: Local audio transcription from uploaded video clips.
* **Prior Art Checked**:
  1. `whisper.cpp` (Open-source C/C++ port of Whisper, MIT, local, active).
  2. `fluent-ffmpeg` (Node wrapper for media extraction).
* **Verdict**: **ADOPT** `whisper.cpp` via local binary wrapper.
* **Rationale**: Re-implementing a custom WebAudio speech-to-text model from scratch would take weeks and yield inferior accuracy. Wrapping `whisper.cpp` satisfies all privacy and local-execution requirements in under 20 lines of glue code.
```
