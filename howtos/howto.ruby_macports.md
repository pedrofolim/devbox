# Getting Ruby

These were instructions I researched in utilizing MacPorts to install and manage Ruby Versions.  These Instructions are valid as of September 5th, 2013.  This article highlights a lot of issues that can arise with open source on OS X (especially new releases).

For simple needs, such as a system-wide availability of Ruby on a Server, MacPorts may be all that is needed.  For a web server environment or development environment, any serious shop will undoubtedly use [RVM](http://rvm.io/).  For managing Ruby libraries (GEM), [Bundler](http://bundler.io/) is essential, as GEM libraries will have dependencies on other GEM libraries.

## Requirements

XCode needs to be installed prior beginning

* [XCode 5.1.1 on OS X 10.8.5](https://github.com/darkn3rd/devbox/blob/master/howtos/howto.xcode.md) - These are instructions for getting XCode 5.1.1 on OS X 10.8.5.

## Assumptions

* Unfiltered connection to Internet
* All software downloaded will be stored in ```$HOME/Downloads```
* Clean configuration; no previous version Ruby, RVM, or Bundler installed.

## PART I: Mac Ports Installation

### STEP 1: Download and Install MacPorts for OS X 10.8 "Mountain Lion"

```bash
cd $HOME/Downloads
curl -O https://distfiles.macports.org/MacPorts/MacPorts-2.3.1-10.8-MountainLion.pkg
sudo -S installer -verbose -pkg MacPorts-2.3.1-10.8-MountainLion.pkg -target /
```

### STEP 2: Update Libraries

```bash
sudo port selfupdate
sudo port upgrade outdated 
```

## PART II: Install Ruby using MacPorts

With MacPorts installed, we can install and select the desired Ruby version.

### STEP 1: Install Dependencies

```bash
sudo port install libyaml 
```

### STEP 2: Install Ruby

Install your desired version of Ruby.  Here's an example of installing both Ruby 1.9 and Ruby 2.0.

```bash
sudo port install ruby19
sudo port install ruby20
```

### STEP 3: Select the Target Ruby

This is how we can select the desired Ruby version using just MacPorts.

```bash
sudo port select --set ruby ruby19
sudo port select --set ruby ruby20
```

### STEP 4: Verify Results

```bash
. ~.profile
ruby -v
```

## PART III: Install RVM (Ruby Version Manager)

As an alternative to MacPorts ```port select --set ruby``` for managing Ruby, we can use [RVM](http://rvm.io/) with MacPorts.  

### STEP 1: Prerequisite: Update Broken GCC with XCode 4.4

These insructiosn are valid for XCode 4.4.  If you use a later version of XCode, this may not be necessary.  References for this issue and instructions come from [Ruby, RVM and Mountain Lion](https://gist.github.com/zenkay/3237860) and [Upgrading to Mountain Lion - Ruby + MacPorts ](https://coderwall.com/p/pagj2w).

```bash
sudo port selfupdate
sudo port upgrade outdated
sudo port install apple-gcc42
sudo ln -s /opt/local/bin/gcc-apple-4.2 /usr/bin/gcc-4.2
```

### STEP 2: Download and Install RVM

```bash
curl -L https://get.rvm.io | bash -s stable
```

### STEP 3: Reinstall Desired Ruby

We want to ensure that we can rebuild ruby versions.

```bash
rvm reinstall 1.9.3
rvm reinstall rbx
```

### STEP 4: Fix OpenSSL segmentation fault on OS X

This may no longer be an issue.  This was an issue on OX X with Ruby 1.9.2 and Ruby 1.9.3.  This article titled [Fix Ruby 1.9.x OpenSSL Segfault on OS X](https://coderwall.com/p/f4hyqw) cover this issue.

```bash
sudo port install openssl
rvm reinstall 1.9.3 --with-openssl-dir=/opt/local --with-opt-dir=/opt/local 
```

## PART IV: Update Ruby GEMS and Bundler

Finally, we want to update are [Ruby GEM libraries](https://rubygems.org/), and also install [Bundler](http://bundler.io/) to manage are Ruby GEM libraries.

```bash
sudo gem update --system
sudo gem install bundler
```