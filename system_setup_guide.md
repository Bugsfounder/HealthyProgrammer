# System Setup (Linux Friendly)

## 1 Install Rust

Run this in terminal:

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

Reload shell:

```bash
source ~/.cargo/env
```

Check version:

```bash
rustc --version
```

healthyProgrammer

# 2 Install Node (for Tauri frontend)

Tauri needs Node only for building UI.

Install Node LTS:

```bash
sudo apt install nodejs npm
```

Or better:

```bash
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt install -y nodejs
```

Check version:

```bash
node -v
npm -v
```

healthyProgrammer

# 3 Install Tauri CLI

```bash
cargo install tauri-cli
```

healthyProgrammer

# 4 Install Linux Dependencies (VERY IMPORTANT)

For Ubuntu/Debian:

```bash
sudo apt install \
  libwebkit2gtk-4.1-dev \
  build-essential \
  curl \
  wget \
  libssl-dev \
  libgtk-3-dev \
  libayatana-appindicator3-dev \
  librsvg2-dev

```

These are required for:

- System tray
- Notifications
- Webview
- Packaging

healthyProgrammer

# 5 Create Your Project

In your folder:

```bash
cargo create-tauri-app breaktimer
```

Choose:

- Template: Vanilla
- Package manager: npm or yarn
- Frontend language: JS (simple)

Then:

```bash
cd breaktimer
npm install
```

healthyProgrammer

# 6 Run the App in Dev Mode

```bash
cargo tauri dev
```

This opens your first desktop window.

healthyProgrammer

# 7 Build the App

Linux AppImage:

```bash
cargo tauri build
```

Output:

```
./src-tauri/target/release/bundle/appimage/breaktimer.AppImage
```

Double-click to run.
