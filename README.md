## alacritty

GPU-accelerated terminal emulator

Automatic install/update:

```shell
bash -c "$(curl -LSs https://github.com/dfmgr/alacritty/raw/main/install.sh)"
```

Manual install:

requires:

Debian based:

```shell
apt install alacritty
```

Fedora Based:

```shell
yum install alacritty
```

Arch Based:

```shell
pacman -S alacritty
```

MacOS:

```shell
brew install alacritty
```

```shell
mv -fv "$HOME/.config/alacritty" "$HOME/.config/alacritty.bak"
git clone https://github.com/dfmgr/alacritty "$HOME/.config/alacritty"
```

## Keyboard Bindings

Press `Ctrl+Shift+/` to view the full keybindings help in the terminal.

### Quick Reference

| Key | Action |
|-----|--------|
| `Ctrl+Shift+Space` | Toggle Vi mode |
| `Ctrl+Shift+C` | Copy |
| `Ctrl+Shift+V` | Paste |
| `Ctrl+Shift+F` | Search forward |
| `Ctrl+Shift+N` | New window |
| `F11` | Toggle fullscreen |
| `Ctrl+0` | Reset font size |
| `Ctrl+=` / `Ctrl+-` | Increase/decrease font |
| `Ctrl+Shift+K` | Clear history |
| `Ctrl+Shift+/` | Show keybindings help |

### Hints (URL/Path Detection)

| Key | Action |
|-----|--------|
| `Ctrl+Shift+O` | Highlight URLs - type hint to open |
| `Ctrl+Shift+P` | Highlight file paths - type hint to open/edit |
| `Ctrl+Shift+I` | Highlight IP addresses - type hint to copy |

### Mouse Bindings

| Mouse | Action |
|-------|--------|
| `Middle-click` | Paste selection |
| `Right-click` | Paste clipboard |
| `Ctrl+Left-click` | Open URL |
| `Alt+Left-drag` | Block selection |

### Vi Mode

Enter with `Ctrl+Shift+Space`, exit with `i`, `q`, or `Escape`.

| Key | Action |
|-----|--------|
| `h/j/k/l` | Navigation |
| `w/b/e` | Word movement |
| `0` / `$` | Line start/end |
| `G` / `gg` | Bottom/top of scrollback |
| `v` / `V` / `Ctrl+V` | Visual/line/block select |
| `/` / `?` | Search forward/backward |
| `n` / `N` | Next/previous match |
| `y` | Copy selection |

### Multiplexer Integration (tmux/screen/zellij)

| Key | Action |
|-----|--------|
| `Alt+1` - `Alt+9` | Switch to window 1-9 |
| `Alt+n` / `Alt+p` | Next/previous window |
| `Alt+c` | New window |
| `Alt+d` | Detach session |
| `Alt+z` | Zoom pane |
| `Alt+\|` / `Alt+-` | Split vertical/horizontal |
| `Alt+Arrow` | Navigate panes |

See [etc/bindings.md](etc/bindings.md) for complete documentation including multiplexer config snippets.

## Themes

Available themes in `etc/themes/`:

- `doom-one`, `dracula` (default), `gruvbox-dark`, `monokai-pro`, `nord`
- `oceanic-next`, `palenight`, `solarized-dark`, `solarized-light`, `tomorrow-night`

Change theme by editing `import` in `etc/alacritty.toml`:
```toml
import = ["./themes/nord.toml"]
```

## Notes

- **No tabs**: Alacritty doesn't support tabs by design. Use `tmux`, `screen`, or `zellij`.
- **Live reload**: Config changes apply automatically when saved.
- **Cursor blinking**: Enabled by default (500ms interval).
- **URL hints**: Press `Ctrl+Shift+O` to highlight clickable URLs.
- **Auto-start multiplexer**: Uncomment the `[terminal]` section in config to auto-launch tmux/screen/zellij.

<p align=center>
  <a href="https://wiki.archlinux.org/index.php/alacritty" target="_blank" rel="noopener noreferrer">alacritty wiki</a>  |
  <a href="https://github.com/alacritty/alacritty" target="_blank" rel="noopener noreferrer">alacritty site</a>
</p>  
