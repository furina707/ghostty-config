# Ghostty Configuration

Personal configuration for [Ghostty](https://ghostty.org/) terminal emulator, optimized for **Arch Linux**, **Niri** (Wayland) tiling window manager, and large-scale compilation/development workflows (such as AOSP).

## ✨ Features

- **Theme & Appearance**:
  - Theme: `Catppuccin Mocha` (high readability, easy on the eyes)
  - Translucency: `0.95` opacity with frosted glass aesthetic
  - Clean UI: Disabled window decorations & GTK titlebars (perfect for tiling compositors like Niri)
  - Cursor: Smooth breathing block cursor (`cursor-style = block`, `cursor-style-blink = true`)
- **Clipboard & Mouse Interactions**:
  - **`Ctrl + C`**: Smart copy (copies text when selected; sends standard `SIGINT` interrupt when nothing is selected)
  - **`Ctrl + V`**: Instant paste from clipboard
  - Unbound legacy `Ctrl + Shift + C` & `Ctrl + Shift + V` for clean keymapping
  - **Right Click**: Smart copy-or-paste (copies selected text to clipboard; pastes clipboard content when no text is selected)
  - Automatically clears highlight after copy for seamless subsequent paste
  - Disabled annoying automatic copy on text selection (`copy-on-select = false`)
  - Disabled unsafe paste confirmation dialog (`clipboard-paste-protection = false`) for seamless pasting without confirmation prompts
- **Productivity & Splits**:
  - Scrollback buffer expanded to **100,000 lines** (protects long compilation/debug logs from truncation)
  - `Ctrl + Shift + D`: Split right
  - `Ctrl + Shift + S`: Split down
  - `Ctrl + Shift + W`: Close split surface
  - `Ctrl + Alt + Arrow Keys`: Focus navigation between splits
  - `Ctrl + T`: New tab
  - `Ctrl + Shift + N`: New window

## 🚀 Installation

```bash
mkdir -p ~/.config/ghostty
curl -fsSL https://raw.githubusercontent.com/furina707/ghostty-config/main/config -o ~/.config/ghostty/config
```

Or clone the repository:

```bash
git clone https://github.com/furina707/ghostty-config.git
cp ghostty-config/config ~/.config/ghostty/config
```

### Reload Configuration

To reload in an active Ghostty session:
- Press `Ctrl + Shift + ,` (comma)
- Or send a signal:
  ```bash
  kill -SIGUSR2 $(pgrep ghostty)
  ```
