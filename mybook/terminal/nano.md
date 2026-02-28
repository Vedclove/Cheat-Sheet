```{image} https://raw.githubusercontent.com/Vedclove/Cheat-Sheet/main/mybook/utils/nano.png
:height: 60px
:align: left
```

# nano

```{admonition} Quick Facts
:class: tip
- **Type:** Simple terminal text editor
- **Use cases:** Quick config edits, beginner-friendly terminal editing, cron jobs, commit messages
- **Config file:** `~/.nanorc` or `/etc/nanorc`
- **Open file:** `nano filename`
- **Notation:** `^` = Ctrl, `M-` = Alt (Meta)
```

---

```{dropdown} 🚀 Opening & Exiting
:open:

| Command | Description |
|---------|-------------|
| `nano file` | Open or create file |
| `nano +N file` | Open file at line N |
| `nano -l file` | Show line numbers |
| `nano -v file` | Open in view-only (read-only) mode |
| `nano -B file` | Create backup before saving |
| `nano -m file` | Enable mouse support |
| `^X` | Exit nano |
| `^X` then `Y` | Save and exit |
| `^X` then `N` | Exit without saving |
```

```{dropdown} 💾 Saving & Files

| Shortcut | Description |
|----------|-------------|
| `^S` | Save current file |
| `^O` | Save as (Write Out) — prompts for filename |
| `^O` then `Enter` | Confirm save with same filename |
| `^R` | Read (insert) another file at cursor |
| `^T` (in filename prompt) | Open file browser to pick a file |
```

```{dropdown} 🧭 Navigation

| Shortcut | Description |
|----------|-------------|
| Arrow keys | Move cursor |
| `^F` / `^B` | Forward / backward one character |
| `^N` / `^P` | Next / previous line |
| `^A` | Beginning of line |
| `^E` | End of line |
| `^Space` | Forward one word |
| `M-Space` | Backward one word |
| `^V` | Page down |
| `^Y` | Page up |
| `M-\` or `^Home` | Go to first line |
| `M-/` or `^End` | Go to last line |
| `^_` | Go to specific line (and column) |
| `M-G` | Same as `^_` — go to line number |
```

```{dropdown} ✏️ Editing

| Shortcut | Description |
|----------|-------------|
| `^D` | Delete character under cursor |
| `Backspace` | Delete character before cursor |
| `M-Backspace` | Delete word to the left |
| `^K` | Cut (kill) current line |
| `M-6` | Copy current line |
| `^U` | Paste (uncut) |
| `M-U` | Undo |
| `M-E` | Redo |
| `^J` | Justify (reflow) current paragraph |
| `M-J` | Justify entire file |
| `Tab` | Insert tab / indent |
| `M-}` | Indent selected lines |
| `M-{` | Unindent selected lines |
```

```{dropdown} 🔍 Search & Replace

| Shortcut | Description |
|----------|-------------|
| `^W` | Search (Where is) |
| `^W` then `^R` | Search and replace |
| `M-W` | Repeat last search (find next) |
| `M-Q` | Repeat search in reverse |

**In the search prompt:**

| Key | Description |
|-----|-------------|
| `^C` | Cancel search |
| `M-C` | Toggle case sensitivity |
| `M-R` | Toggle regular expressions |
| `M-B` | Toggle backwards search |
| `Up/Down` | Navigate search history |

**In the replace prompt:**

| Key | Description |
|-----|-------------|
| `Y` | Replace this occurrence |
| `N` | Skip this occurrence |
| `A` | Replace all occurrences |
```

```{dropdown} 📋 Selection & Cut/Copy/Paste

| Shortcut | Description |
|----------|-------------|
| `M-A` | Set mark (start selection) |
| Arrow keys | Extend selection after mark |
| `^K` | Cut selected text (or current line) |
| `M-6` | Copy selected text (or current line) |
| `^U` | Paste cut/copied text |
| `M-A` again | Cancel mark/selection |

**Cut buffer tip:** `^K` multiple times appends to the cut buffer — paste all at once with `^U`.
```

```{dropdown} 🪟 Multiple Buffers & Toggles

| Shortcut | Description |
|----------|-------------|
| `M-<` | Switch to previous buffer |
| `M->` | Switch to next buffer |
| `^X` | Close current buffer |
| `M-I` | Toggle auto-indent |
| `M-N` | Toggle line numbers |
| `M-P` | Toggle whitespace display |
| `M-S` | Toggle soft-wrapping |
| `M-X` | Toggle help bar at bottom |
| `M-C` | Toggle cursor position display |
```

```{dropdown} ⚙️ Configuration (~/.nanorc)

```ini
# Line numbers
set linenumbers

# Smooth scrolling
set smooth

# Auto-indent
set autoindent

# Tab size and use spaces
set tabsize 4
set tabstospaces

# Enable mouse
set mouse

# Soft wrap long lines
set softwrap

# Show cursor position
set constantshow

# Backup files
set backup

# Syntax highlighting (load all defaults)
include "/usr/share/nano/*.nanorc"
```
```

```{dropdown} 💡 Tips & Tricks

- **Bottom bar shortcuts:** nano always shows available shortcuts at the bottom — `^` = Ctrl, `M-` = Alt
- **Line number jump:** `^_` then type `line,column` (e.g. `42,10`) to jump precisely
- **Open multiple files:** `nano file1 file2` — use `M-<` / `M->` to switch between them
- **Pipe into nano:** `echo "hello" | nano -` — edit piped input
- **View compressed files:** `zcat file.gz | nano -`
- **Syntax highlighting:** install language `.nanorc` files from `/usr/share/nano/` or `nano-syntax-highlighting` package
- **Disable help bar** for more editing space: `M-X` toggles it, or add `set nohelp` to `~/.nanorc`
- **Undo history** is session-only — changes cannot be undone after reopening a file
```
