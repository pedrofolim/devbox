# The Dev Box - HowTo 

Howdy Ho! This section will have various How-To that captures sequence of steps that demonstrate, well, ahem, how-to do something.  Should I come across something technical that I might, oh, let's say, repeat someday in the future, I will collect set of steps to document how to repeat this process.

In the future, I hope the pull out some of the more useful How-To documents for inclusion in a web page.

## Background

In creating scripting and programming tutorials, I found that many environments do not include standard set of compilers, scripitng engines, virtual machines (Java, .NET), or common up-to-date GNU or POSIX tools.  For this reason, I started documenting how to get these tools onto your system.

The second part to this, is after documenting a recipee on how to install an enviornment, I may want to craft some scripts or use a system like [Boxen](https://boxen.github.com/) or other system to install a devbox environment.


## HOWTOs

### OS X (Darwin Mach XNU kernel with BSD Unix process model)

* General
  * [Updating OS X 10.8 to OS X 10.8.5](https://github.com/darkn3rd/devbox/blob/master/howtos/howto.update_osx_10_8_5.md)
  * [Testing Defaults](https://github.com/darkn3rd/devbox/blob/master/howtos/howto.check_defaults.md) - this tests gcc, cpp, java, bash, ksh, php, perl, ruby, python, tcl, and git versions.  Should you not be happy with antiquated versions, install newer versions.
* Package Management
  * [Homebrew on OS X 10.8.5](https://github.com/darkn3rd/devbox/blob/master/howtos/howto.homebrew.md)  
* Compilers (C/C++)
  * [XCode 5.1.1 on OS X 10.8.5](https://github.com/darkn3rd/devbox/blob/master/howtos/howto.xcode.md) - These are instructions for getting XCode 5.1.1 on OS X 10.8.5.
* Java Virtual Machine
  * [Getting Java 6 on Mac OS 10.8](https://github.com/darkn3rd/devbox/blob/master/howtos/howto.jre6.md)    
* Ruby
  * [Ruby, RVM, Bundler with MacPorts](https://github.com/darkn3rd/devbox/blob/master/howtos/howto.ruby_macports.md) - These are instructions that I crafted back in 2013 for installing Ruby 1.9 on MacPorts with RVM and Bundler.
  * [Getting Ruby 2 using Homebrew on OS X 10.8.5](https://github.com/darkn3rd/devbox/blob/master/howtos/howto.ruby_homebrew.md)

### Ubuntu (Debian Linux)

* Ruby-On-Rails
  * [Getting Ruby-on-Rails on Ubuntu](https://github.com/darkn3rd/devbox/blob/master/howtos/howto.rails_ubuntu.md)

### Windows NT Systems

* Ruby
  * [Installing Ruby 1.9 on Windows 7](https://github.com/darkn3rd/devbox/blob/master/howtos/howto.ruby_windows.md)