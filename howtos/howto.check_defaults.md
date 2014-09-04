# Testing Defaults

These are a laundry list of defaults that OS X 10.8.5, XCode 5.1.1, and Apple's supplied Java 6 SE.


## Assumptions

* Operating System updated to OS X 10.8.5.  See [Updating OS X 10.8 to OS X 10.8.5](https://github.com/darkn3rd/devbox/blob/master/howtos/howto.update_osx_10_8_5.md).
* XCode 5.1.1 is installed. See [XCode 5.1.1 on OS X 10.8.5](https://github.com/darkn3rd/devbox/blob/master/howtos/howto.xcode.md).
* Java 6 SE installed from Apple. See [Getting Java 6 on Mac OS 10.8](https://github.com/darkn3rd/devbox/blob/master/howtos/howto.jre6.md).

# The Tests

## Compilers

### Checking GNU C Compiler

It seems like Apple is forcing us to use LLVM compiler, which has caused problems with some open source code, namely various Ruby GEMs.

```bash
gcc --version
Configured with: --prefix=/Applications/Xcode.app/Contents/Developer/usr --with-gxx-include-dir=/usr/include/c++/4.2.1
Apple LLVM version 5.1 (clang-503.0.40) (based on LLVM 3.4svn)
Target: x86_64-apple-darwin12.5.0
Thread model: posix
```

### Checking LLVM C++ Compiler

```bash
cpp --version
Apple LLVM version 5.1 (clang-503.0.40) (based on LLVM 3.4svn)
Target: x86_64-apple-darwin12.5.0
Thread model: posix
```

## Application Virtual Machines

### Checking Java Virtual Machine Environment

```bash
java -version
java version "1.6.0_65"
Java(TM) SE Runtime Environment (build 1.6.0_65-b14-466.1-11M4716)
Java HotSpot(TM) 64-Bit Server VM (build 20.65-b04-466.1, mixed mode)
```

## Scripting Engines

### Checking AWK Version

```bash
/usr/bin/awk --version
awk version 20070501
```

This version is the antiquated BSD version.  GNU Awk 4.1.1 is out and supports more features.

### Checking Perl Version

```bash
perl -version | head -3

This is perl 5, version 12, subversion 4 (v5.12.4) built for darwin-thread-multi-2level
(with 2 registered patches, see perl -V for more detail)
```

### Checking PHP Version

```bash
php -v
PHP 5.3.26 (cli) (built: Jul  7 2013 19:05:08) 
Copyright (c) 1997-2013 The PHP Group
Zend Engine v2.3.0, Copyright (c) 1998-2013 Zend Technologies
```

### Checking Python Version

```bash
python --version
Python 2.7.2
```

### Checking Ruby Version

```bash
/usr/bin/ruby --version
ruby 1.8.7 (2012-02-08 patchlevel 358) [universal-darwin12.0]
```

### Checking TCL (Tool Command Language)

```bash
echo 'puts $tcl_version;exit 0' | /usr/bin/tclsh
8.5
```

## Shells

### Checking Default Shell Version

```
/bin/sh --version
GNU bash, version 3.2.48(1)-release (x86_64-apple-darwin12)
Copyright (C) 2007 Free Software Foundation, Inc.
```

This uses the antiquated bash running in strict shell mode.  This may cause problems to create portiable POSIX shell scripts, as Bash-only features may work.  An alternative would be to use Korn shell as ```sh```, as that has worked better in strict shell mode, or to install ```dash```, which only runs in POSIX shell mode.

### Checking Bash (Bourne Again Shell) Version

```bash
/bin/bash --version
GNU bash, version 3.2.48(1)-release (x86_64-apple-darwin12)
Copyright (C) 2007 Free Software Foundation, Inc.
```

Apple's supplied default bash is really old, and the current one is at Bash 4.3.

### Checking Korn Shell Version

```bash
/usr/bin/ksh --version
  version         sh (AT&T Research) 93u 2011-02-08
```

There is a more recent version of "93u+ 2012-08-01".

### Checking Korn Shell Version

```bash
/usr/bin/zsh --version
zsh 4.3.11 (i386-apple-darwin12.0)
```

## Tools

### Checking GIT Version

```bash
git --version
git version 1.8.5.2 (Apple Git-48)
```