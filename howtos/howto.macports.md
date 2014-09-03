# Install MacPorts on OS X 10.8.5

[MacPorts](https://www.macports.org/) is a popular system level package management system that will download and compile source code for OS X.  The packages will be installed for all users.

## Assumptions

* XCode 5.1.1 is installed. See [XCode 5.1.1 on OS X 10.8.5](https://github.com/darkn3rd/devbox/blob/master/howtos/howto.xcode.md)
* Unfiltered connection to Internet
* All software downloaded will be stored in ```$HOME/Downloads```
* Installation is from a user account, not ```root```.
* Clean configuration; no previous version of Homebrew has been installed.

## STEPS

### STEP 1: Downloard MacPorts

Download the latest package.  This is MacPorts 2.3.1 as of September 3rd, 2014.

```bash
curl -O https://distfiles.macports.org/MacPorts/MacPorts-2.3.1-10.8-MountainLion.pkg
```

### STEP 2: Install Mac Ports

```bash
sudo -S installer -verbose -pkg $HOME/Downloads/MacPorts-2.3.1-10.8-MountainLion.pkg -target /
```

### STEP 3: Configure and Source Login Scripts

On a new system without an initial ```$HOME/.profile```, the ```$PATH``` is not updated to include the new software.  Thus this will have to be done manually.

```bash
echo 'export PATH="$PATH:/opt/local/bin"' >> $HOME/.profile
source $HOME/.profile
```

### STEP 4: Update Mac Ports

```bash
sudo port -v selfupdate
```