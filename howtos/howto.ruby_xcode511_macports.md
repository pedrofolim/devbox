# Getting Ruby using MacPorts

This installs Ruby using [MacPorts](https://www.macports.org/).  MacPorts has a built in facility to manage multiple Ruby versions.

For simple needs, such as a system-wide availability of Ruby on a general server, MacPorts may be all that is needed.  

For more complex environments, such as a web server environment or development environment, any serious shop will undoubtedly use [RVM](http://rvm.io/).  

For managing Ruby libraries (GEM), [Bundler](http://bundler.io/) is essential, as GEM libraries will have dependencies on other GEM libraries.

## Requirements

XCode and MacPorts need to be previously instaleld prior to beginning. needs to be installed prior beginning

1. [XCode 5.1.1 on OS X 10.8.5](https://github.com/darkn3rd/devbox/blob/master/howtos/howto.xcode.md) - These are instructions for getting XCode 5.1.1 on OS X 10.8.5.
2. [MacPorts on OS X 10.8.5](https://github.com/darkn3rd/devbox/blob/master/howtos/howto.macports.md)

## Assumptions

* Unfiltered connection to Internet
* Installation is from a user account, not ```root```.
* Clean configuration; no previous version Ruby, RVM, or Bundler installed.

## The Steps

### STEP 1: Install Ruby

Install your desired version of Ruby.  Here's an example of installing both Ruby 1.9 and Ruby 2.0.

```bash
sudo port install ruby19
sudo port install ruby20
```

An installation of Ruby will have dependencies naturally.  Here's a list of the packages that are installed with ```sudo port install ruby20```:

* expat-2.1.0_0.darwin_12.x86_64.tbz2
* libiconv-1.14_0.darwin_12.x86_64.tbz2
* ncurses-5.9_2.darwin_12.x86_64.tbz2
* gettext-0.19.2_0.darwin_12.x86_64.tbz2
* gdbm-1.11_0.darwin_12.x86_64.tbz2
* libffi-3.1_4.darwin_12.x86_64.tbz2
* libyaml-0.1.6_0.darwin_12.x86_64.tbz2
* zlib-1.2.8_0.darwin_12.x86_64.tbz2
* openssl-1.0.1i_0.darwin_12.x86_64.tbz2
* readline-6.3.003_0.darwin_12.x86_64.tbz2
* ruby_select-1.0_0.darwin_12.noarch.tbz2
* ruby20-2.0.0-p481_0.darwin_12.x86_64.tbz2

### STEP 2: Select the Target Ruby

This is how we can select the desired Ruby version using just MacPorts.

```bash
sudo port select --set ruby ruby19
sudo port select --set ruby ruby20
```

### STEP 4: Verify Results

```
ruby -v
``

### STEP 5: Update Ruby GEMS and Bundler

Finally, we want to update our [Ruby GEM libraries](https://rubygems.org/), and also install [Bundler](http://bundler.io/) to manage are Ruby GEM libraries.

```bash
sudo gem update --system
sudo gem install bundler
```

This installs ```rubygems-2.4.1``` and ```bundler-1.7.2.gem``` (as of 2014-08-03).
