# Install and configure Git on Mac OS

#### Git is automatically installed with Xcode or Xcode command line tools

#### Configure Git globally
```console
git config --global user.name "MyName"
git config --global user.email "myname@mysite.com"
git config --list
```

***

#### Create a new project

Create an empty project on the GitHub without readme or git ignore files.

Go to directory on developer machine where new project is created
Execute the following commands:

```console
git init
git add .
git commit -m "Initial Commit"
git remote add origin git@github.com:mygithubusername/name-of-your-newly-created-project.git
git push -u origin master
```

***

#### Clone an existing project hosted on the GitHub

Go to a directory where existing project will be cloned

```console
git clone git@github.com:mygithubusername/name-of-your-github-project.git
```

***

#### Create a GitHub deployment SSH key

If we need to deploy our application using GitHub,
the most secure way is to create a read-only deployment key for that repository.

First, let's create a key pair on the production server

```console
cd /home/your-user/.ssh
ssh-keygen -t rsa -C "git@your-site.com"
```

Go to repository in GitHub, choose "Settings", then "Deploy keys".
Paste the public key generated above, and it will be the read only deployment key for that repository.

***

#### Create the Git ignore file in the home directory

```console
mkdir ~/.git
touch ~/.git/.gitignore_global
echo ".DS_Store" >> ~/.git/.gitignore_global
echo "._.DS_Store" >> ~/.git/.gitignore_global
echo "**/.DS_Store" >> ~/.git/.gitignore_global
echo "**/._.DS_Store" >> ~/.git/.gitignore_global
git config --global core.excludesfile ~/.git/.gitignore_global
```
