# SeedCode Starter
Starting point for working on SeedCode projects. This includes SeedCode's dev environment.


Core Dev Software
=======================

Download and install the following applications
------------

**VirtualBox:**
https://www.virtualbox.org/wiki/Downloads

**Vagrant:**
https://www.vagrantup.com/downloads.html

**SourceTree:**
https://www.sourcetreeapp.com

**MonoSnap (for screencasts):**
https://www.monosnap.com

Configuration and cleanup using the terminal
------------
**Launch Terminal app:**

**Create a global git ignore file:**
```shell
git config --global core.excludesfile ~/.gitignore_global
touch ~/.gitignore_global
nano ~/.gitignore_global
```

Then paste the following:
```
## Begin ignore list ##
# OS generated files #
######################
.DS_Store
.DS_Store?
._*
.Spotlight-V100
.Trashes
ehthumbs.db
Thumbs.db

# Vagrant generated files #
######################
.vagrant
## End ignore list ##
```

press "ctl" + "x" to exit, then “y” to save and "enter" to confirm.

**Add user email and name to git config file:**
```shell
nano ~/.gitconfig
```

Fill in name and email. When done "ctrl" + "x" to exit, then “y” to save and "enter" to confirm.

Once you have the project repo URL from Kiln add the repo to SourceTree and pull the project:

Click "New Repository"

Then "Clone from URL"

Paste in the repo URL and choose a folder on your computer to clone the repo to

Then click "Clone"

Navigate back to the Terminal App and excecute the following commands:

**Vagrant plugins:**
```shell
vagrant plugin install vagrant-hostsupdater
vagrant plugin install vagrant-vbguest
```

**How to start vagrant:**

Navigate to your project repo, then navigate to the vagrant folder within that. Then run the command vagrant up...
```shell
cd yourproject/vagrant
vagrant up
```
This may take several minutes as it will download the base image and install everything. This will only take this long the first time.

If you need to activate SSL for the development environment run the following commands from the context of the vagrant folder replace the email and domain placeholders with your specific data...
```shell
vagrant ssh
cd /vagrant
grunt ssl:YourEmail:YourDomain
```

Once complete you can exit out of your vagrant ssh session by executing the command
```shell
exit
```

Vagrant can be stopped by typing
```shell
vagrant halt
```

To start vagrant again (and the dev environment) simply navigate to the vagrant folder in the terminal and type
```shell
vagrant up
```
