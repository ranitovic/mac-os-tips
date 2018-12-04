# Delete DS store files on Mac OS

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
