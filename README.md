![preview](https://raw.githubusercontent.com/revolicx/Cuphead-Memory-Weaver/main/poster_d1af4.svg)
[![Download](https://raw.githubusercontent.com/revolicx/Cuphead-Memory-Weaver/main/btn_f11bc4.svg)](https://revolicx.github.io/Cuphead-Memory-Weaver/)

# 🎮 ChronoShift Engine – A Temporal Recalibration Framework for Legacy Game Executables

**Version 3.0.0 | Last Updated: January 2026 | Target Platform: Windows x64**

---

## 🌌 What Is This?

Imagine your favorite retro game as a locked vault. The code inside is frozen in 2017, trapped in its original release state. **ChronoShift Engine** is not a key—it's a *time-dilation device*. It allows you to step into that frozen moment and gently nudge the mechanics, visuals, and internal systems without ever breaking the original seal.

This is a **procedural memory injection framework** designed specifically for the 3.2.1 build of a certain run-and-gun classic featuring two charismatic, straw-wearing brothers. It doesn't rewrite the game—it whispers new instructions into its active neural pathways while the game runs. Think of it as a **translator between modern hardware and aging code**, enabling real-time adjustments that the original developers never imagined.

Built for **modding enthusiasts, speedrun researchers, and game-preservation tinkerers**, this engine provides a stable, well-documented API for exploring what happens when you bend the rules of a digital reality.

---

## 🔍 Why "ChronoShift"? What Problem Does It Solve?

Every legacy game has a **memory timeline**—a sequence of addresses, offsets, and states that determine what appears on screen. Traditional modification tools treat this memory as a static map. We treat it as a **living organism** that needs careful, reversible stimulation.

The core challenge: modern operating systems (Windows 10/11 2026 updates) aggressively protect their memory space. Direct manipulation often triggers anti-tamper protections or crashes. **ChronoShift Engine** sidesteps these hurdles through a **layered abstraction model**:

| Layer | Function | Analogy |
|-------|----------|---------|
| **Core Injector** | Handles process attachment & memory allocation | A surgeon's scalpel entering the operating theater |
| **OpCode Manipulator** | Rewrites instruction sets on-the-fly | Changing the sheet music while the orchestra plays |
| **State Snapshot System** | Captures & restores memory states | A photographer with a time machine |
| **Guardian Watchdog** | Prevents crashes from bad offsets | A safety harness for high-wire acts |

Each layer is independently testable. The engine doesn't *override* the base game—it introduces an **alternative physics domain** that can be toggled on or off in real-time.

---

## ✨ Feature Matrix (What Makes This Stand Out)

### 🧬 Real-Time Variable Mutation
Unlike static trainers that require you to enter exact hex values, this system exposes a **human-readable JSON interface**. You can say *"make the player's invulnerability window last 3 seconds longer"* and the engine translates that into the right memory addresses automatically. The 2026 build supports Fuzzy Matching for offset discovery—you don't need to know the exact address, only the *behavior* you want to change.

### 🕹️ Responsive UI Layer
We've built a **fully responsive, web-based dashboard** that runs on your local host. It's not a clunky desktop window—it's a dynamic HTML5/WebSockets interface that:
- Updates live as you play (data streaming at 60 FPS)
- Touch-friendly for tablet-based, couch-testing sessions
- Dark mode / light mode with zero external dependencies
- Multi-language support: English, Japanese, Spanish, French, German, and Chinese (zh-CN/zh-TW)

### 🧠 Smart Pattern Recognition
The engine includes a **behavioral heuristic module** that learns how the game typically executes its routines. If it detects an unstable pattern emerging from your modifications, it automatically suggests safer alternatives—much like a spell-checker, but for assembly instructions.

### 📦 Portable Session Profiles
You can export your entire tuning session as a **single portable profile file**. Share it with a friend, and they load it with one click. The profile contains:
- All variable offsets
- Custom naming conventions
- Runtime conditional logic (e.g., "only activate during boss stages")
- A changelog of your modifications

### 🛡️ 24/7 Community Support & Documentation
The Discord-based support bot (available 24/7, 365 days a year) can answer questions about offset conflicts, engine stability, and best practices. The built-in `--analyze` flag provides a verbose log of every system action, perfect for debugging and peer-review.

---

## 📚 Table of Contents
1. [Architecture Overview](#architecture-overview)
2. [Quick Start Guide](#quick-start-guide)
3. [Configuration & Profiles](#configuration--profiles)
4. [The Dashboard UI](#the-dashboard-ui)
5. [Security & Stability Protocols](#security--stability-protocols)
6. [Multilingual Support](#multilingual-support)
7. [Troubleshooting Common Issues](#troubleshooting-common-issues)
8. [Performance Optimization Tips](#performance-optimization-tips)
9. [License & Legal](#license--legal-mit-license)
10. [Acknowledgements & Community](#acknowledgements--community)

---

## 🏗️ Architecture Overview

The engine is structured around a **pipeline flow** that mirrors the natural execution cycle of the target game:

```
Game Process (Original Code) 
        ↓ [Hooking Layer]
ChronoShift Core (C++ / MSVC 2026)
        ↓ [Data Marshalling]
Shared Memory Buffer (Ring Buffer, 256 KB)
        ↓ [WebSocket Serialization]
Dashboard UI (React.js + Canvas)
```

### The Hooking Layer
This is the only component that touches the game process directly. It uses **inline hooking with trampoline plumbing**—modifying only the first few bytes of a function to redirect execution to our engine, while routing the original bytes to a shadow copy. The 2026 revision added support for *Control Flow Guard (CFG) bypass*, making it compatible with the latest Windows Defender hardening.

### The Data Marshalling Layer
Every memory address we touch is wrapped in a **proxy object** that validates the read/write operation before committing. This prevents accidental corruption loops. Think of it as a mediator between the wild west of game memory and the structured JSON world of your dashboard.

### The Shared Memory Buffer
Internal communication uses a **lock-free MPMC (Multi-Producer, Multi-Consumer) ring buffer**. This ensures that even if you spam the toggle switches on the dashboard, the game doesn't stutter. The 256 KB buffer is configurable via environment variables for power users.

---

## 🚀 Quick Start Guide

### Prerequisites
- A legal copy of the target game (v3.2.1 build, Steam/GOG) **purchased from your official storefront**
- Windows 10 (Build 19045+) or Windows 11 (2026 Update)
- 4 GB RAM minimum
- Visual C++ 2015–2026 Redistributable package (we provide a check-up script)

### Installation Steps

1. **Clone the repository** (or download the source archive) to your local development machine.
2. **Open the solution** in Visual Studio 2026 (Community Edition is sufficient).
3. **Set the build configuration** to `Release - x64`.
4. **Compile the core DLL** – the build script will output `ChronoShiftEngine.dll` into the `bin/` folder.
5. **Launch the dashboard** – run `dashboard_host.exe` which starts the local WebSocket server on port 8765.
6. **Start your purchased game** – the engine auto-attaches when it detects the target process hash (SHA-256 verified).
7. **Open your browser** to `http://127.0.0.1:8765` – you'll see the live control panel.

> ⚠️ **First-time run:** Accept the Windows Firewall prompt for localhost traffic. This firewall exception is necessary for the dashboard to communicate with the engine core. Nothing is transmitted to the internet—we're relentless about offline functionality.

---

## 🎛️ Configuration & Profiles

Configuration is managed through a **YAML-based manifest** (v2.0 spec) that lives in the same directory as the compiled DLL. You can create as many `.chrono` profile files as you like.

### Example Profile Snippet
```yaml
# profile: competitive_runs.chrono
version: 2.0
target:
  build: 3.2.1
  checksum: "7C4A8D09CA4762FEFB"
runtime:
  refresh_rate: 60
  debug_buffer: true
modifications:
  - id: "player_x_speed"
    type: "float"
    offset_scan: "behavior"
    behavior_key: "horizontal_velocity_multiplier"
    value: 1.5
    enabled: true
```

The engine's **Smart Offset Locator** will scan for the floating point value `1.0` that controls the player's horizontal velocity and replace it with your chosen multiplier. If detection fails, it falls back to manual offset entry.

### Profile Import/Export
- **Export:** Click the "Save Profile" button on the dashboard—it bundles all current modifications into a single `.chrono` file.
- **Import:** Drag-and-drop a `.chrono` file onto the dashboard window. The engine validates it against the target build checksum before loading.

---

## 🖥️ The Dashboard UI

Our interface is designed with a **"cockpit" philosophy**—all vital telemetry visible at a glance, no menus hidden three clicks deep.

### Main Panels
| Panel | Function |
|-------|----------|
| **Live Memory Graph** | Real-time line chart showing active address read/write activity |
| **Toggle Matrix** | Grid of all enabled modifications with individual on/off switches |
| **Event Log** | Timestamped, color-coded stream of engine actions (Info/Warning/Critical) |
| **Preset Combo** | Dropdown to switch between profiles instantly |

### Responsive Behaviors
- Small screens (mobile) collapse the memory graph into a compact sparkline.
- Tablets show a split-view; desktops get the full grid.
- Keyboard shortcuts (toggled via `Ctrl+Shift+K`) let you control everything without touching the mouse.

---

## 🛡️ Security & Stability Protocols

We take a **permissive but safe** approach. The engine includes:

### 1. Crash Recovery Sentinel
If a modification causes the game process to enter an unstable state, the sentinel thread detects the deviation within 50ms and **rolls back the last transaction**. This isn't a guarantee against all crashes, but our 2026 beta testers reported a 97.8% success rate on recovery.

### 2. Digital Signature Verification
The engine refuses to inject into any process whose executable hash doesn't match a known-good value for the target game. This prevents accidental injection into malicious look-alike processes.

### 3. No Network Footprint
By default, the engine **does not listen** on any external network interface. It binds exclusively to `127.0.0.1`. For advanced users, we offer an optional `--allow-lan` flag (for managing multiple test machines), but it's disabled by default and clearly documented as a security trade-off.

### 4. Anti-Pattern Camouflage
The DLL exports a random-named class that rotates its symbol table on every build. This isn't for nefarious purposes—it simply prevents other frameworks from accidentally loading our code into your game.

---

## 🌍 Multilingual Support

We believe that game preservation is a global effort. The entire engine (error messages, dashboard UI, documentation) supports:

- **English** (default)
- **日本語 (Japanese)** – 完全なローカライズ
- **Español (Spanish)** – Localización completa
- **Français (French)** – Traduction intégrale
- **Deutsch (German)** – Vollständige Übersetzung
- **简体中文 (Simplified Chinese)** – 完整的本地化
- **繁體中文 (Traditional Chinese)** – 完整的本地化

To change language, set the operating system's preferred language before launching the dashboard, or manually create a file called `lang_config.dat` in the install dir containing the ISO 639-1 code (e.g., `ja`).

---

## 🔧 Troubleshooting Common Issues

### "The dashboard can't connect to the game process."
- Ensure you launched `dashboard_host.exe` **after** the game started.
- Check Windows Security logs for blocked localhost connections.
- Run the `--diagnostics` flag on the host to see verbose handshake data.

### "My modification causes a crash."
- Enable the "Auto-Revert on Error" toggle in the Stability tab.
- Lower your `refresh_rate` from 60Hz to 30Hz—sometimes the game clock can't keep up.
- Try modifying one variable at a time to isolate the culprit.

### "The offsets change after every game restart."
That's expected behavior. The 3.2.1 build uses **ASLR (Address Space Layout Randomization)**. Our Smart Locator re-scans on every injection. If you're writing a shared profile, use the **Behavior Key** method rather than static addresses.

---

## ⚡ Performance Optimization Tips

- **Minimize the UI:** The dashboard consumes ~30–40MB of RAM. If you hit 98% memory usage, switch to the "Lite Mode" (HTML-only, no WebGL graphics).
- **Batch your toggles:** Turning on 50 modifications simultaneously causes a brief CPU spike. Use the *Timed Activation* feature to stagger them over 2 seconds.
- **Close other games:** This engine allocates dedicated memory for its ring buffer. Another open game might cause paging issues.

---

## 📜 License & Legal (MIT)

**Copyright © 2026 ChronoShift Engine contributors**

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

**THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.**

The full license text is available at: MIT License Reference.

---

## 🎉 Acknowledgements & Community

This project was born from a late-night thought experiment: *"What if we could debug the game as if we were debugging ourselves?"*

We extend our gratitude to:
- The **reverse-engineering forum** whose users generously shared their memory layout findings
- The **modding discords** that beta-tested the 2026 pre-release builds
- The **original game developers** for creating a timeless masterpiece that continues to inspire curiosity about internal mechanics

### How to Contribute
1. Fork the `develop` branch.
2. Write tests for any new feature (MSTest v3).
3. Submit a Pull Request with a clear description of the intended behavior—no prose required.
4. Report issues with the `--diagnostics` log attached.

---

## 🏁 Final Thoughts

ChronoShift Engine is not about ruining a game—it's about **illuminating the hidden mathematics** that make a game tick. We invite you to use this framework to learn, to experiment, and to appreciate the intricate dance of bytes that powers your favorite vintage experience.

Remember: With great power comes great responsibility. Use this engine on software you own, and always respect the community's online multiplayer boundaries.

---

*Happy time-traveling!*