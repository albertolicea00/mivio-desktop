# 🍿 Mivio for Desktop (Windows & Linux)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)
[![Platform Compatibility](https://img.shields.io/badge/Platforms-Windows%20%7C%20Linux-brightgreen.svg?style=flat-square)](#platform-specific-goals)
[![Electron](https://img.shields.io/badge/UI-Electron-47848F.svg?style=flat-square&logo=electron)](https://electronjs.org/)
[![Rust](https://img.shields.io/badge/Native_Bridge-Rust-black.svg?style=flat-square&logo=rust)](https://www.rust-lang.org/)

**Mivio** is a premium, high-performance media management and playback application tailored for desktop environments (Windows and Linux). While `mivio-apple` natively handles macOS, this repository ensures the PC ecosystem enjoys the same elegant, fast, and feature-rich media cataloging and streaming experience.

---

## 🏗️ Architectural Blueprint

Mivio Desktop uses a highly customized hybrid architecture designed for maximum performance, bypassing the traditional limitations of web-based desktop apps:

- **Frontend (UI)**: Built on **Electron** (with React/Vue/Svelte) for a beautiful, responsive, and easily stylable user interface.
- **Native Bridges**: Performance-critical operations (like SMB network scanning, parsing, and file I/O) are handled by **Rust native bridges** (NAPI-RS / Neon), guaranteeing memory safety and native execution speeds.
- **Video Engine**: To avoid the codec limitations and performance overhead of HTML5 video, playback is handled by a native **mpv / VLC backend** embedded into the Electron window context, allowing for hardware-accelerated decoding of 4K HDR files, native subtitle rendering, and perfect audio passthrough.

---

## 🎨 Platform Features & Limitations

Mivio Desktop optimizes for mouse, keyboard, and flexible window management, delivering the full desktop experience without limitations:

- ✅ **Local Multi-Account**: Each user saves their progress independently on the same machine.
- ✅ **Local File Reading & Writing**: Full access to the file system, including writing metadata and saving artwork.
- ✅ **Home Server Client**: Fully connects to Plex, Jellyfin, and Emby.
- ✅ **Metadata Management**: Sort and display metadata locally or from the server.
- ✅ **Native Player**: Avoids HTML5 limitations by embedding a native **mpv / VLC backend** directly into Electron for flawless 4K HDR playback and subtitle rendering.

---

## 🚀 Getting Started

### Prerequisites
- Node.js (v18+)
- Rust (Cargo) for compiling the native bridges.
- C/C++ Build Tools (Visual Studio Build Tools on Windows, `build-essential` on Linux) to compile native dependencies.
- `libmpv` or `libvlc` development headers installed on your system.

### Setup and Running the Project
1. **Clone the Repository:**
   ```bash
   git clone https://github.com/albertolicea00/mivio-desktop.git
   cd mivio-desktop
   ```

2. **Install Dependencies:**
   ```bash
   npm install
   ```

3. **Build the Rust Native Bridges:**
   ```bash
   npm run build:native
   ```

4. **Run Development Mode:**
   Launch the application in development mode with hot-reloading:
   ```bash
   npm run dev
   ```

---

## 🤝 Contribution Guidelines

We use a structured branch strategy to protect stable builds while supporting active feature implementation:
- **`main`**: Production-ready release branch.
- **`beta`**: Standard development target. **Always target your PRs to `beta`!**

For detailed instructions on commit formats, coding style guidelines, and PR checks, please review [CONTRIBUTING.md](CONTRIBUTING.md).

For vulnerability reporting or security-related matters, see [SECURITY.md](SECURITY.md).

---

## 📄 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
