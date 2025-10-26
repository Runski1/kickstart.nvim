# kickstart.nvim

## Introduction

Barely modified kickstart.nvim -- Work in progress

### Requirements

- Basic utils: `git`, `make`, `unzip`, C Compiler (`gcc`)
- [ripgrep](https://github.com/BurntSushi/ripgrep#installation),
  [fd-find](https://github.com/sharkdp/fd#installation)
- Clipboard tool (xclip)
- A [Nerd Font](https://www.nerdfonts.com/): optional, provides various icons

> [!NOTE]
> See [Install Recipes](#Install-Recipes) for additional Windows and Linux specific notes
> and quick install snippets

#### How to install

```sh
git clone https://github.com/Runski1/kickstart.nvim.git "${XDG_CONFIG_HOME:-$HOME/.config}"/nvim
```

### My changes

Added clangd server.cmd to launch with `--query-driver` parameter for cross platform development. 
For some reason this is not working and local nvim-lspconfig defaults have to be edited.
```
        clangd = {
          cmd = {
            'clangd',
            '--query-driver=/usr/bin/arm-none-eabi-*',
          },
        },
```
Added incremental selection for `nvim-treesitter`. This allows user to select visual blocks based on 
the code syntax.

#### Read The Friendly Documentation

Read through the `init.lua` file in your configuration folder for more
information about extending and exploring Neovim. That also includes
examples of adding popularly requested plugins.

> [!NOTE]
> For more information about a particular plugin check its repository's documentation.


### Getting Started

[The Only Video You Need to Get Started with Neovim](https://youtu.be/m8C0Cq9Uv9o)

### Useful info

* Local neovim config is located in `~/.config/nvim/` and `~/.local/share/nvim/`
* Multiple configurations can exist.
  * You can use [NVIM_APPNAME](https://neovim.io/doc/user/starting.html#%24NVIM_APPNAME)`=nvim-NAME`
    to maintain multiple configurations. For example, you can install the kickstart
    configuration in `~/.config/nvim-kickstart` and create an alias:
    ```
    alias nvim-kickstart='NVIM_APPNAME="nvim-kickstart" nvim'
    ```
* Uninstall info: [lazy.nvim uninstall](https://lazy.folke.io/usage#-uninstalling)
* Some modular setup for reference [kickstart-modular.nvim](https://github.com/dam9000/kickstart-modular.nvim)
  * Discussions on this topic can be found here:
    * [Restructure the configuration](https://github.com/nvim-lua/kickstart.nvim/issues/218)
    * [Reorganize init.lua into a multi-file setup](https://github.com/nvim-lua/kickstart.nvim/pull/473)

### Install Recipes

#### Arch Linux
```
sudo pacman -S --noconfirm --needed gcc make git ripgrep fd unzip neovim
```

To install on other platforms, see [neovim github page](https://github.com/neovim/neovim/blob/master/INSTALL.md) 
and [kickstart.nvim github](https://github.com/nvim-lua/kickstart.nvim)

