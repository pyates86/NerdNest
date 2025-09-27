# Vim Text Editor Cheatsheet

Vim is a powerful, highly configurable text editor used widely in programming and system administration. This cheatsheet lists the main commands for navigating, editing, saving, and managing files in Vim. It’s designed for quick reference, covering essential commands for beginners and intermediate users.  

**ProTip:** Type `vimtutor` in a Terminal window and you will enter a hands-on vim tutorial, where you will put into practice most (if not all) of what is listed below.  

---

## Modes in Vim

Vim operates in different modes:

* **Normal Mode:** For navigation and issuing commands (default mode).  
* **Insert Mode:** For typing and editing text.  
* **Visual Mode:** For selecting text.  
* **Command-Line Mode:** For executing commands (e.g., saving, quitting).

Switch between modes using the commands below.  

---

## Basic Commands

### Mode Switching

| Command | Description |
| ----- | ----- |
| `i` | Enter Insert Mode before the cursor |
| `I` | Enter Insert Mode at the start of the line |
| `a` | Enter Insert Mode after the cursor |
| `A` | Enter Insert Mode at the end of the line |
| `o` | Open a new line below and enter Insert Mode |
| `O` | Open a new line above and enter Insert Mode |
| `v` | Enter Visual Mode (character-based selection) |
| `V` | Enter Visual Line Mode (line-based selection) |
| `Ctrl-v` | Enter Visual Block Mode (column-based selection) |
| `Esc` | Return to Normal Mode from any mode |
| `:` | Enter Command-Line Mode (for commands like `:w`) |

---

### Navigation

| Command | Description |
| ----- | ----- |
| `h` | Move cursor left |
| `j` | Move cursor down |
| `k` | Move cursor up |
| `l` | Move cursor right |
| `w` | Move to the start of the next word |
| `b` | Move to the start of the previous word |
| `e` | Move to the end of the current/next word |
| `0` | Move to the start of the line |
| `$` | Move to the end of the line |
| `gg` | Go to the first line of the file |
| `G` | Go to the last line of the file |
| `:n` | Go to line number `n` (e.g., `:10` for line 10) |
| `Ctrl-f` | Scroll down one page |
| `Ctrl-b` | Scroll up one page |

---

### Editing

| Command | Description |
| ----- | ----- |
| `x` | Delete character under the cursor |
| `dd` | Delete (cut) the current line |
| `dw` | Delete from cursor to end of word |
| `d$` | Delete from cursor to end of line |
| `d0` | Delete from cursor to start of line |
| `yy` | Yank (copy) the current line |
| `yw` | Yank from cursor to end of word |
| `p` | Paste after the cursor |
| `P` | Paste before the cursor |
| `u` | Undo the last change |
| `Ctrl-r` | Redo the last undone change |
| `r` | Replace the character under the cursor |
| `R` | Enter Replace Mode (overwrite text) |
| `ciw` | Change (delete and enter Insert Mode) the current word |
| `.` | Repeat the last change |

---

### Search and Replace

| Command | Description |
| ----- | ----- |
| `/pattern` | Search forward for `pattern` |
| `?pattern` | Search backward for `pattern` |
| `n` | Move to the next search match |
| `N` | Move to the previous search match |
| `:%s/old/new/g` | Replace all occurrences of `old` with `new` in the file |
| `:%s/old/new/gc` | Replace with confirmation for each occurrence |

---

### Saving and Quitting

| Command | Description |
| ----- | ----- |
| `:w` | Save (write) the file |
| `:w filename` | Save as `filename` |
| `:q` | Quit Vim (if no changes made) |
| `:q!` | Quit without saving changes |
| `:wq` | Save and quit |
| `:x` | Save and quit (same as `:wq`) |
| `ZZ` | Save and quit (from Normal Mode) |
| `ZQ` | Quit without saving (from Normal Mode) |

---

### Visual Mode Operations

| Command | Description |
| ----- | ----- |
| `v` | Start Visual Mode, select characters |
| `V` | Start Visual Line Mode, select lines |
| `Ctrl-v` | Start Visual Block Mode, select columns |
| `d` | Delete selected text |
| `y` | Yank (copy) selected text |
| `p` | Paste over selected text |
| `>` | Indent selected lines right |
| `<` | Indent selected lines left |

---

### Multiple Files and Buffers

| Command | Description |
| ----- | ----- |
| `:e filename` | Open `filename` for editing |
| `:bn` | Switch to the next buffer |
| `:bp` | Switch to the previous buffer |
| `:bd` | Close the current buffer |
| `:ls` | List all open buffers |
| `:sp` | Split window horizontally |
| `:vsp` | Split window vertically |
| `Ctrl-w w` | Switch between split windows |

---

### Miscellaneous

| Command | Description |
| ----- | ----- |
| `:set number` | Show line numbers |
| `:set nonumber` | Hide line numbers |
| `:set wrap` | Enable line wrapping |
| `:set nowrap` | Disable line wrapping |
| `:help command` | Open help for `command` (e.g., `:help :w`) |
| `J` | Join the current line with the next line |
| `ga` | Show ASCII value of character under cursor |
| `:sh` | Open a shell (return to Vim with `exit`) |

---

### Tips for Using Vim

* **Practice Modes:** Always be aware of your current mode (Normal, Insert, Visual, Command-Line). Use `Esc` to return to Normal Mode.  
* **Combine Commands:** Use counts with commands (e.g., `3dd` deletes three lines, `5w` moves five words forward).  
* **Use** `.vimrc`: Customize Vim by editing `~/.vimrc` for settings like `set number` or key mappings.  
* **Learn Incrementally:** Start with basic navigation (`h`, `j`, `k`, `l`) and editing (`i`, `dd`, `yy`), then add advanced commands.  
* **Exit Safely:** If stuck, use `:q!` to exit without saving or `ZZ` to save and exit.

---

### Notes

* Commands are case-sensitive (e.g., `p` vs. `P`).  
* Most commands are executed in Normal Mode unless specified.  
* For advanced features (e.g., macros, plugins), explore Vim’s documentation with `:help`.  
* This cheatsheet covers common commands but isn’t exhaustive. Vim’s power lies in its extensibility and customization.
