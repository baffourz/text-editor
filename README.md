# Text Editor

A terminal text editor with no dependencies past libc, written in C. Built May to August 2025.

**Status:** 🚧 Work in progress. The source isn't published here yet.

## Why

I wanted to know how Vim draws a screen. A terminal is a stream of bytes in both directions, and nothing on it moves unless you tell it to.

## What I did

I started from antirez's kilo tutorial and then went my own way, rewriting its row storage and rendering. Raw mode comes from `termios`, every frame is drawn with VT100 escape codes, and each line is stored in a gap buffer, so typing in the middle of a long line doesn't shift the rest of it. Search, C syntax highlighting and saving came after.

Over SSH the first version flickered badly. I was calling `write` once per character. Building each frame in memory and writing it in one call fixed it.

## Result

- Opens a 20 MB log file in about 0.3 seconds.
- I use it for quick edits on the lab machines.
- About 2,000 lines of C.

## Tools

C with `termios` and VT100 escape codes, built with Make.

More at [ernestbaffour.com](https://ernestbaffour.com/#text-editor).
