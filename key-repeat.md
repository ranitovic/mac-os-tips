# Enable key repeat on the keybord

#### Disable press-and-hold for keys in favor of key repeat

```console
defaults write NSGlobalDomain ApplePressAndHoldEnabled -bool false
```
#### OPTIONAL - Set the keyboard repeat rate in console insted of the System Settings

```console
defaults write NSGlobalDomain KeyRepeat -int 2
defaults write NSGlobalDomain InitialKeyRepeat -int 16
```
