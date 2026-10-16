# wallpaper-picker ✦

A lightweight **Rust terminal UI** for previewing wallpapers and applying matching desktop colours with Matugen.

## Features

- Browse image files in a terminal using arrow keys or **j/k**.
- Preview the currently selected image in supported terminals.
- Apply wallpaper through **awww**, **hyprpaper**, **feh**, **swaybg**, or **nitrogen**.
- Optionally call **Matugen** to generate colours from the selected wallpaper.
- Configure your wallpaper directory and backend using a small TOML file.

> Early-stage personal project. A screenshot or terminal recording is coming soon.

## Requirements

- [Rust and Cargo](https://rustup.rs/) to build from source.
- A supported wallpaper setter installed and accessible on your `PATH`.
- [Matugen](https://github.com/InioX/matugen) if you enable dynamic colour theming.
- An image-capable terminal for image previews (fallback behaviour depends on your terminal).

## Install from source

```bash
git clone https://github.com/lilacruntime/wallpaper-picker.git
cd wallpaper-picker
cargo build --release
cargo install --path .
```

The installed executable is `wallpaper-picker`. Run:

```bash
wallpaper-picker
```

This is an independent source installation. Pre-existing AUR packages may refer to different repositories or versions.

## Configure

Create `~/.config/wallpaper-picker/config.toml`:

```toml
wallpaper_dir = "~/Pictures/wallpapers"
wallpaper_setter = "awww"
matugen_enabled = true
```

Replace `awww` with your installed wallpaper backend if needed. Disable Matugen by setting `matugen_enabled = false`.

## Keys

| Key | Action |
| --- | --- |
| ↑ / ↓ or j / k | Select previous or next wallpaper |
| Enter | Set the selected wallpaper and exit |
| q or Esc | Quit |

## Implementation

Built with **Rust**, **Ratatui**, **Crossterm** and **ratatui-image**. Source is split into modules for configuration, application state, UI rendering and wallpaper backend execution.

Project is under active improvement; bug reports and suggestions are welcome.
