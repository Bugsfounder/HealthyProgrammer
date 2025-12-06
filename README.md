# HealthyProgrammer — A Modern Productivity & Break Reminder App

_A lightweight cross-platform desktop app built with Rust + Tauri._

HealthyProgrammer helps users maintain a healthy work rhythm by reminding them to take breaks at regular intervals. It’s designed to reduce eye strain, improve focus, and promote better work habits — without heavy system usage.

##  Features (Planned)

- Set total work duration
- Set break intervals & break duration
- System notifications (Linux/Windows/macOS)
- Custom alarm sound playback
- System tray support (run in background)
- Global shortcut to open/close the UI
- Beautiful modern UI (Tauri + HTML/CSS/JS)
- Cross-platform lightweight build (~5–10 MB)
- Persistent settings (work intervals saved locally)

## Tech Stack

| Layer            | Technology                                            |
| ---------------- | ----------------------------------------------------- |
| Desktop Shell    | **Tauri**                                             |
| Backend Logic    | **Rust**                                              |
| Frontend UI      | HTML • CSS • JavaScript (or Svelte/React later)       |
| Notifications    | Tauri notify plugin                                   |
| Audio Playback   | Rust crate (rodio or lofty)                           |
| Global Shortcuts | Tauri global shortcut API                             |
| Packaging        | `.AppImage` (Linux), `.exe` (Windows), `.app` (macOS) |


##  Project Structure (Proposed)

```
breaktimer/
 ├── src-tauri/
 │   ├── src/
 │   │    ├── main.rs          # Rust backend
 │   │    ├── timer.rs         # Timer engine
 │   │    ├── notifier.rs      # Notifications
 │   │    ├── audio.rs         # Alarm sound player
 │   │    └── settings.rs      # Load/save settings
 │   └── tauri.conf.json       # App configuration
 │
 ├── src/
 │   ├── index.html            # Main UI
 │   ├── app.js                # Frontend logic
 │   ├── styles.css            # Styling
 │
 ├── README.md
 └── package.json (if using JS bundler)
```

##  Core Logic (Short Summary)

### 1. **User sets:**

- Total work time (in hours)
- Break interval (in minutes)
- Break duration (in minutes)

### 2. **Timer Engine (Rust)**

- Runs in background thread
- Tracks time precisely (Rust is perfect for this)
- Sends events to frontend (start break, resume work)

### 3. **When break begins**

- Show notification
- Play alarm sound
- Pause work timer

### 4. **When break ends**

- Show “Resume Work” notification
- Restart work timer

### 5. **When total work time ends**

- Final notification
- Stop timers
- Optionally quit or reset

##  Installation (Developer Setup)

### 1️ Install Rust

```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

### 2️ Install Tauri Requirements

Linux example:

```
sudo apt install libwebkit2gtk-4.1-dev libgtk-3-dev libappindicator3-dev librsvg2-dev
```

### 3️ Create a Tauri project

```
cargo create-tauri-app breaktimer
```

### 4️ Run dev mode

```
cargo tauri dev
```

### 5️ Build final binary

```
cargo tauri build
```

## Team Work Guidelines

- Use feature branches (`feature/timer-engine`, `feature-notifications`)
- Keep Rust logic modular
- UI can be improved anytime without touching backend
- Document every function inside `src-tauri/src`
- Always test on Linux + Windows (team can divide tasks)

## Roadmap (Milestones)

### **Phase 1 — MVP**

- Basic UI
- Timer engine in Rust
- Notifications + Sound
- Settings input form

### **Phase 2 — UX Upgrade**

- System tray
- Global shortcut (Ctrl+Shift+B)
- Dark mode UI

### **Phase 3 — Production**

- Auto-updater (optional)
- AppImage packaging
- Windows installer
- Polished UI


##  Credits

Created by bugsfounder & Team
Inspired by a prototype built 2 years ago, now rebuilt with Rust for long-term quality.

Bro, if you want I can also write:

- Full **CONTRIBUTING.md**
- Coding guidelines
- UI wireframe
- First sprint tasks

Just tell me.
