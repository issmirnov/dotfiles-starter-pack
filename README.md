# Dotfiles Starter Pack

This repo is a lightweight shadow of https://github.com/issmirnov/dotfiles

Some of the more magical components have been removed and simplified. This repo is meant as
an inspiration for someone to fork and extend for their own needs.

## Quick Tour

Each folder contains config for that particular tool.

- [bat](https://github.com/sharkdp/bat) (colorized cat) contains the config file and some custom syntaxes.
- [cheat](https://github.com/cheat/cheat) (built in tldr pages) - has a folder for custom cheatsheets and a git summodule with the community suggestions
- [espanso](https://espanso.org/) - a lightweight text expander
- fonts - simple font files that make the terminal look nicer
- git - contains the .gitconfig, hooks, some template files and the initial ignore file
- [skhd](https://github.com/koekeishiya/skhd) - MacOS hotkey daemon, used to control [yabai](), a tiling window managere
- [tmate](https://tmate.io/) - instant terminal sharing via remote tmux
- [tmux](https://github.com/tmux/tmux/wiki/Getting-Started) - terminal multiplexer, modern version of screen.
- [ubersicht](https://tracesof.net/uebersicht/) - MacOS widget engine. Used to support [status bar](https://ivans.io/better-status-bar-for-macos/)
- [vim](https://www.openvim.com/) - slightly opinionated vim config using the [vim-plug](https://github.com/junegunn/vim-plug) plugin manager
- [yabai](https://github.com/koekeishiya/yabai) - tiling window manager for MacOS
- zsh - contains config and aliases for zsh, an awesome shell.

## Prerequisites and Setup

On MacOS:

```
brew install bat cheat espanso python git \
    koekeishiya/formulae/yabai koekeishiya/formulae/skhd vim tmux tmate
    ubersicht
brew services start skhd
brew services start yabai
```

## Installation

0. [Fork](https://github.com/issmirnov/dotfiles-starter-pack/fork) this repo
1. Clone your fork to `~/.dotfiles`
2. Run `./install` from the repo. This will download
[dotbot](https://github.com/anishathalye/dotbot) and symlink everything into
place.
3. If you don't have ZSH already as your default shell, run `~/.dotfiles/zsh/setup`

If you would like to use the MacOS terminal theme, run
`open ~/.dotfiles/osx_terminal/SolarizedDark.terminal`, then open Terminal Preferences
with `Cmd + ,`, and scroll down to `SolarizedDark`. Click the "Default" button in the bottom left corner.
Now, any new terminals you open will use that theme.

## Macos Window manager stack

I've been getting a lot of questions about my MacOS window management. Here's the full stack:

- https://github.com/koekeishiya/yabai is used to tile my windows.
  - the `yabai` folder has general config - setting border colors, focus rules, etc.
  - NOTE: The top two lines are for SIP patched machines. See the inline comment.
- https://github.com/koekeishiya/skhd is a hoteky daeemon, used to interact with yabai.
  - Config folder `skhd` - note the dynamic generator. You can just copy `base` to your `.skhd`
  - This is where all the shortcuts are set up. See the inline comments for examples
  - NOTE: A lot of the shortcuts require extensive finger yoga on traditiona keyboards.
    I use a custom mechanical keyboard running QMK (https://github.com/issmirnov/qmk-keebs)
    with home row mods (https://precondition.github.io/home-row-mods), so I have a dedicated
    "Navigation" layer that has single button combos for all the crazy shortcuts.
- https://tracesof.net/uebersicht/
  - Config folder `ubersicht`
  - This sets up a custom status bar with useful indicators (https://ivans.io/better-status-bar-for-macos/)
- https://contexts.co/ - fast window switcher, activated with Ctrl+Space. I disabled the sidebar and only use the switcher.
- https://www.alfredapp.com/ or https://www.raycast.com/  - drop in replacement for spotlight. I generally only use it to lock
  my screen or open apps. If you want to go deeper, check out: https://wiki.nikitavoloboev.xyz/macos/macos-apps/alfred
