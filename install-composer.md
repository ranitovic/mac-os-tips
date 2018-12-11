# Composer Installation on Mac OS

#### Verify if PHP is installed properly

```console
php -v
```

#### Download composer setup file into the current directory
```console
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
```

#### Create /usr/local/bin directory if does not exist
```console
sudo mkdir /usr/local/bin
```

#### Install composer to /usr/local/bin directory
```console
sudo php composer-setup.php --install-dir=/usr/local/bin --filename=composer
```

#### Verify installation
```console
composer -V
```

#### Change ownership of the ~/.composer directory
```console
sudo chown -R <myuser>:staff ~/.composer
```

#### Update composer
```console
sudo composer self-update
```
