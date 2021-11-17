# Homebrew installation on Mac OS Catalina

#### Install Homebrew and close terminal

``` console
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

sudo mkdir /usr/local/log
sudo mkdir /usr/local/log/php
sudo chgrp -R staff /usr/local/log/php
sudo chmod -R ug+w /usr/local/log/php/
```

#### Check Homebrew Version (Homebrew 3.3.4) and status

``` console
brew -v
brew doctor
```

#### Install tree with the brew install command (optional)

``` console
brew install tree
which tree
tree --version
```

#### Start Apache, check http://127.0.0.1/, remove Apache, reboot

``` console
sudo apachectl start
sudo launchctl unload -w /System/Library/LaunchDaemons/org.apache.httpd.plist
cat /private/var/db/com.apple.xpc.launchd/disabled.plist
sudo reboot
```



#### Install Apache

``` console
sudo mkdir /usr/local/log
sudo mkdir /usr/local/log/httpd
sudo chgrp -R staff /usr/local/log/httpd
sudo chmod -R ug+w /usr/local/log/httpd/

sudo apachectl stop
sudo launchctl unload -w /System/Library/LaunchDaemons/org.apache.httpd.plist 2&gt;/dev/null

brew install httpd

brew services start httpd
```

#### Configure Apache

``` console
sudo nano /usr/local/etc/httpd/httpd.conf
```

``` apacheconf
LoadModule deflate_module lib/httpd/modules/mod_deflate.so
LoadModule vhost_alias_module lib/httpd/modules/mod_vhost_alias.so
LoadModule rewrite_module lib/httpd/modules/mod_rewrite.so
LoadModule php7_module /usr/local/opt/php@7.2/lib/httpd/modules/libphp7.so

User YOURUSERNAME
Group staff

ServerAdmin admin@yoursite.com
ServerName localhost

<IfModule dir_module>
    DirectoryIndex index.php index.html
</IfModule>

<FilesMatch \.php$>
    SetHandler application/x-httpd-php
</FilesMatch>

Include /usr/local/etc/httpd/extra/httpd-vhosts.conf
```

#### Configure Apache virtual hosts

``` console
sudo nano /usr/local/etc/httpd/extra/httpd-vhosts.conf
```

``` apacheconf
<VirtualHost *:80>
    DocumentRoot "/Users/YOURUSERNAME/Sites/Default"
    ServerName localhost
    ServerAlias yourlocaltestdomain.com
    <Directory "/Users/YOURUSERNAME/Sites/Default">
        Options FollowSymLinks Multiviews Indexes
        MultiviewsMatch Any
        AllowOverride All
        Require all granted
    </Directory>
    ErrorLog "/Users/YOURUSERNAME/Sites/Default/apache-error-log.txt"
    CustomLog "/Users/YOURUSERNAME/Sites/Default/apache-access-log" common
</VirtualHost>

<VirtualHost *:80>
    DocumentRoot "/Users/YOURUSERNAME/Sites/SUBDOMAINSITE/public"
    ServerName SUBDOMAINSITE.localhost
    ServerAlias *.SUBDOMAINSITE.localhost
    <Directory "/Users/YOURUSERNAME/Sites/SUBDOMAINSITE/public">
        Options FollowSymLinks Multiviews Indexes
        MultiviewsMatch Any
        AllowOverride All
        Require all granted
    </Directory>
    ErrorLog "/Users/YOURUSERNAME/Sites/SUBDOMAINSITE/apache-error-log.txt"
    CustomLog "/Users/YOURUSERNAME/Sites/SUBDOMAINSITE/apache-access-log" common
</VirtualHost>

```

#### Install PHP

``` console
brew install php@7.2
brew services start php@7.2
```

Location of php.ini:
/usr/local/etc/php/7.2/php.ini
