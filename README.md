# Theme changer

An easy light to dark theme changer for my i3/kitty/neovim workflow.

# How it works

The script gets the current terminal colors, checks the background color and then handles every change of color from light to dark or viceversa.

## Wallpaper

My wallpaper setter is feh, so it just run a command for the background to set on daytime and one for the background at nightime.

## Kitty

I use [kitty](https://github.com/kovidgoyal/kitty) as a single instance listening on `/tmp/kitty` so running the command can affect all the open terminals. It sources the colorscheme file to the current instance of `kitty` and then a `sed` command replaces the configured colors on the config file.

## Neovim

Using [nvr](https://github.com/mhinz/neovim-remote) the script gets all the running neovim instances and then sends the command to change the colorscheme remotely to each of them.
