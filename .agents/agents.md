# Mivio Desktop Agents Configuration

## Project Overview
Mivio for Desktop (Windows & Linux) is a premium, high-performance media management and playback application tailored for desktop environments. Uses a hybrid architecture with Electron UI and Rust native bridges for performance-critical operations.

## Key Technologies
- Frontend (UI): Electron (with React/Vue/Svelte) for responsive user interface
- Native Bridges: Rust native bridges (NAPI-RS / Neon) for memory safety and native execution speeds
- Video Engine: Native mpv / VLC backend for hardware-accelerated decoding, 4K HDR playback, and perfect audio passthrough
- Language: JavaScript/TypeScript for Electron frontend, Rust for native bridges
- Build System: npm + Cargo for Rust compilation

## Project Structure
```
mivio-desktop/
├── native-bridge/          # Rust native bridges (NAPI-RS / Neon)
├── public/                 # Static assets
├── src/                    # Electron frontend source code
├── CONTRIBUTING.md         # Contribution guidelines
├── LICENSE                 # License file
├── README.md               # Project documentation
└── SECURITY.md             # Security policy
```

## Development Guidelines
- Target branch for PRs: `beta` (main is production-ready)
- Prerequisites: Node.js (v18+), Rust (Cargo), C/C++ Build Tools, libmpv or libvlc development headers
- Setup process:
  1. Clone repository
  2. Run `npm install` to install Node.js dependencies
  3. Run `npm run build:native` to compile Rust native bridges
  4. Run `npm run dev` to launch development mode with hot-reloading

## Platform Features
- Local Multi-Account: Each user saves progress independently
- Local File Reading & Writing: Full filesystem access including metadata and artwork writing
- Home Server Client: Connects to Plex, Jellyfin, and Emby
- Metadata Management: Sort and display metadata locally or from server
- Native Player: Embedded mpv / VLC backend for flawless 4K HDR playback and subtitle rendering

## Agent Instructions
When working on this project:
1. Understand the hybrid architecture (Electron UI + Rust bridges + native video engine)
2. For UI changes: Work with Electron/frontend technologies (HTML/CSS/JS or framework of choice)
3. For performance-critical operations: Modify Rust native bridges in the native-bridge/ directory
4. For video playback changes: Work with the mpv/VLC backend integration
5. Ensure proper error handling between Electron frontend and Rust bridges
6. Test native bridge functionality thoroughly as it involves unsafe Rust code
7. Follow existing patterns for inter-process communication between Electron and Rust
8. Keep security in mind when handling file system operations through native bridges
9. Update documentation when changing public APIs or significant functionality