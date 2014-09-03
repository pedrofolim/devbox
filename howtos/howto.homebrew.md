# Install HomeBrew on OS X 10.8.5

[Homebrew](http://brew.sh/) is a popular single-user package management system that fetches either pre-compiled binaries, or compiles the source downloaded from the Internet.

## Assumptions

* XCode 5.1.1 is installed. See [XCode 5.1.1 on OS X 10.8.5](https://github.com/darkn3rd/devbox/blob/master/howtos/howto.xcode.md)
* Unfiltered connection to Internet
* All software downloaded will be stored in ```$HOME/Downloads```
* Clean configuration; no previous version of Homebrew has been installed.

## STEPS

### Install and Run Homebrew

```bash
ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
```

This will print something like:
```
==> This script will install:
/usr/local/bin/brew
/usr/local/Library/...
/usr/local/share/man/man1/brew.1

Press RETURN to continue or any other key to abort
==> /usr/bin/sudo /bin/mkdir /usr/local
Password:
==> /usr/bin/sudo /bin/chmod g+rwx /usr/local
==> /usr/bin/sudo /usr/bin/chgrp admin /usr/local
==> /usr/bin/sudo /bin/mkdir /Library/Caches/Homebrew
==> /usr/bin/sudo /bin/chmod g+rwx /Library/Caches/Homebrew
==> Downloading and installing Homebrew...
remote: Counting objects: 185728, done.
remote: Compressing objects: 100% (50947/50947), done.
```

### STEP 2: Run Brew Doctor

```bash
brew doctor
```

