# Installation

## Steps to bootstrap a new Mac

1. Install Apple's Command Line Tools, which are prerequisites for Git and Homebrew.

```zsh
xcode-select --install
```


2. Clone repo into new hidden directory.

```zsh
# Use SSH (if set up)...
git clone git@github.com:Rooknj/dev-tool-preferences.git ~/.dotfiles

# ...or use HTTPS and switch remotes later.
git clone https://github.com/Rooknj/dev-tool-preferences.git ~/.dotfiles
```


3. Create symlinks in the Home directory to the real files in the repo.

```zsh
# There are better and less manual ways to do this;
# investigate install scripts and bootstrapping tools.

ln -s ~/.dotfiles/mac/.zshrc ~/.zshrc
ln -s ~/.dotfiles/mac/.ssh/config ~/.ssh/config
# ln -s ~/.dotfiles/.gitconfig ~/.gitconfig
```

4. Install oh-my-zsh and Spaceship Prompt
    1. Install oh-my-zsh https://github.com/robbyrussell/oh-my-zsh
        - Yes you need to install it even on OSX Catalina where zsh is default
        - It gives you the different colors for directories and files
    2. Install Spaceship Prompt https://denysdovhan.com/spaceship-prompt/#npm
        - run `yarn global add spaceship-prompt`
    3. Copy and paste the .zshrc file into your home directory

5. Install Homebrew, followed by the software listed in the Brewfile.

```zsh
# These could also be in an install script.

# Install Homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Then pass in the Brewfile location...
brew bundle --file ~/.dotfiles/Brewfile

# ...or move to the directory first.
cd ~/.dotfiles && brew bundle
```

## TODO List

- Learn how to use [`defaults`](https://macos-defaults.com/#%F0%9F%99%8B-what-s-a-defaults-command) to record and restore System Preferences and other macOS configurations.
- Organize these growing steps into multiple script files.
- Automate symlinking and run script files with a bootstrapping tool like [Dotbot](https://github.com/anishathalye/dotbot).
- Revisit the list in [`.zshrc`](.zshrc) to customize the shell.
- Integrate other cloud services into your Dotfiles process (Dropbox, Google Drive, etc.).
- Find inspiration and examples in other Doffiles repositories at [dotfiles.github.io](https://dotfiles.github.io/).