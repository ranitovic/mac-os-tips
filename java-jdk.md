# Install and configure multiple Java JDK's on Mac OS

<br />

#### Download and install Java JDK's
From the Oracle site download and install all required JDK versions

<br />

#### Show currently used JDK

```console
/usr/libexec/java_home
```

<br />

#### List available JDK's

```console
/usr/libexec/java_home -V
```

<br />

#### Add this to the .bash_profile to change JDK versions

```console
alias j8="export JAVA_HOME=`/usr/libexec/java_home -v 1.8`; java -version"
alias j9="export JAVA_HOME=`/usr/libexec/java_home -v 9`; java -version"
export PATH=${PATH}:/usr/local/mysql/bin/:${HOME}/.composer/vendor/bin:${JAVA_HOME}/bin
```
