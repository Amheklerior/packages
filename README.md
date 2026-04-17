# Packages

This repository contains the list of packages and apps I use on MacOS.

The [Brewfile](./Brewfile) defines all of them in a nice and readable way, including Mac App Store applications and VSCode extensions.
The whole bundle is going to be installed via [Homebrew](https://brew.sh/).

## Getting Started

First, install Homebrew on your system:

```bash
# first, install homebrew on your system and make it available in the bin path 
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
export PATH=/opt/homebrew/bin:$PATH

# make homebrew available in your PATH
eval $(/opt/homebrew/bin/brew shellenv zsh)
```

Then, download the bundle and launch the installation process:

```bash
# download the Brewfile to ~/Brewfile
curl -o $HOME/Brewfile https://raw.githubusercontent.com/Amheklerior/packages/HEAD/Brewfile

# and install the whole bundle
brew bundle --global --verbose
```

<!-- [!note]: Once SSH keys are setup, clone this repo and symlink the Brewfile into `XDG_CONFIG_HOME/homebrew` or `$HOME/.homebrew`. -->

## Maintaining the Brewfile

The following commands are useful in keeping things in check.

```bash
# check how far the current system deviates from the Brewfile's defined list
# NOTE: the --verbose flag will list the offending items
brew bundle check --verbose

# uninstall any package which is NOT listed in the Brewfile
brew bundle cleanup
```
