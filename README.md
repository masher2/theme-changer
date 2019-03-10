# Theme changer

An easy light to dark theme changer for my i3/kitty/neovim workflow.

# How it works

The script gets the current terminal colors, checks the background color and then handles every change of color from light to dark or viceversa.

## Wallpaper

Reads from a config file a list of wallpapers, gets one randomly according to the theme that it's setting and pipe it into `feh` to change it.

After changing the wallpaper it also calls `betterlockscreen -u` with the same wallpaper to update the lockscreen too. This is done as the last step as it's the most time consuming.

My config file looks something like this:

```
bright:
    island.png
    buildings.png
    desert.png

shine:
    island 2.png
    blackhole.png
    stars 1.png

```

## Kitty

I use [kitty](https://github.com/kovidgoyal/kitty) as a single instance listening on `/tmp/kitty` so running the command can affect all the open terminals. It sources the colorscheme file to the current instance of `kitty` and then a `sed` command replaces the configured colors on the config file.

## Neovim

Using [nvr](https://github.com/mhinz/neovim-remote) the script gets all the running neovim instances and then sends the command to change the colorscheme remotely to each of them.
