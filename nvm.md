# NVM installation on Mac OS

#### Install nvm

``` console
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.0/install.sh | bash
```

Exit the Shell

Open a Shell

#### Verify Installation:

``` console
command -v nvm
```

#### To uninstall it later:

``` console
nvm use system
npm uninstall -g a_module
```

#### Show all available LTS versions of node.js:

``` console
nvm ls-remote
```

#### Shows all locally installed versions:

``` console
nvm ls
```

#### Install the latest version of node.js:

``` console
nvm install node
```

#### Install a specific version of node.js:

``` console
nvm install 8.16.2
```

#### Set node.js to the latest version:

``` console
nvm use node
```

#### Set node.js to the specific version:

``` console
nvm use 8.16.2
```

#### Installs the latest version of npm on the current node version:

``` console
nvm install-latest-npm
```
