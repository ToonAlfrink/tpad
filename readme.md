# tpad

A minimal notepad server. Visit it in your browser, get a pad, start typing. Saves automatically.

## Install

```sh
git clone https://github.com/toonalfrink/tpad
cd tpad && ./tpad install
```

Then open `http://localhost:3000`.

## Commands

| Command | Description |
|---|---|
| `tpad install` | Build, install, and start the systemd service |
| `tpad run` | Compile and run locally (no systemd) |
| `tpad uninstall` | Stop the service and delete all data |

## Configuration

| Variable | Default | Description |
|---|---|---|
| `PORT` | `3000` | Port to listen on (auto-increments if taken) |
| `TPAD_DATA_DIR` | `~/.local/share/tpad` | Where pads are stored |

## Requirements

- [Rust](https://rustup.rs) — `rustc` in PATH
- [Nushell](https://www.nushell.sh) — `nu` in PATH
- `systemd`
