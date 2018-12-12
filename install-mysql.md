# MySQL installation and configuration on Mac OS

1. Download the MySQL Community Server 5.7.24 for macOS 10.14 (x86, 64-bit), DMG Archive

2. Double-click on the DMG archive to start the installation

3. Copy the temporary generated password for root@localhost

4. Go to System Preferences, select MySQL and start the MySQL server

---

#### Setup the path and alias in .bash_profile

``` console
export PATH=${PATH}:/usr/local/mysql/bin/
alias my='/usr/local/mysql/bin/mysql -u root'
```

#### Run the MySQL client and enter the temporary password when prompted

``` console
mysql -u root -p
```

#### Once logged in, remove the root password and expiration

``` sql
ALTER USER `root`@`localhost` IDENTIFIED BY '', `root`@`localhost` PASSWORD EXPIRE NEVER;
```
