---
tags:
  - cheatsheet
  - program
---
**The** perfect text editor.
An in-terminal text editor to edit text files, code and do a lot of stuff.
[[nvim]]
# Vim modes
## Normal mode

## Insert mode

## Visual mode

# Cheatsheet
The cheasheet motions, commands and actions found below are to be executed in normal mode.
## Vim motions
- `hjkl` : **Move one character** left, down, up and right respectively.
- `w`: Go to the **beginning of the word**.
- `e` : Go to the **end of the word**.
- `b` : Go to the **beginning of the last word**.
- `0` : Go to the **beginning of the line**.
- `$` : Go to the **end of the line**.
- `^b` : **Go Back** - Scroll up one page.
- `^f` : **Go Forward** - Scroll down one page.
- `^d` : Scroll **Down half a page**.
- `^u` : Scroll **Up half a page**.
## Vim actions
- `i` : Enter **insert mode** before the caret.
- `a` : **Append** : Enter insert mode after the caret.
- `A` : **Append after line** : Enter insert mode at the end of the line.
- `o` : Create **new line after caret** and enter insert mode there.
- `O` : Create **new line before caret** and enter insert mode there.
- `v` : Enter **visual mode** (selection mode).
- `V` : Enter **visual line mode** (visual mode with all whole line selected).
- `y` : **Yank**, or **copy** selection into the clipboard.
- `x` : **Cut** the selection into the clipboard.
- `p` : **Puts** or **paste after** the caret.
- `P` : **Puts before** the caret.
- `d<motion>` : **Delete** the text covered by the motion.
- `dd` : **Delete** the **entire line**.
- `c<motion>` : **Change** the text covered by the motion : delete and enter insert mode.
- `cc` : **Change** the **entire line**.
- `u` : **Undo** last change.
- `^r` : **Redo** next change.
- `/<query>` : **Search** query in current file.
## Vim commands
- `:w` : **Write**, or **save** the current file.
- `:q` : **Close** the current file. Closes vim if this is the only file currently opened.
- `:q!` : **Force close**. Will close without prompting to save files.


# Resources

