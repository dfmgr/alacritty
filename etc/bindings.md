# Alacritty Keyboard Bindings

## Quick Reference

| Action | Key |
|--------|-----|
| Toggle Vi mode | `Ctrl+Shift+Space` |
| Show this help | `Ctrl+Shift+/` |
| Search | `Ctrl+Shift+F` |
| URL hints | `Ctrl+Shift+O` |
| Path hints | `Ctrl+Shift+P` |

---

## Clipboard

| Key | Action |
|-----|--------|
| `Ctrl+Shift+C` | Copy |
| `Ctrl+Shift+V` | Paste |
| `Shift+Insert` | Paste selection |

## Window & Display

| Key | Action |
|-----|--------|
| `F11` | Toggle fullscreen |
| `Ctrl+Shift+N` | New window |
| `Ctrl+0` | Reset font size |
| `Ctrl+=` | Increase font size |
| `Ctrl+Shift++` | Increase font size |
| `Ctrl+-` | Decrease font size |

## Clear/Reset

| Key | Action |
|-----|--------|
| `Ctrl+L` | Clear screen |
| `Ctrl+Shift+K` | Clear scrollback history |
| `Ctrl+Shift+R` | Reset terminal |

## Search

| Key | Action |
|-----|--------|
| `Ctrl+Shift+F` | Search forward |
| `Ctrl+Shift+B` | Search backward |

### In Search Mode

| Key | Action |
|-----|--------|
| `Enter` | Confirm search |
| `Escape` | Cancel search |
| `n` / `Down` | Next match |
| `Shift+N` / `Up` | Previous match |

## Scrolling

| Key | Action |
|-----|--------|
| `PageUp` | Scroll page up |
| `PageDown` | Scroll page down |
| `Shift+Home` | Scroll to top |
| `Shift+End` | Scroll to bottom |
| `Ctrl+Shift+U` | Scroll half page up |
| `Ctrl+Shift+D` | Scroll half page down |
| `Ctrl+Shift+Up` | Scroll one line up |
| `Ctrl+Shift+Down` | Scroll one line down |

## Help

| Key | Action |
|-----|--------|
| `Ctrl+Shift+/` | Show this help |

---

## Hints (URL/Path Detection)

Press the key combo, then type the displayed hint character to activate.

| Key | Action |
|-----|--------|
| `Ctrl+Shift+O` | Highlight URLs - type hint to open |
| `Ctrl+Shift+P` | Highlight file paths - type hint to open/edit |
| `Ctrl+Shift+I` | Highlight IP addresses - type hint to copy |

---

## Mouse Bindings

| Mouse | Action |
|-------|--------|
| `Middle-click` | Paste selection |
| `Right-click` | Paste clipboard |
| `Ctrl+Left-click` | Open URL |
| `Alt+Left-drag` | Block selection |

---

## Vi Mode

Enter Vi mode with `Ctrl+Shift+Space`. Exit with `i`, `q`, or `Escape`.

### Navigation

| Key | Action |
|-----|--------|
| `h` | Move left |
| `j` | Move down |
| `k` | Move up |
| `l` | Move right |

### Word Movement

| Key | Action |
|-----|--------|
| `w` | Next word start |
| `b` | Previous word start |
| `e` | Next word end |
| `W` | Next WORD start (whitespace delimited) |
| `B` | Previous WORD start |
| `E` | Next WORD end |

### Line Movement

| Key | Action |
|-----|--------|
| `0` | Start of line |
| `$` | End of line |
| `^` | First non-blank character |

### Screen Movement

| Key | Action |
|-----|--------|
| `G` | Go to bottom |
| `gg` | Go to top |
| `H` | Top of screen (High) |
| `M` | Middle of screen |
| `L` | Bottom of screen (Low) |
| `Ctrl+U` | Half page up |
| `Ctrl+D` | Half page down |

### Selection

| Key | Action |
|-----|--------|
| `v` | Toggle character selection |
| `V` | Toggle line selection |
| `Ctrl+V` | Toggle block selection |
| `y` | Copy (yank) selection |
| `Escape` | Clear selection |

### Search (in Vi Mode)

| Key | Action |
|-----|--------|
| `/` | Search forward |
| `?` | Search backward |
| `n` | Next match |
| `N` | Previous match |

### Other

| Key | Action |
|-----|--------|
| `o` | Open URL/hint under cursor |
| `%` | Jump to matching bracket |
| `i` | Exit Vi mode (insert) |
| `q` | Exit Vi mode (quit) |

---

## Multiplexer Integration (tmux/screen/zellij)

These bindings send escape sequences. Configure your multiplexer to respond to them.

### Window/Tab Switching

| Key | Sends | Typical Use |
|-----|-------|-------------|
| `Alt+1` - `Alt+9` | `Esc+1` - `Esc+9` | Switch to window 1-9 |
| `Alt+0` | `Esc+0` | Switch to window 10 |
| `Alt+n` | `Esc+n` | Next window |
| `Alt+p` | `Esc+p` | Previous window |

### Window Management

| Key | Sends | Typical Use |
|-----|-------|-------------|
| `Alt+c` | `Esc+c` | New window |
| `Alt+d` | `Esc+d` | Detach session |
| `Alt+z` | `Esc+z` | Zoom/maximize pane |

### Pane Splitting

| Key | Sends | Typical Use |
|-----|-------|-------------|
| `Alt+\|` | `Esc+\|` | Vertical split |
| `Alt+-` | `Esc+-` | Horizontal split |

### Pane Navigation

| Key | Sends | Typical Use |
|-----|-------|-------------|
| `Alt+Up` | Arrow | Move to pane above |
| `Alt+Down` | Arrow | Move to pane below |
| `Alt+Left` | Arrow | Move to pane left |
| `Alt+Right` | Arrow | Move to pane right |

---

## Multiplexer Setup

To use the Alt+ bindings, add these to your multiplexer config:

### tmux (~/.tmux.conf)

```bash
# Alt+number to switch windows
bind -n M-1 select-window -t 1
bind -n M-2 select-window -t 2
bind -n M-3 select-window -t 3
bind -n M-4 select-window -t 4
bind -n M-5 select-window -t 5
bind -n M-6 select-window -t 6
bind -n M-7 select-window -t 7
bind -n M-8 select-window -t 8
bind -n M-9 select-window -t 9
bind -n M-0 select-window -t 10

# Alt+n/p for next/previous
bind -n M-n next-window
bind -n M-p previous-window

# Alt+c for new window
bind -n M-c new-window

# Alt+d to detach
bind -n M-d detach-client

# Alt+z to zoom
bind -n M-z resize-pane -Z

# Alt+| and Alt+- for splits
bind -n M-| split-window -h
bind -n M-- split-window -v

# Alt+arrows for pane navigation
bind -n M-Up select-pane -U
bind -n M-Down select-pane -D
bind -n M-Left select-pane -L
bind -n M-Right select-pane -R

# Start windows at 1, not 0
set -g base-index 1
setw -g pane-base-index 1
```

### zellij (~/.config/zellij/config.kdl)

```kdl
keybinds {
    normal {
        bind "Alt 1" { GoToTab 1; }
        bind "Alt 2" { GoToTab 2; }
        bind "Alt 3" { GoToTab 3; }
        bind "Alt 4" { GoToTab 4; }
        bind "Alt 5" { GoToTab 5; }
        bind "Alt n" { GoToNextTab; }
        bind "Alt p" { GoToPreviousTab; }
        bind "Alt c" { NewTab; }
        bind "Alt d" { Detach; }
        bind "Alt z" { ToggleFocusFullscreen; }
        bind "Alt |" { NewPane "Right"; }
        bind "Alt -" { NewPane "Down"; }
    }
}
```

### screen (~/.screenrc)

```
# Alt+number bindings
bindkey "^[1" select 1
bindkey "^[2" select 2
bindkey "^[3" select 3
bindkey "^[4" select 4
bindkey "^[5" select 5
bindkey "^[n" next
bindkey "^[p" prev
bindkey "^[c" screen
bindkey "^[d" detach
```

---

## Available Themes

Change theme by editing `import` in `alacritty.toml`:

- `doom-one`
- `dracula` (default)
- `gruvbox-dark`
- `monokai-pro`
- `nord`
- `oceanic-next`
- `palenight`
- `solarized-dark`
- `solarized-light`
- `tomorrow-night`

Example: `import = ["./themes/nord.toml"]`

---

## Auto-Start Multiplexer

Edit `alacritty.toml` and uncomment one of:

```toml
# tmux
[terminal]
shell = { program = "/usr/bin/tmux", args = ["new-session", "-A", "-s", "main"] }

# screen
[terminal]
shell = { program = "/usr/bin/screen", args = ["-xRR"] }

# zellij
[terminal]
shell = { program = "/usr/bin/zellij", args = ["attach", "--create", "main"] }
```

---

## Tips

- **No tabs**: Alacritty doesn't support tabs by design. Use `tmux`, `screen`, or `zellij`.
- **Live reload**: Config changes apply automatically when saved.
- **URL hints**: Press `Ctrl+Shift+O` to highlight links, then type the hint character.
- **Cursor blinking**: Enabled by default. Edit `[cursor]` section to customize.
