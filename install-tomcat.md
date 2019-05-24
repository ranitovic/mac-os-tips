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

---

## Configure Eclipse to use our Tomcat server

1. Change perspective to Java EE

2. Select Servers tab and create a new server, choose Tomcat version that has been installed

3. Create a new Dynamic Web Project called Services

4. Copy ant, src, and WebContent folders from the original project

5. Update database credentials in WebContent/META-INF/context.htm

6. Run the Tomcat server within Eclipse and test one URL: http://localhost:8080/Services/onlineStatus

7. Right click on ant/build.xml and choose Run As Ant Build to deploy the production jar file
