---
tags:
  - C
---
A [[C]] software library that provides in-line edition and history capabilities for interactive programs with a command-line interface for example, like [[Bash]]. Part of the [[GNU Project]].

> [!WARNING] `readline` vs `libedit`
> One needs to be careful coding using `readline` related functions on [[macOS]], because it has (same as pretty much all the [[libc]]) a different implementation than GNU readline, specific to [[BSD]] systems, called `libedit`.

# Keybinds
A lot of keybindings are directly taken from the [[Emacs]] text editor.
# Resources
`man 3 readline` on a Linux that has readline installed.
[Wikipedia Article](https://en.wikipedia.org/wiki/GNU_Readline)