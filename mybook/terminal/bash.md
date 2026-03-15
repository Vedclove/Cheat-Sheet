```{image} https://www.vectorlogo.zone/logos/gnu_bash/gnu_bash-icon.svg
:height: 60px
:align: left
```

# Bash

```{admonition} Quick Facts
:class: tip
- **Type:** Unix shell and scripting language
- **Use cases:** Automation, scripting, file management, process control, DevOps pipelines
- **Config files:** `~/.bashrc` (interactive), `~/.bash_profile` (login), `~/.bash_aliases`
- **Script shebang:** `#!/usr/bin/env bash`
- **Check version:** `bash --version`
```

---

:::{dropdown} 🧭 Navigation & File Management
:open:

| Command | Description |
|---------|-------------|
| `pwd` | Print working directory |
| `cd dir` | Change directory |
| `cd ..` | Go up one level |
| `cd ~` | Go to home directory |
| `cd -` | Go to previous directory |
| `ls` | List files |
| `ls -la` | List all files with details |
| `ls -lh` | Human-readable file sizes |
| `tree` | Directory tree view |
| `mkdir dir` | Create directory |
| `mkdir -p a/b/c` | Create nested directories |
| `rm file` | Delete file |
| `rm -rf dir` | Delete directory recursively |
| `cp src dst` | Copy file |
| `cp -r src dst` | Copy directory |
| `mv src dst` | Move or rename |
| `touch file` | Create empty file / update timestamp |
| `ln -s target link` | Create symbolic link |
:::

:::{dropdown} 📄 Viewing & Editing Files

| Command | Description |
|---------|-------------|
| `cat file` | Print file contents |
| `less file` | Page through file (`q` to quit) |
| `head -n 20 file` | First 20 lines |
| `tail -n 20 file` | Last 20 lines |
| `tail -f file` | Follow file (live updates) |
| `wc -l file` | Count lines |
| `wc -w file` | Count words |
| `sort file` | Sort lines alphabetically |
| `sort -n file` | Sort numerically |
| `uniq file` | Remove duplicate adjacent lines |
| `sort file \| uniq -c` | Count occurrences of each line |
| `cut -d: -f1 file` | Cut field 1 using `:` delimiter |
| `tr 'a-z' 'A-Z'` | Translate characters (lowercase to upper) |
| `diff file1 file2` | Show differences between files |
:::

:::{dropdown} 🔍 Searching

| Command | Description |
|---------|-------------|
| `grep pattern file` | Search for pattern in file |
| `grep -r pattern dir` | Recursive search in directory |
| `grep -i pattern file` | Case-insensitive search |
| `grep -n pattern file` | Show line numbers |
| `grep -v pattern file` | Invert match (exclude lines) |
| `grep -l pattern dir` | List files with matches |
| `grep -E 'a\|b' file` | Extended regex (OR) |
| `find . -name "*.txt"` | Find files by name |
| `find . -type f -mtime -7` | Files modified in last 7 days |
| `find . -size +10M` | Files larger than 10MB |
| `locate filename` | Fast file search (uses index) |
| `which cmd` | Show path of command |
| `type cmd` | Show how a command is resolved |
:::

:::{dropdown} 🔀 Pipes, Redirection & I/O

| Syntax | Description |
|--------|-------------|
| `cmd1 \| cmd2` | Pipe stdout of cmd1 to cmd2 |
| `cmd > file` | Redirect stdout to file (overwrite) |
| `cmd >> file` | Redirect stdout to file (append) |
| `cmd < file` | Read stdin from file |
| `cmd 2> file` | Redirect stderr to file |
| `cmd &> file` | Redirect both stdout and stderr |
| `cmd 2>&1` | Redirect stderr to stdout |
| `cmd \| tee file` | Write to file and also stdout |
| `cmd1 && cmd2` | Run cmd2 only if cmd1 succeeds |
| `cmd1 \|\| cmd2` | Run cmd2 only if cmd1 fails |
| `cmd1 ; cmd2` | Run cmd2 regardless of cmd1 |
| `$(cmd)` | Command substitution |
| `` `cmd` `` | Command substitution (older syntax) |
:::

:::{dropdown} 📦 Variables & Strings

**Variables**

```bash
name="Alice"
echo $name
echo "${name}!"       # Use braces for clarity
readonly PI=3.14      # Constant
unset name            # Delete variable
```

**Special variables**

| Variable | Description |
|----------|-------------|
| `$0` | Script name |
| `$1` … `$9` | Positional arguments |
| `$@` | All arguments (array) |
| `$#` | Number of arguments |
| `$?` | Exit status of last command |
| `$$` | PID of current shell |
| `$!` | PID of last background process |
| `$HOME` | Home directory |
| `$PATH` | Executable search path |
| `$PWD` | Current directory |

**String operations**

```bash
str="Hello World"
echo ${#str}          # Length: 11
echo ${str:6}         # Substring: World
echo ${str:0:5}       # Substring: Hello
echo ${str/World/Bash}  # Replace: Hello Bash
echo ${str,,}         # Lowercase: hello world
echo ${str^^}         # Uppercase: HELLO WORLD
echo ${str% World}    # Strip suffix: Hello
echo ${str#Hello }    # Strip prefix: World
```
:::

:::{dropdown} 🔢 Arithmetic

```bash
# Arithmetic expansion
echo $((3 + 4))
echo $((10 % 3))

# let
let x=5+3

# expr (older)
expr 5 + 3

# bc for floats
echo "scale=2; 10/3" | bc
```

| Operator | Description |
|----------|-------------|
| `+` `-` `*` `/` | Basic arithmetic |
| `%` | Modulo |
| `**` | Exponentiation |
| `++x` / `x++` | Pre/post increment |
| `--x` / `x--` | Pre/post decrement |
:::

:::{dropdown} 🔁 Control Flow

**if / elif / else**

```bash
if [ "$x" -gt 10 ]; then
  echo "big"
elif [ "$x" -eq 10 ]; then
  echo "ten"
else
  echo "small"
fi
```

**Test operators**

| Operator | Description |
|----------|-------------|
| `-eq` `-ne` `-lt` `-le` `-gt` `-ge` | Numeric comparison |
| `=` `!=` | String equality |
| `-z str` | String is empty |
| `-n str` | String is non-empty |
| `-f file` | File exists and is regular |
| `-d file` | Directory exists |
| `-e file` | File or directory exists |
| `-r` `-w` `-x` | Readable / writable / executable |

**for loop**

```bash
for i in 1 2 3; do
  echo $i
done

for file in *.txt; do
  echo "$file"
done

for ((i=0; i<5; i++)); do
  echo $i
done
```

**while / until**

```bash
while [ "$count" -lt 5 ]; do
  echo $count
  ((count++))
done

until [ "$count" -ge 5 ]; do
  ((count++))
done
```

**case**

```bash
case "$var" in
  start) echo "Starting" ;;
  stop)  echo "Stopping" ;;
  *)     echo "Unknown" ;;
esac
```
:::

:::{dropdown} 🧩 Functions

```bash
greet() {
  local name="$1"          # local variable
  echo "Hello, $name!"
  return 0                 # exit status
}

greet "Alice"
result=$(greet "Bob")      # capture output
```

| Feature | Syntax |
|---------|--------|
| Define function | `name() { ... }` |
| Call function | `name arg1 arg2` |
| Local variable | `local var=value` |
| Return status | `return N` (0=success) |
| Access args | `$1`, `$2`, `$@` |
:::

:::{dropdown} 📋 Arrays

```bash
# Indexed array
arr=(one two three)
echo ${arr[0]}          # one
echo ${arr[@]}          # all elements
echo ${#arr[@]}         # length: 3
arr+=(four)             # append
unset arr[1]            # remove element

# Associative array (Bash 4+)
declare -A map
map[key]="value"
echo ${map[key]}
echo ${!map[@]}         # all keys
echo ${map[@]}          # all values
```
:::

:::{dropdown} 📜 Script Basics

**Template**

```bash
#!/usr/bin/env bash
set -euo pipefail       # strict mode
IFS=$'\n\t'

main() {
  echo "Args: $@"
}

main "$@"
```

**`set` options**

| Option | Description |
|--------|-------------|
| `set -e` | Exit on error |
| `set -u` | Error on undefined variable |
| `set -o pipefail` | Catch errors in pipes |
| `set -x` | Print each command (debug) |
| `set +x` | Disable debug |

**Input**

```bash
read -p "Enter name: " name
read -s -p "Password: " pass   # silent input
read -t 10 input                # timeout
```

**Exit codes**

```bash
exit 0    # success
exit 1    # general error
exit 2    # misuse of command
echo $?   # check last exit code
```
:::

:::{dropdown} ⚙️ Process Management

| Command | Description |
|---------|-------------|
| `ps aux` | List all running processes |
| `top` / `htop` | Interactive process viewer |
| `kill PID` | Send SIGTERM to process |
| `kill -9 PID` | Force kill (SIGKILL) |
| `pkill name` | Kill by process name |
| `jobs` | List background jobs |
| `bg %N` | Resume job N in background |
| `fg %N` | Bring job N to foreground |
| `cmd &` | Run command in background |
| `nohup cmd &` | Run immune to hangup |
| `wait` | Wait for all background jobs |
| `sleep N` | Pause for N seconds |
| `time cmd` | Measure execution time |
:::

:::{dropdown} 🌐 Environment & Shell Config

```bash
export VAR=value         # export to child processes
printenv                 # print all env variables
env VAR=x cmd            # run cmd with modified env
source ~/.bashrc         # reload config
. script.sh              # source script (same shell)

# PATH management
export PATH="$HOME/.local/bin:$PATH"

# Aliases
alias ll='ls -la'
alias gs='git status'
unalias ll
```

**`.bashrc` essentials**

```bash
# Prompt
export PS1="\u@\h:\w\$ "

# History
export HISTSIZE=10000
export HISTFILESIZE=20000
export HISTCONTROL=ignoredups:erasedups
shopt -s histappend

# Auto-complete
bind 'set show-all-if-ambiguous on'
```
:::

:::{dropdown} 💡 Tips & Tricks

- **Brace expansion:** `mkdir -p project/{src,tests,docs}` creates all three dirs
- **Glob patterns:** `*` any chars, `?` one char, `[abc]` character class, `**` recursive (with `shopt -s globstar`)
- **History shortcuts:** `!!` last command, `!$` last argument, `Ctrl+r` reverse search
- **Here-doc:** `cat << EOF ... EOF` for multiline strings
- **Here-string:** `cmd <<< "string"` feed string as stdin
- **Parameter defaults:** `${var:-default}` use default if unset, `${var:=default}` assign default if unset
- **String length check:** `[[ -z "$var" ]]` empty, `[[ -n "$var" ]]` non-empty
- **Null device:** `cmd > /dev/null 2>&1` suppress all output
- **xargs:** `find . -name "*.log" | xargs rm` pass results as arguments
- **Script directory:** `DIR="$(cd "$(dirname "${BASH_SOURCE[0]}")" && pwd)"`
:::
