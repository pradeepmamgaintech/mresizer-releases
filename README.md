# MResizer

[](https://github.com/pradeepmamgaintech/mresizer-releases/releases)
[](https://github.com/pradeepmamgaintech/mresizer-releases)
[](LICENSE)

MResizer is a lightweight, tray-based desktop utility designed for developers, designers, tutorial creators, and documentation writers. It allows you to quickly resize and reposition external application windows to exact preset or custom dimensions.

---

## 🚀 Key Features

- **Window Resizing & Repositioning**: Target any running window and resize it to exact dimensions, with support for outer-window bounds or client-area borders.
- **System Tray Integration**: Quietly runs in your system tray. Quickly access presets, profiles, and configurations from the right-click menu.
- **Click-to-Select Overlay Mode**: Hit a global shortcut, hover over any window to see its resizability status color-coded, and click to resize it instantly.
- **Workspace Profiles**: Group your presets and customize your layout configurations (e.g., *Tutorial Recording*, *Screenshot Prep*, *Development*) to show only relevant preset groups.
- **Per-App Automation Rules**: Define default presets, resize modes, and positioning overrides for specific processes or class names.
- **DPI & Multi-Monitor Polish**: All coordinates and bounds are calculated using logical pixels mapped to target monitor DPI contexts.
- **Portable Mode**: Redirect settings and preset configurations to a local `data` directory inside the executable's folder by placing a `portable.txt` file next to the binary.
- **Command Line Interface (CLI)**: Control resizing, list presets, or import/export configurations programmatically.
- **Single Instance Enforcement**: Runs a background Named Pipe IPC channel to forward commands and focus settings when launching duplicate instances.

---

## 📦 Downloads

Grab the latest version of MResizer from the [Releases page](https://github.com/pradeepmamgaintech/mresizer-releases/releases):

- **[MResizer-win-Setup.exe](https://github.com/pradeepmamgaintech/mresizer-releases/releases/latest/download/MResizer-win-Setup.exe)**: Standard Windows installer (sets up start menu shortcuts and auto-update support).

---

## 🛠️ CLI Usage

MResizer includes a headless command-line interface. If the tray app is already running, CLI commands are forwarded via a Named Pipe channel to prevent duplicate instances.

### Available Commands

| Command | Arguments | Description |
| --- | --- | --- |
| `help` | None | Displays help text. |
| `list` | None | Lists all built-in and custom presets. |
| `resize` | `<preset_id \\| preset_name>` | Resizes the active foreground window to a preset. |
| `resize-custom` | `<w> <h> [mode] [position]` | Resizes the active window to custom dimensions. |
| `restore` / `undo` | None | Restores the last resized window to its previous size. |
| `import` | `<file_path>` | Imports custom presets from a JSON file. |
| `export` | `<file_path>` | Exports all custom presets to a JSON file. |

### CLI Examples

- **Show Help Menu**:
  
  ```cmd
  MResizer.exe help
  ```
  
- **List Presets**:
  
  ```cmd
  MResizer.exe list
  ```
  
- **Resize Active Window to 1080p (16:9)**:
  
  ```cmd
  MResizer.exe resize "1920 x 1080"
  ```
  
- **Custom Client-Area Resize (Centered)**:
  
  ```cmd
  MResizer.exe resize-custom 1280 720 ClientArea CenterOnMonitor
  ```
  
- **Undo Last Resize Action**:
  
  ```cmd
  MResizer.exe restore
  ```
  

---

## ⚙️ Keyboard Shortcuts (Defaults)

- **Ctrl + Alt + R**: Enter Click-to-Select Window mode.
- **Ctrl + Alt + A**: Resize active foreground window to last selected preset.
- **Escape**: Cancel Click-to-Select mode overlay.

*You can fully customize global shortcuts and assign custom keys to individual presets via the **Hotkeys** settings tab.*

---

## 📜 License

Distributed under the MIT License. See [LICENSE](LICENSE) for more information.
