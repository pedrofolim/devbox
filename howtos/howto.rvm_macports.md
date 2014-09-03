# Using RVM on MacPorts

This guide documents my experience using [RVM](http://rvm.io/) on [MacPorts](https://www.macports.org/).  Generally, MacPorts is adequate for system-wide availability of Ruby on a server.  For environments that do web server development, [Ruby Version Manager](http://rvm.io/) will likely be the core tool required for managing different versions of Ruby along with unique Gemsets, i.e. versions of Ruby libraries.

For managing Ruby libraries (GEM), [Bundler](http://bundler.io/) is essential, as GEM libraries will have dependencies on other GEM libraries.

## Requirements

1. [XCode 5.1.1 on OS X 10.8.5](https://github.com/darkn3rd/devbox/blob/master/howtos/howto.xcode.md) - These are instructions for getting XCode 5.1.1 on OS X 10.8.5.
2. [MacPorts on OS X 10.8.5](https://github.com/darkn3rd/devbox/blob/master/howtos/howto.macports.md)

## Assumptions

* Unfiltered connection to Internet
* All software downloaded will be stored in ```$HOME/Downloads```
* Clean configuration; no previous version Ruby, RVM, or Bundler installed.

## The Steps

### STEP 1: Download and Install RVM

You can do this in just one command:

```bash
\curl -sSL https://get.rvm.io | bash -s stable
```
### STEP 2: Install your Rubies

```bash
rvm install 2.1
rvm install 1.9.3
```

If you want to check out what Rubies are available, you can:

```bash
rvm list rubies
```

### STEP 3: Set the Default Ruby

You can choose the default Ruby.

```bash
rvm default 2.1
```

And then test the version installed:

```
ruby -v
ruby 2.1.2p95 (2014-05-08 revision 45877) [x86_64-darwin13.0]
```

The version such as the one above will be accessed from ```$HOME/.rvm/rubies/ruby-2.1.2/bin/ruby"```.

### STEP 4: Update Gems and Install Bundler

Finally, we want to update our [Ruby GEM libraries](https://rubygems.org/), and also install [Bundler](http://bundler.io/) to manage are Ruby GEM libraries.  

Note that even if we did this before, we need to do this for every different version of Ruby that we wish to use.  The Gems are maintained seperately for each version of Ruby installed.

```bash
sudo gem update --system
sudo gem install bundler
```

This installs ```rubygems-2.4.1``` and ```bundler-1.7.2.gem``` (as of 2014-08-03).


