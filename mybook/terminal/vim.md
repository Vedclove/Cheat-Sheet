```{image} https://www.vectorlogo.zone/logos/vim/vim-icon.svg
:height: 60px
:align: left
```

# Vim

```{admonition} Quick Facts
:class: tip
- **Type:** Modal text editor
- **Use cases:** Code editing, config files, quick terminal edits, remote SSH editing
- **Modes:** Normal, Insert, Visual, Command-line, Replace
- **Config file:** `~/.vimrc` (Vim) or `~/.config/nvim/init.vim` (Neovim)
- **Exit:** `:q` quit, `:wq` save & quit, `:q!` force quit without saving
```

---

```{dropdown} 🚀 Opening & Exiting
:open:

| Command | Description |
|---------|-------------|
| `vim file.txt` | Open file |
| `vim +N file.txt` | Open file at line N |
| `vim +/pattern file.txt` | Open file at first match of pattern |
| `vim -R file.txt` | Open file in read-only mode |
| `:q` | Quit (fails if unsaved changes) |
| `:q!` | Force quit, discard changes |
| `:w` | Save file |
| `:wq` or `ZZ` | Save and quit |
| `:w filename` | Save as new filename |
| `:x` | Save only if changed, then quit |
```

```{dropdown} 🎮 Modes

| Mode | Enter with | Description |
|------|-----------|-------------|
| **Normal** | `Esc` | Default mode — navigate and run commands |
| **Insert** | `i` | Type and edit text |
| **Visual** | `v` | Select characters |
| **Visual Line** | `V` | Select whole lines |
| **Visual Block** | `Ctrl+v` | Select a block/column |
| **Command-line** | `:` | Run ex commands |
| **Replace** | `R` | Overwrite characters |
```

```{dropdown} 🧭 Navigation (Normal Mode)

**Basic movement**

| Key | Move |
|-----|------|
| `h` | Left |
| `j` | Down |
| `k` | Up |
| `l` | Right |
| `w` | Next word start |
| `b` | Previous word start |
| `e` | Next word end |
| `W` / `B` / `E` | Same but WORD (whitespace-delimited) |

**Line navigation**

| Key | Move |
|-----|------|
| `0` | Start of line |
| `^` | First non-blank character |
| `$` | End of line |
| `gg` | First line of file |
| `G` | Last line of file |
| `:N` or `NG` | Go to line N |

**Screen navigation**

| Key | Move |
|-----|------|
| `Ctrl+f` | Page down |
| `Ctrl+b` | Page up |
| `Ctrl+d` | Half page down |
| `Ctrl+u` | Half page up |
| `H` | Top of screen |
| `M` | Middle of screen |
| `L` | Bottom of screen |
| `zz` | Center cursor on screen |
```

```{dropdown} ✏️ Inserting & Editing

**Entering insert mode**

| Key | Description |
|-----|-------------|
| `i` | Insert before cursor |
| `I` | Insert at beginning of line |
| `a` | Append after cursor |
| `A` | Append at end of line |
| `o` | Open new line below |
| `O` | Open new line above |
| `s` | Delete character and insert |
| `S` | Delete line and insert |
| `C` | Delete to end of line and insert |

**Editing in normal mode**

| Key | Description |
|-----|-------------|
| `x` | Delete character under cursor |
| `X` | Delete character before cursor |
| `dd` | Delete (cut) current line |
| `D` | Delete to end of line |
| `dw` | Delete word |
| `d$` | Delete to end of line |
| `d0` | Delete to start of line |
| `yy` | Yank (copy) current line |
| `yw` | Yank word |
| `p` | Paste after cursor |
| `P` | Paste before cursor |
| `r` | Replace single character |
| `~` | Toggle case of character |
| `u` | Undo |
| `Ctrl+r` | Redo |
| `.` | Repeat last change |
```

```{dropdown} 🔍 Search & Replace

**Searching**

| Command | Description |
|---------|-------------|
| `/pattern` | Search forward for pattern |
| `?pattern` | Search backward for pattern |
| `n` | Next match |
| `N` | Previous match |
| `*` | Search for word under cursor (forward) |
| `#` | Search for word under cursor (backward) |
| `:noh` | Clear search highlighting |

**Substitution**

| Command | Description |
|---------|-------------|
| `:s/old/new/` | Replace first occurrence on current line |
| `:s/old/new/g` | Replace all on current line |
| `:%s/old/new/g` | Replace all in file |
| `:%s/old/new/gc` | Replace all with confirmation |
| `:5,10s/old/new/g` | Replace in lines 5–10 |
```

```{dropdown} 📋 Visual Mode & Selection

| Key | Description |
|-----|-------------|
| `v` | Start character selection |
| `V` | Start line selection |
| `Ctrl+v` | Start block selection |
| `o` | Move to other end of selection |
| `d` | Delete selected |
| `y` | Yank selected |
| `c` | Change selected (delete + insert) |
| `>` | Indent selected |
| `<` | Unindent selected |
| `=` | Auto-indent selected |
| `~` | Toggle case of selected |
| `u` / `U` | Lowercase / Uppercase selected |
```

```{dropdown} 🪟 Windows & Tabs

**Splits**

| Command | Description |
|---------|-------------|
| `:sp` or `Ctrl+w s` | Horizontal split |
| `:vsp` or `Ctrl+w v` | Vertical split |
| `Ctrl+w h/j/k/l` | Move between splits |
| `Ctrl+w =` | Equal size splits |
| `Ctrl+w _` | Maximize height |
| `Ctrl+w \|` | Maximize width |
| `:close` | Close current split |

**Tabs**

| Command | Description |
|---------|-------------|
| `:tabnew file` | Open file in new tab |
| `gt` | Next tab |
| `gT` | Previous tab |
| `:tabclose` | Close tab |
| `:tabs` | List all tabs |
```

```{dropdown} 📁 Buffers & Files

| Command | Description |
|---------|-------------|
| `:e file` | Edit a file |
| `:ls` or `:buffers` | List open buffers |
| `:b N` | Switch to buffer N |
| `:bn` | Next buffer |
| `:bp` | Previous buffer |
| `:bd` | Delete (close) buffer |
| `:r file` | Read file contents into current buffer |
| `:r !cmd` | Read command output into buffer |
```

```{dropdown} ⚙️ Useful Settings (`:set`)

| Command | Description |
|---------|-------------|
| `:set number` | Show line numbers |
| `:set relativenumber` | Show relative line numbers |
| `:set hlsearch` | Highlight search results |
| `:set incsearch` | Incremental search |
| `:set ignorecase` | Case-insensitive search |
| `:set smartcase` | Case-sensitive if uppercase used |
| `:set autoindent` | Auto-indent new lines |
| `:set tabstop=4` | Tab width = 4 spaces |
| `:set expandtab` | Use spaces instead of tabs |
| `:set wrap` | Wrap long lines |
| `:set syntax=on` | Enable syntax highlighting |
| `:set paste` | Paste mode (disables auto-indent) |

**Sample `~/.vimrc`**

```vim
set number
set relativenumber
set hlsearch
set incsearch
set ignorecase
set smartcase
set autoindent
set tabstop=4
set shiftwidth=4
set expandtab
set wrap
syntax on
```
```

```{dropdown} 🔧 Macros & Registers

| Command | Description |
|---------|-------------|
| `qa` | Start recording macro into register `a` |
| `q` | Stop recording |
| `@a` | Play macro `a` |
| `@@` | Repeat last macro |
| `5@a` | Run macro `a` 5 times |
| `"ay` | Yank into register `a` |
| `"ap` | Paste from register `a` |
| `:reg` | Show all registers |
```

```{dropdown} 💡 Tips & Tricks

- **Repeat a command N times:** prefix with a number, e.g. `5j` moves down 5 lines, `3dd` deletes 3 lines
- **Text objects:** `ciw` (change inner word), `ci"` (change inside quotes), `da(` (delete around parentheses)
- **Jump list:** `Ctrl+o` (older position), `Ctrl+i` (newer position)
- **Marks:** `ma` set mark `a`, `` `a `` jump to mark `a`
- **Sort lines:** `:%sort` (whole file), `:5,10sort` (lines 5–10)
- **Execute shell command:** `:!ls`
- **Filter lines through command:** `:%!sort -u`
- **Spell check:** `:set spell`, `]s` next misspelling, `z=` suggest corrections
```
