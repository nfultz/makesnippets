# A snippet manager implemented in Makefile

I recently read the No Starch Press _GNU Make Book_ by John Graham-Cumming,
which inspired me to use `make` a lot more. Also I am a masochist. This project
provides five generic `make` targets for easy access to code snippets:

  * `help` lists the available targets.
  * `completion` produces the bash command for autocompletion
  * `fzf` lists the available targets in fuzzy finder, and executes the
    selected one.
  * `edit` opens the snippet file in `$EDITOR`
  * `install` places the snippet file into the system include directory.

It also sets better defaults for code snippets:

  * All targets are `PHONY`
  * Uses a single shell per snippet instead of per line - you can use shell
    variables now.
  * Default target is help.


## Installation

Option 1: Assumming you have `make` installed, you can drop snippets anywhere
on your search path and `chmod +x` it. You can then edit the file and add your
own snippets.

Option 2: You can install snippets as a library using the command:

    sudo make -f snippets install

You can then `-include` it in other makefiles and automatically add the
functionality to them. See `example`

Option 3: Unsafe one liner

    sudo wget -P /usr/local/include https://github.com/nfultz/makesnippets/raw/master/snippets


## Usage

    $ snippets <target>

where target is defined in snippets. You can edit snippets to add more targets.

[![asciicast](https://asciinema.org/a/a856k76bw7ppvtv9v20xepw4t.png)](https://asciinema.org/a/a856k76bw7ppvtv9v20xepw4t)

## bash integration

In your `.bashrc`, you can enable completions:

    type -p snippets >/dev/null && eval `snippets completion`

You can also set up a hotkey to choose a snippet:

    bind '"\C-e":" snippets fzf\n"'

