# A snippet manager implemented in Makefile

I recently read the No Starch Press _GNU Make Book_ by John Graham-Cumming,
which inspired me to use `make` a lot more. Also I am a masochist.

## Installation

Assumming you have `make` installed, you can drop snippets anywhere on your
search path and `chmod +x` it.

## Usage

    $ snippets <target>

where target is defined in snippets. You can edit snippets to add more targets.

[![asciicast](https://asciinema.org/a/a856k76bw7ppvtv9v20xepw4t.png)](https://asciinema.org/a/a856k76bw7ppvtv9v20xepw4t)

## bash integration

In your `.bashrc`, you can enable completions:

    type -p snippets >/dev/null && eval `snippets completion`

You can also set up a hotkey to choose a snippet:

    bind '"\C-e":" snippets fzf\n"'

