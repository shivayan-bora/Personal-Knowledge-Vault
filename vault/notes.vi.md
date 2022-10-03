---
id: 8pxj3vsxxi38suycj9b9stb
title: Vi
desc: ''
updated: 1663902373455
created: 1663835826192
---

## What is Vi?

Vi is a text editor that is available on most Linux distributions. It is a command-line based text editor. It is a very powerful text editor and is used by many developers.

## Modes

- **Command Mode**: The default mode when you open the editor. You can use the commands to navigate and edit the file e.g. copy or paste lines or delete a line or a word or to navigate between lines.

You can move around the file using the arrow keys or the `hjkl` keys.

![Moving around](/assets/images/2022-09-22-14-11-30.png)

Delete a character using `x`.

Delete a line using `dd`.

Copy a line using `yy`.

Paste a line using `p`.

Scroll down using `Ctrl + d`.

Scroll up using `Ctrl + u`.

`:` is used to take you to the prompt where you can enter a command.

To save the file, use `:w`. You can optionally specify the file name to save the file as. For example, `:w new_file.txt`.

To discard the changes, use `:q`.

To save and quit, use `:wq`.

If you want to find a word in the file, use `/` followed by the word. For example, `/hello`. When you do this, the cursor will move to the first occurrence of the word. To move to the next occurrence, use `n`.

- **Insert Mode**: You can use this mode to insert text into the file i.e. insert contents to the file. You can switch to this mode by pressing `i` or `a` or `o` or `I` or `A` or `O`.

To switch back to the command mode, press `Esc`.
