# Delete DS store files on Mac OS

#### Permanently disable the creation of DS store files on network drives

```console
defaults write com.apple.desktopservices DSDontWriteNetworkStores true
```

#### Delete from the current folder

```console
find . -name .DS_Store -type f -delete && killall Finder
```

#### Delete all

```console
sudo find / -name ".DS_Store" -depth -exec rm {} \;
killall Finder
```

#### Delete from the home directory

```console
sudo find /Users/YourUsername -name ".DS_Store" -depth -exec rm {} \;
killall Finder
```
