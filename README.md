# Packages

My list of packages to be installed on MacOS via [Homebrew](https://brew.sh/), for my dev setup.

> [!IMPORTANT]
> If you want to keep track of your package list,
> [fork](https://github.com/Amheklerior/packages/fork) the repo first.

## Getting Started

First, install Homebrew on your system:

```bash
# first, install homebrew on your system and make it available in the bin path 
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
export PATH=/opt/homebrew/bin:$PATH

# make homebrew available in your PATH
eval $(/opt/homebrew/bin/brew shellenv zsh)
```

Then, download the file and make any desired changes:

```bash
# download the Brewfile to ~/Brewfile
curl -o $HOME/Brewfile https://raw.githubusercontent.com/Amheklerior/packages/HEAD/Brewfile

# edit the file
vim $HOME/Brewfile
```

Finally, trigger the installation process:

```bash
# install all the listed packages
brew bundle --global
```

## The Bigger Picture

The [Brewfile](./Brewfile) defines a list of packages to be installed on the system.
It allows me to declaratively define, in a single place:

- binaries (`brew "xyz"`),
- cask applications (`cask "xyz"`),
- _Mac App Store_ specific apps (`mas "xyz"`),
- _Go_ tools (`go "xyz"`),
- _VS Code_ extentions (`vscode "xyz"`).

It is used as part of my [System Environment Setup](https://github.com/Amheklerior/sysenv)
for quickly setting up new machines.

> [!TIP]
>
> ```bash
> # check how far the current system deviates from the Brewfile's defined list
> # NOTE: the --verbose flag will list all offending items
> brew bundle check --verbose
> 
> # uninstall any package which is NOT listed in the Brewfile
> brew bundle cleanup
> ```
