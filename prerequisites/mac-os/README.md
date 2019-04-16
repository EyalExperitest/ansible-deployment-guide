
# Prepare Mac OS Machine

## Prerequisites

* add the line `export PATH="/usr/local/bin:$PATH"` to ~/.bashrc

* install brew \
  `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

* install java8 \
  `brew tap caskroom/versions`\
  `brew cask install java8`

## Remote Login

* enable ssh login: \
  System Preferences -> Sharing -> Enable Remote Login

* add ssh key (using ssh-copy-id) from executor to target machine - [see explanation](./SSH.md)
