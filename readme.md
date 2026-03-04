# tpad

A minimal notepad server. Visit it in your browser, get a pad, start typing. Saves automatically.

```
http://localhost:3000  →  redirects to /:id  →  your pad
```

---

## Features

- **Zero dependencies** — single Rust source file, compiled on the fly with `rustc`
- **Auto-save** — debounced saves on every keystroke, or `Ctrl+S` / `Cmd+S`
- **Shareable pads** — each pad has a unique ID in the URL
- **Persistent** — pads live on disk, survive restarts
- **Systemd managed** — runs as a background service after install

---

## Install

```sh
git clone https://github.com/toonalfrink/tpad /tmp/tpad && /tmp/tpad/tpad install
```

This will:
1. Copy the project to `/srv/tpad`
2. Create the data directory at `/var/lib/tpad`
3. Register and start a systemd service

Then open `http://localhost:3000` in your browser.

---

## Usage

| Command | Description |
|---|---|
| `tpad install` | Build, install, and start the systemd service |
| `tpad run` | Compile and run locally (no systemd) |
| `tpad uninstall` | Stop the service and delete all data |

---

## Configuration

| Variable | Default | Description |
|---|---|---|
| `PORT` | `3000` | Port to listen on (auto-increments if taken) |
| `TPAD_DATA_DIR` | `~/.local/share/tpad` | Where pads are stored |

---

## Uninstall

```sh
./tpad uninstall
```

> **Warning:** this deletes all pad data at `/var/lib/tpad`.

---

## Requirements

- [Rust](https://rustup.rs) (`rustc` in PATH)
- [Nushell](https://www.nushell.sh) (`nu` in PATH) — for the install script
- `systemd` — for service management
