# Tomcat installation on Mac OS

1. Download the latest Tomcat core version in the zip format

2. Unip and copy it to the ~/Tomcat folder

3. Execute the commands below and open the default Tomcat site at http://127.0.0.1:8080/

---

#### Enable executable permision for all Tomcat scripts

``` console
chmod +x ~/Tomcat/bin/*.sh
```

#### Start the server

``` console
~/Tomcat/bin/startup.sh
```

#### Shutdown the server

``` console
~/Tomcat/bin/shutdown.sh
```
