# 🖥️ FileBrowser Quantum Desktop OS & Minimal Themes

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![FileBrowser Quantum](https://img.shields.io/badge/FileBrowser-Quantum%20v2.0%2B-00d2ff.svg)](https://filebrowserquantum.com/)

A curated suite of native OS-inspired and minimalist themes for **[FileBrowser Quantum](https://filebrowserquantum.com/)**, designed to mimic the simplicity and ergonomics of native desktop file managers (Apple macOS Finder and Windows 11 File Explorer).

---

## 🎨 Themes Included

| Theme | File | Style & Features |
| :--- | :--- | :--- |
| **🖥️ OS Minimal (B&W)** | `os-minimal.css` | **Flagship OS Theme**. Super simple high-contrast black/white monochrome interface. Sidebar shows **shortcuts only**. User avatar in the top right; Settings tucked into a floating bottom-right button. |
| **🍎 macOS Finder** | `macos-finder.css` | Native macOS Finder aesthetic with SF Pro typography, authentic Apple system grays, macOS selection blue (`#0066cc`), streamlined Favorites sidebar, top-right profile avatar, and bottom-right settings pill. |
| **🪟 Windows 11 Explorer** | `windows-explorer.css` | Windows 11 Fluent design with Segoe UI typography, subtle 4px borders, clean Navigation Pane (shortcuts only), top-right user icon, and floating settings button. |
| **🌌 Quantum Aurora** | `aurora.css` | Modern glassmorphism dark theme with cyan & violet aurora accents and frosted panels. |
| **🖤 Quantum Obsidian** | `obsidian.css` | Pure OLED true-black edition with emerald accents for high contrast and OLED displays. |
| **☕ Catppuccin Mocha** | `catppuccin-mocha.css` | Soothing pastel theme based on the official Catppuccin Mocha palette. |

---

## 🎯 Key Design Features

- **Desktop OS Experience**: Native titlebar toolbar, system typography stacks, and clean border geometry.
- **Pure Black & White**: Super simple monochrome styling (light mode = crisp white & charcoal; dark mode = true black & clean white).
- **Shortcuts-Only Sidebar**: All profile banners, quick toggle buttons, action pills, and footer clutter are completely hidden from the sidebar, leaving only your pinned shortcuts, favorites, and directory locations.
- **Top-Right User Icon**: A minimal user avatar circle in the top right corner of the window titlebar for instant profile access without cluttering the sidebar.
- **Bottom-Right Settings Button**: The settings panel is cleanly extracted out of the sidebar and placed as a floating, minimal button in the bottom-right corner of the window.

---

## 🚀 Quick Start & Installation

### 1. Download or Clone

Clone this repository into your FileBrowser themes folder:

```bash
git clone https://github.com/eliotstocker/filebrowser-quantum-themes.git /path/to/themes
```

Or copy the `.css` files into a `themes` folder alongside your `config.yaml`.

---

### 2. Configure `config.yaml`

Add the custom themes to your `config.yaml`:

```yaml
frontend:
  styling:
    customThemes:
      # Automatically applied to all users
      default:
        description: "OS Minimal (Default)"
        css: "/themes/os-minimal.css"
      os-minimal:
        description: "OS Minimal (Black & White)"
        css: "/themes/os-minimal.css"
      macos-finder:
        description: "macOS Finder"
        css: "/themes/macos-finder.css"
      windows-explorer:
        description: "Windows 11 Explorer"
        css: "/themes/windows-explorer.css"
      aurora:
        description: "Quantum Aurora (Glass)"
        css: "/themes/aurora.css"
      obsidian:
        description: "Quantum Obsidian (OLED)"
        css: "/themes/obsidian.css"
      catppuccin-mocha:
        description: "Catppuccin Mocha"
        css: "/themes/catppuccin-mocha.css"
```

---

### 3. Docker Compose Mount

If running FileBrowser Quantum with Docker, mount the `themes` directory:

```yaml
services:
  filebrowser:
    image: gtstef/filebrowser:latest
    container_name: filebrowser-quantum
    ports:
      - "8080:8080"
    volumes:
      - ./data:/srv
      - ./config.yaml:/etc/filebrowser/config.yaml
      - ./filebrowser.db:/etc/filebrowser/filebrowser.db
      - ./themes:/themes:ro
    restart: unless-stopped
```

---

### 4. Switch Themes in the UI

1. Open FileBrowser Quantum in your browser.
2. Click the **gear icon button** in the bottom-right corner (or the **user avatar** in the top-right corner).
3. Select your theme from the **Theme** dropdown.
4. Changes apply immediately and persist across sessions!

---

## 📄 License

Distributed under the [MIT License](LICENSE).
Contributions and issues are welcome!
