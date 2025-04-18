<div align="center">

![HyprUpld](Banner.png)

![Arch](https://img.shields.io/badge/Arch%20Linux-1793D1?logo=arch-linux&logoColor=fff&style=for-the-badge)
![Bash Script](https://img.shields.io/badge/bash_script-%23121011.svg?style=for-the-badge&logo=gnu-bash&logoColor=white)
![Neovim](https://img.shields.io/badge/NeoVim-%2357A143.svg?&style=for-the-badge&logo=neovim&logoColor=white)

**A versatile screenshot and file upload utility for Linux and MacOS with multi-platform support**

[![License: GPL-2.0](https://img.shields.io/badge/License-GPL%20v2-blue.svg)](https://github.com/PhoenixAceVFX/hyprupld/blob/main/LICENSE)
[![Latest Release](https://img.shields.io/github/v/release/PhoenixAceVFX/hyprupld)](https://github.com/PhoenixAceVFX/hyprupld/releases)

</div>

---

## Table of Contents

- [Quick Start](#quick-start)
- [Features](#features)
  - [Upload Services](#upload-services)
  - [Command Line Options](#command-line-options)
- [Desktop Environment Support](#desktop-environment-support)
- [Package Manager Support](#package-manager-support)
- [About](#about)
- [Resources](#resources)
- [License](#license)

---

## Quick Start

To install HyprUpld, execute the following one-line command in your terminal:
### Linux
```bash
bash -c "$(curl -fsSL https://raw.githubusercontent.com/PhoenixAceVFX/hyprupld/main/install.sh)"
```
### MacOS
```bash
bash -c "$(curl -fsSL https://raw.githubusercontent.com/PhoenixAceVFX/hyprupld/main/macos_install.sh)"
```

> **Note:** If downloading manually from the [releases page](https://github.com/PhoenixAceVFX/hyprupld/releases), remember to make the script executable with `chmod +x` before creating keybindings. This step is not needed when using the one-line installer.

---

## Features

### Upload Services

HyprUpld supports uploading to multiple services:

- [e-z.host](https://e-z.host)
- [fakecri.me](https://fakecri.me)
- [guns.lol](https://guns.lol)
- [nest.rip](https://nest.rip)
- [pixelvault.co](https://pixelvault.co)
- [imgur](https://imgur.com)
- **Zipline instances** (self-hosted image hosting)
- **XBackbone instances** (self-hosted image hosting)

### Command Line Options

HyprUpld offers various command-line options for flexibility:

```bash
hyprupld - Screenshot and Upload Utility

Usage: hyprupld [OPTIONS]

Options:
  -h, --help       Show this help message
  -debug           Enable Verbose Debug Logs
  -strict          Enable Strict Error Handling
  -reset           Reset all settings and start fresh
  -s, --save       Save screenshots to a specified directory
  -update          Update hyprupld to the latest version
  -mute            Mute sound feedback
  -silent          Silent mode (no sound or notification)
  -kill            Kill all running instances of hyprupld
  -uwsm            Enable UWSM compatibility mode for Hyprland

Screenshot Services:
  -guns            Use guns.lol
  -ez              Use e-z.host
  -fakecrime       Use fakecri.me
  -nest            Use nest.rip
  -pixelvault      Use pixelvault.co
  -zipline         Use a custom Zipline instance
  -xbackbone       Use a custom xBackBone instance
  -imgur           Use imgur.com

Environment Variables:
  HYPRUPLD_CONFIG  Override default config directory
  HYPRUPLD_DEBUG   Enable debug output when set to 1

Examples:
  hyprupld -guns              # Take screenshot and upload to guns.lol
  hyprupld                    # Take screenshot and copy to clipboard
  hyprupld -zipline https://example.com myauthkey  # Use custom Zipline instance
  hyprupld -xbackbone https://example.com token  # Use custom xBackBone instance
```

> **Note:** If no service is selected, the file will be copied to the clipboard.

### Local Screenshot Storage

When using the `-s` or `--save` option, HyprUpld will:
- Prompt for a base directory on first use
- Create a `hyprupld` folder in the chosen location
- Automatically organize screenshots by month (e.g., `march-2024`, `april-2024`)
- Save files with format: `hyprupld-YYYYMMDD-HHMMSS.png`

Example directory structure:

### Additional Features

- Interactive screenshot tool selection for each desktop environment
- Persistent configuration storage for settings and preferences
- Automatic package manager detection and fallback
- GUI dialogs for user interactions
- Debug mode for troubleshooting (`-debug`)
- **Mute and Silent Modes**: Use `-mute` to disable sound feedback or `-silent` to disable both sound and notifications.

### Configuration

HyprUpld stores its configuration in `~/.config/hyprupld/`:
- Authentication keys for upload services
- Preferred screenshot tools per desktop environment
- Screenshot save location preferences
- Package manager information

Use `-reset` to clear all saved settings and start fresh.

### Environment Variables

- `HYPRUPLD_CONFIG`: Override default config directory location
- `HYPRUPLD_DEBUG`: Enable debug output when set to 1
- Automatically detects `DISPLAY` and `WAYLAND_DISPLAY` for proper display server support

---

## Platform and Desktop Environment Support

### Operating Systems
- Linux (Primary support)
- macOS (Experimental)
  - Built-in screencapture tool
  - Third-party tools: CleanShot X, Xsnapper

### Desktop Environments
HyprUpld works seamlessly with various Linux desktop environments:

- KDE Plasma
- Hyprland
- GNOME
- XFCE
- i3
- Deepin
- Cinnamon
- Openbox
- MATE
- Sway
- Cosmic

---

## Package Manager Support

Installation is supported on systems using:

- Pacman (Arch)
- Apt (Debian/Ubuntu)
- DNF (Fedora)
- Nix-Env (NixOS)
- Emerge (Gentoo)
- Zypper (openSUSE)
- XBPS (Void)
- AUR Helpers (Yay/Paru)

---

## About

HyprUpld is an all-in-one screenshot tool designed to streamline the process of capturing and uploading screenshots across Linux and macOS (experimental) platforms.

For more information, visit the [official website](https://hyprupld.space).

---

## Resources

- [Readme](https://github.com/PhoenixAceVFX/hyprupld/blob/main/README.md)
- [Releases](https://github.com/PhoenixAceVFX/hyprupld/releases)

---

## AppImage Support

- Pre-built AppImages are available in the [Releases](../../releases) section
- Can be compiled using the included `compile.sh` script
- Automatic builds generated from the latest commit
- Functionally identical to the standard scripts

## Installation

The `install.sh` script:
- Places executables in `/usr/local/bin`
- Sets appropriate permissions
- Verifies PATH configuration
- Handles dependency installation

To install:
1. Clone the repository or download the release package
2. Run `bash compile.sh` to build from source
3. Run `bash install_scripts.sh`

## Dependencies

### Core Tools
* [curl](https://github.com/curl/curl) - Command line tool for transferring data
* [xclip](https://github.com/astrand/xclip) - Command line interface to X selections (clipboard)
* [wl-clipboard](https://github.com/bugaevc/wl-clipboard) - Command line interface to Wayland selections (Clipboard)
* [fyi](https://github.com/Macchina-CLI/fyi) - Minimal desktop notifications
* [zenity](https://gitlab.gnome.org/GNOME/zenity) - Display graphical dialog boxes from shell scripts
* [python](https://github.com/python) - Replacing JQ as a JSON Processor
* [sips](https://developer.apple.com/documentation/sips) - Command line tool for macOS
* [osascript](https://developer.apple.com/documentation/appscript) - Command line tool for macOS
* [zip](https://github.com/infozip/zip) - Command line tool for creating zip archives

### Screenshot Tools
* [grimblast](https://github.com/hyprwm/contrib) - For Sway and i3
* [hyprshot](https://github.com/your-repo/hyprshot) - For Hyprland
* [spectacle](https://github.com/KDE/spectacle) - For KDE Plasma
* [gnome-screenshot](https://gitlab.gnome.org/GNOME/gnome-screenshot) - For GNOME
* [xfce4-screenshooter](https://docs.xfce.org/apps/xfce4-screenshooter/start) - For XFCE
* [scrot](https://github.com/resurrecting-open-source-projects/scrot) - For i3, Openbox, and other minimal WMs
* [deepin-screenshot](https://github.com/linuxdeepin/deepin-screenshot) - For Deepin
* [mate-screenshot](https://github.com/mate-desktop/mate-utils) - For MATE
* [grim](https://github.com/emersion/grim) - For Sway
* [screencapture](https://developer.apple.com/documentation/appkit/screencapture) - For macOS
* [cleanshot](https://cleanshot.com) - For macOS
* [xsnapper](https://xsnapper.com) - For macOS

## Issues and Support
Please use the [Issues](../../issues) section to:
- Report bugs
- Request new features
- Request additional upload service support

---

## License

This project is licensed under the [GPL-2.0 License](https://github.com/PhoenixAceVFX/hyprupld/blob/main/LICENSE).

---

*For any issues or contributions, please visit the [GitHub repository](https://github.com/PhoenixAceVFX/hyprupld).*

--- 

Created by PhoenixAceVFX
