# Mac OS X 10.8 Snow Leopard and HomeBrew

This is a set of snippets used to capture installation of packages uses HomeBrew as of July, 2014.  I specify the date because HomeBrew scripts and packages may change at any moment as they are fetched from the Internet.

## Unix Shell and Unix Tools

I wanted to fetch a pure POSIX shell to test out portable scripts:

```bash
brew install dash
==> Downloading http://gondor.apana.org.au/~herbert/dash/files/dash-0.5.7.tar.gz
######################################################################## 100.0%
==> ./configure --prefix=/usr/local/Cellar/dash/0.5.7 --with-libedit --enable-fnmatch --enable-glob
==> make
==> make install
🍺   /usr/local/Cellar/dash/0.5.7: 5 files, 220K, built in 7 seconds
man dash | head

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

Then for Korn shell:

```bash
brew install ksh
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/ksh-93u+.mountain_lion.bottle.1.tar.gz
######################################################################## 100.0%
==> Pouring ksh-93u+.mountain_lion.bottle.1.tar.gz
==> Caveats
We have agreed to the Eclipse Public License on your behalf.
If this is unacceptable for any reason, please uninstall.
==> Summary
🍺   /usr/local/Cellar/ksh/93u+: 4 files, 1.5M
```

And of course, Bourne Again Shell 4.x, as Mac OS X comes with icky old version of Bash 3.x:


```bash
brew install bash
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
