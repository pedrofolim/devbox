# Vagrant

These are simple steps to create and configure a vagrant environment using VirtualBox.

1. Install VirtualBox
2. Install Vagrant
3. (optional) Download target `box` image.
3. Configure Vagrantfile
   * Configure to use the downloaded `box` image
   * Optionally configure Network and VM Settings
   * Optionally configure provisioner (Chef, Puppet, etc.).
4. Startup Vagrant and Experiment

# Box Files

You can get faster performance if boxes installed from local directory.  You can find a bunch of boxes at http://www.vagrantbox.es/.

This is what I do:

```bash
$ BOXURL={Your box URL goes here}
$ mkdir ~boxen
$ cd ~boxen
$ curl -O $BOXURL
```

# OS X

You can download and install Virtualbox and Vagrant.  Personally, I like to use [Homebrew](http://brew.sh/) and [Cask](http://caskroom.io/) for installation of these pieces.

```bash
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
$ brew update
$ brew doctor
$ brew install caskroom/cask/brew-cask
```

Once the package management systems are install, I can install the components.

```bash
$ sudo brew cask install virtualbox
$ brew cask install vagrant
```
