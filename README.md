# Text Editor

A terminal-based text editor built from first principles in C, with no dependencies beyond the C standard library and POSIX.

**Status:** 🚧 Work in progress

## Highlights

- Puts the terminal into raw mode via `termios` and renders directly with VT100 escape sequences
- Gap-buffer text storage for efficient inserts and deletes
- Cursor movement, scrolling, file open/save, and incremental search
- Syntax highlighting for C

## Tech

C, POSIX, termios, VT100/ANSI escape codes, Make
