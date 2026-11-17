# SM3DWRecomp

### Super Mario 3D World — Native PC Recompilation Project

**An independent effort to bring the original Wii U version of Super Mario 3D World to Windows through static recompilation.**

---

<p align="center">
  <strong>Wii U PowerPC → Native Windows x86-64</strong>
  <br>
  <em>No emulator runtime. No Cemu dependency. Native execution.</em>
</p>

> [!WARNING]
> **Early Development — Research & Feasibility Phase**
>
> SM3DWRecomp is currently in its initial research and planning stage. No playable build or game compatibility is currently claimed. Development progress and technical capabilities will be documented as they are verified.

## Overview

SM3DWRecomp is an open-source engineering project aiming to produce a fully native Windows PC port of **Super Mario 3D World**, originally released for the Nintendo Wii U.

The project aims to achieve this through **static recompilation**, translating the game's original PowerPC executable into native x86-64 code while implementing the necessary Wii U system functionality through an independent host runtime.

Rather than wrapping an existing emulator, the ultimate objective is a standalone Windows application that executes natively on PC.

## Project Goals

- **Static Recompilation:** Translate original Wii U PowerPC machine code into native x86-64 instructions.
- **Independent Runtime:** Reimplement the necessary Cafe OS functionality without requiring an emulator.
- **Native Graphics:** Develop an independent graphics backend for translating Wii U GX2 functionality to PC graphics APIs.
- **Audio:** Reproduce the necessary Wii U audio functionality through native PC audio systems.
- **GamePad Support:** Recreate the Wii U GamePad display in a separate, configurable PC window.
- **PC Input:** Support modern controllers and appropriate keyboard/mouse input.
- **Single-player First:** Prioritise a complete single-player experience, with local multiplayer considered for later development.

## Technical Direction

| Component | Intended technology |
|---|---|
| Target architecture | Wii U PowerPC |
| Host architecture | x86-64 |
| Primary language | C++ |
| Build system | CMake |
| Initial platform | Windows 10/11 x64 |
| Graphics API | Vulkan (under investigation) |
| Windowing and input | SDL3 (under investigation) |
| Execution model | Static recompilation |
| Runtime | Independent Cafe OS compatibility layer |

Technology choices remain subject to technical feasibility and upstream compatibility research.

## GamePad Implementation

One of the project's goals is to make the Wii U GamePad experience practical on PC.

The planned implementation includes:

- A separate GamePad window.
- Configurable window size and position.
- Touchscreen interaction mapped to appropriate PC input.
- Controller integration.
- Independent window management.

The objective is to preserve the relevant gameplay functionality while making it comfortable to use on a conventional PC setup.

## Project Architecture

The planned architecture is divided into several independent subsystems:

```text
SM3DWRecomp
│
├── Binary Analysis
│   └── RPX/RPL parsing and executable analysis
│
├── Static Recompiler
│   └── PowerPC → Native x86-64
│
├── Cafe OS Runtime
│   └── Wii U system services and memory management
│
├── Graphics
│   └── GX2 translation and native rendering
│
├── Audio
│   └── Native PC audio implementation
│
├── Input
│   └── Controllers, keyboard and mouse
│
├── GamePad
│   └── Separate configurable display window
│
└── Windows Platform
    └── Application lifecycle and integration
```

The architecture is intended to keep reusable recompilation infrastructure separate from game-specific functionality.

## Development Roadmap

Development is planned around independently verifiable milestones. (aspects will be ticked off as they're completed)

- [ ] **Phase 0 — Research & Feasibility**
  - [ ] Audit existing Wii U recompilation projects.
  - [ ] Evaluate upstream code and licensing.
  - [ ] Identify the target Wii U executable and update.
  - [ ] Analyse PowerPC instructions and dependencies.
  - [ ] Establish the independent runtime architecture.

- [ ] **Phase 1 — Foundation**
  - [ ] Establish the CMake build system.
  - [ ] Integrate approved open-source foundations.
  - [ ] Implement testing and diagnostics infrastructure.

- [ ] **Phase 2 — Binary Analysis**
  - [ ] RPX/RPL parsing.
  - [ ] Function and symbol analysis.
  - [ ] Relocation and import handling.

- [ ] **Phase 3 — Static Recompilation**
  - [ ] PowerPC instruction translation.
  - [ ] Native code generation.
  - [ ] ABI and execution correctness.

- [ ] **Phase 4 — Independent Runtime**
  - [ ] Guest memory management.
  - [ ] Cafe OS functionality.
  - [ ] Required system services.

- [ ] **Phase 5 — Graphics & Audio**
  - [ ] GX2 functionality.
  - [ ] Native graphics backend.
  - [ ] Audio implementation.

- [ ] **Phase 6 — Single-player Integration**
  - [ ] Game-specific integration.
  - [ ] Main display.
  - [ ] TBC
     
This was made with the help of Claude (Fable 5.2 on Max) with all directing and testing done by me.
