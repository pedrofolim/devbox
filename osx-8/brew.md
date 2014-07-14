# HomeBrew on Mountain Lion

This is a set of snippets used to capture installation of packages uses HomeBrew on Mac OS X 10.8.5 (Mountain Lion) as of July, 2014.

I specify the date because HomeBrew scripts and packages may change at any moment as they are fetched from the Internet.

# Unix Shell and Unix Tools

## POSIX Shell for Portable Scripts

Install a POSIX shell for Mac OS X.

```bash
$ brew install dash
```

On my run, this fetched some tarball from Australia.

```bash
==> Downloading http://gondor.apana.org.au/~herbert/dash/files/dash-0.5.7.tar.gz
######################################################################## 100.0%
==> ./configure --prefix=/usr/local/Cellar/dash/0.5.7 --with-libedit --enable-fnmatch --enable-glob
==> make
==> make install
🍺   /usr/local/Cellar/dash/0.5.7: 5 files, 220K, built in 7 seconds
```

Dash (Debian Ash) does not have a version parameter, so tested to see if it existed using man pages.  Sure enough man pages were installed.

```bash
$ man dash | head -20

DASH(1)                   BSD General Commands Manual                  DASH(1)

NAME
     dash -- command interpreter (shell)

SYNOPSIS
     dash [-aCefnuvxIimqVEb] [+aCefnuvxIimqVEb] [-o option_name]
          [+o option_name] [command_file [argument ...]]
     dash -c [-aCefnuvxIimqVEb] [+aCefnuvxIimqVEb] [-o option_name]
Joaquins-MacBook-Pro:devbox joaquinmenchaca$ man dash | head -20

DASH(1)                   BSD General Commands Manual                  DASH(1)

NAME
     dash -- command interpreter (shell)

SYNOPSIS
     dash [-aCefnuvxIimqVEb] [+aCefnuvxIimqVEb] [-o option_name]
          [+o option_name] [command_file [argument ...]]
     dash -c [-aCefnuvxIimqVEb] [+aCefnuvxIimqVEb] [-o option_name]
          [+o option_name] command_string [command_name [argument ...]]
     dash -s [-aCefnuvxIimqVEb] [+aCefnuvxIimqVEb] [-o option_name]
          [+o option_name] [argument ...]

DESCRIPTION
     dash is the standard command interpreter for the system.  The current
     version of dash is in the process of being changed to conform with the
     POSIX 1003.2 and 1003.2a specifications for the shell.  This version has
     many features which make it appear similar in some respects to the Korn
     shell, but it is not a Korn shell clone (see ksh(1)).  Only features des-

```

## Korn Shell

The Korn shell available on Mac OS X is from 2011.

```bash
$ /bin/ksh --version
  version         sh (AT&T Research) 93u 2011-02-08
```

Let's fetch something more recent.

```bash
$ brew install ksh
```

This fetches a precompiled bottle.

```bash
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/ksh-93u+.mountain_lion.bottle.1.tar.gz
######################################################################## 100.0%
==> Pouring ksh-93u+.mountain_lion.bottle.1.tar.gz
==> Caveats
We have agreed to the Eclipse Public License on your behalf.
If this is unacceptable for any reason, please uninstall.
==> Summary
🍺   /usr/local/Cellar/ksh/93u+: 4 files, 1.5M
```



```bash
$ ksh --version
  version         sh (AT&T Research) 93u+ 2012-08-01
```

## Bash 4.3 (Not default Bash 3.x)

```bash
$ bin/bash --version | head -1 
GNU bash, version 3.2.48(1)-release (x86_64-apple-darwin12)
$ brew install bash
==> Downloading http://ftpmirror.gnu.org/bash/bash-4.3.tar.gz
######################################################################## 100.0%
==> Downloading https://gist.githubusercontent.com/jacknagel/c1cf23775c774e2b4b6d/raw/abd9bd4289bb443684ba26d5a2d3fb9449bbfa90/bash-4.3.18.diff
######################################################################## 100.0%
==> Patching
patching file arrayfunc.c
patching file bashline.c
patching file externs.h
patching file jobs.c
patching file lib/glob/glob.c
patching file lib/glob/gmisc.c
patching file lib/readline/display.c
patching file lib/readline/readline.c
patching file lib/sh/shquote.c
patching file parse.y
patching file patchlevel.h
patching file pcomplete.c
patching file subst.c
patching file test.c
patching file trap.c
patching file variables.c
patching file y.tab.c
==> ./configure --prefix=/usr/local/Cellar/bash/4.3.18 --with-installed-readline
==> make install
==> Caveats
In order to use this build of bash as your login shell,
it must be added to /etc/shells.
==> Summary
🍺  /usr/local/Cellar/bash/4.3.18: 59 files, 7.5M, built in 39 seconds
$ bash --version | head -1 
GNU bash, version 4.3.18(1)-release (x86_64-apple-darwin12.5.0)
$ sudo vi /etc/shells
$ cat /etc/shells
# List of acceptable shells for chpass(1).
# Ftpd will not allow users to connect who are not using
# one of these shells.

#/bin/bash
/usr/local/bin/bash
/bin/csh
/bin/ksh
/bin/sh
/bin/tcsh
```

A patch is required to get Bash 4.3 to work on Mac OS X.  I will dig into this later.

# Scripting Engines

## Python 2

```bash
$ brew install python
==> Installing dependencies for python: readline, sqlite, gdbm, openssl
==> Installing python dependency: readline
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/readline-6.3.6.mountain_lion.bottle.tar.gz
######################################################################## 100.0%
==> Pouring readline-6.3.6.mountain_lion.bottle.tar.gz
==> Caveats
This formula is keg-only, so it was not symlinked into /usr/local.

OS X provides the BSD libedit library, which shadows libreadline.
In order to prevent conflicts when programs look for libreadline we are
defaulting this GNU Readline installation to keg-only.

Generally there are no consequences of this for you. If you build your
own software and it requires this formula, you'll need to add to your
build variables:

    LDFLAGS:  -L/usr/local/opt/readline/lib
    CPPFLAGS: -I/usr/local/opt/readline/include

==> Summary
🍺  /usr/local/Cellar/readline/6.3.6: 40 files, 2.1M
==> Installing python dependency: sqlite
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/sqlite-3.8.5.mountain_lion.bottle.tar.gz
######################################################################## 100.0%
==> Pouring sqlite-3.8.5.mountain_lion.bottle.tar.gz
==> Caveats
This formula is keg-only, so it was not symlinked into /usr/local.

Mac OS X already provides this software and installing another version in
parallel can cause all kinds of trouble.

OS X provides an older sqlite3.

Generally there are no consequences of this for you. If you build your
own software and it requires this formula, you'll need to add to your
build variables:

    LDFLAGS:  -L/usr/local/opt/sqlite/lib
    CPPFLAGS: -I/usr/local/opt/sqlite/include

==> Summary
🍺  /usr/local/Cellar/sqlite/3.8.5: 9 files, 2.1M
==> Installing python dependency: gdbm
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/gdbm-1.11.mountain_lion.bottle.tar.gz
######################################################################## 100.0%
==> Pouring gdbm-1.11.mountain_lion.bottle.tar.gz
🍺  /usr/local/Cellar/gdbm/1.11: 16 files, 420K
==> Installing python dependency: openssl
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/openssl-1.0.1h.mountain_lion.bottle.tar.gz
######################################################################## 100.0%
==> Pouring openssl-1.0.1h.mountain_lion.bottle.tar.gz
==> Caveats
A CA file has been bootstrapped using certificates from the system
keychain. To add additional certificates, place .pem files in
  /usr/local/etc/openssl/certs

and run
  /usr/local/opt/openssl/bin/c_rehash

This formula is keg-only, so it was not symlinked into /usr/local.

Mac OS X already provides this software and installing another version in
parallel can cause all kinds of trouble.

The OpenSSL provided by OS X is too old for some software.

Generally there are no consequences of this for you. If you build your
own software and it requires this formula, you'll need to add to your
build variables:

    LDFLAGS:  -L/usr/local/opt/openssl/lib
    CPPFLAGS: -I/usr/local/opt/openssl/include

==> Summary
🍺  /usr/local/Cellar/openssl/1.0.1h: 429 files, 15M
==> Installing python
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/python-2.7.8.mountain_lion.bottle.tar.gz
######################################################################## 100.0%
==> Pouring python-2.7.8.mountain_lion.bottle.tar.gz
==> Caveats
Setuptools and Pip have been installed. To update them
  pip install --upgrade setuptools
  pip install --upgrade pip

You can install Python packages with
  pip install <package>

They will install into the site-package directory
  /usr/local/lib/python2.7/site-packages

See: https://github.com/Homebrew/homebrew/wiki/Homebrew-and-Python

.app bundles were installed.
Run `brew linkapps` to symlink these to /Applications.
==> /usr/local/Cellar/python/2.7.8/bin/python -s setup.py --no-user-cfg install --force --verbose --install-scripts=/usr/local/Cellar/python/2.7.8/bin --install-lib=/usr/local/lib/p
==> /usr/local/Cellar/python/2.7.8/bin/python -s setup.py --no-user-cfg install --force --verbose --install-scripts=/usr/local/Cellar/python/2.7.8/bin --install-lib=/usr/local/lib/p
==> Summary
🍺  /usr/local/Cellar/python/2.7.8: 4654 files, 75M

$ pip install virtualenv
Downloading/unpacking virtualenv
  Downloading virtualenv-1.11.6-py2.py3-none-any.whl (1.6MB): 1.6MB downloaded
Installing collected packages: virtualenv
Successfully installed virtualenv
Cleaning up...
```

## Python 3

```bash
$ brew install python3
==> Installing python3 dependency: xz
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/xz-5.0.5.mountain_lion.bottle.3.tar.gz
######################################################################## 100.0%
==> Pouring xz-5.0.5.mountain_lion.bottle.3.tar.gz
🍺  /usr/local/Cellar/xz/5.0.5: 58 files, 1.5M
==> Installing python3
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/python3-3.4.1.mountain_lion.bottle.tar.gz
######################################################################## 100.0%
==> Pouring python3-3.4.1.mountain_lion.bottle.tar.gz
==> Caveats
Pip has been installed. To update it
  pip3 install --upgrade pip

You can install Python packages with
  pip3 install <package>

They will install into the site-package directory
  /usr/local/lib/python3.4/site-packages

See: https://github.com/Homebrew/homebrew/wiki/Homebrew-and-Python

.app bundles were installed.
Run `brew linkapps` to symlink these to /Applications.
==> /usr/local/Cellar/python3/3.4.1/bin/python3 -m ensurepip --upgrade
==> Summary
🍺  /usr/local/Cellar/python3/3.4.1: 3845 files, 67M

$ pip3 install --upgrade setuptools
Downloading/unpacking setuptools from https://pypi.python.org/packages/3.4/s/setuptools/setuptools-5.4.1-py2.py3-none-any.whl#md5=5b7b07029ad2285d1cbf809a8ceaea08
  Downloading setuptools-5.4.1-py2.py3-none-any.whl (528kB): 528kB downloaded
Installing collected packages: setuptools
  Found existing installation: setuptools 2.1
    Uninstalling setuptools:
      Successfully uninstalled setuptools
Successfully installed setuptools
Cleaning up...

$ pip3 install virtualenv
Downloading/unpacking virtualenv
  Downloading virtualenv-1.11.6-py2.py3-none-any.whl (1.6MB): 1.6MB downloaded
Installing collected packages: virtualenv
Successfully installed virtualenv
Cleaning up...

$ virtualenv venv
New python executable in venv/bin/python2.7
Also creating executable in venv/bin/python
Installing setuptools, pip...done.
```

## Ruby 2

```bash
$ brew install ruby
==> Installing ruby dependency: libyaml
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/libyaml-0.1.6.mountain_lion.bottle.tar.gz
######################################################################## 100.0%
==> Pouring libyaml-0.1.6.mountain_lion.bottle.tar.gz
🍺  /usr/local/Cellar/libyaml/0.1.6: 7 files, 352K
==> Installing ruby
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/ruby-2.1.2_2.mountain_lion.bottle.1.tar.gz
######################################################################## 100.0%
==> Pouring ruby-2.1.2_2.mountain_lion.bottle.1.tar.gz
🍺  /usr/local/Cellar/ruby/2.1.2_2: 942 files, 20M

$ ruby --version
ruby 2.1.2p95 (2014-05-08 revision 45877) [x86_64-darwin12.0]

$ gem --version
2.2.2
```

# Web Clients

$ brew cask install firefox
==> We need to make Caskroom for the first time at /opt/homebrew-cask/Caskroom
==> We'll set permissions properly so we won't need sudo in the future
Password:
==> Downloading https://download.mozilla.org/?product=firefox-latest&os=osx&lang=en-US
######################################################################## 100.0%
==> Symlinking App 'Firefox.app' to '/Users/hansolo/Applications/Firefox.app'
🍺  firefox installed to '/opt/homebrew-cask/Caskroom/firefox/latest' (113 files, 141M)

$ brew cask install google-chrome
==> Downloading https://dl.google.com/chrome/mac/stable/GGRO/googlechrome.dmg
######################################################################## 100.0%
==> Symlinking App 'Google Chrome.app' to '/Users/hansolo/Applications/Google Chrome.app'
🍺  google-chrome installed to '/opt/homebrew-cask/Caskroom/google-chrome/latest' (228 files, 151M)

# Editors

$ brew cask install sublime-text
==> Caveats
Cask sublime-text installs files under "/usr/local".  The presence of such
files can cause warnings when running "brew doctor", which is considered
to be a bug in homebrew-cask.

==> Downloading http://c758482.r82.cf2.rackcdn.com/Sublime%20Text%202.0.2.dmg
######################################################################## 100.0%
==> Symlinking App 'Sublime Text 2.app' to '/Users/hansolo/Applications/Sublime Text 2.app'
==> Symlinking Binary 'subl' to '/usr/local/bin/subl'
🍺  sublime-text installed to '/opt/homebrew-cask/Caskroom/sublime-text/2.0.2' (124 files, 26M)
