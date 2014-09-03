# Testing Defaults

These are a laundry list of defaults that OS X 10.8.5 and XCode 5.1.1


## Assumptions

* Operating System updated to OS X 10.8.5.  See [Updating OS X 10.8 to OS X 10.8.5](https://github.com/darkn3rd/devbox/blob/master/howtos/howto.update_osx_10_8_5.md).
* XCode 5.1.1 is installed. See [XCode 5.1.1 on OS X 10.8.5](https://github.com/darkn3rd/devbox/blob/master/howtos/howto.xcode.md).
* Java 6 SE installed from Apple. See [Getting Java 6 on Mac OS 10.8](https://github.com/darkn3rd/devbox/blob/master/howtos/howto.jre6.md).

## The Tests

## Checking GNU C Compiler

```bash
gcc --version
Configured with: --prefix=/Applications/Xcode.app/Contents/Developer/usr --with-gxx-include-dir=/usr/include/c++/4.2.1
Apple LLVM version 5.1 (clang-503.0.40) (based on LLVM 3.4svn)
Target: x86_64-apple-darwin12.5.0
Thread model: posix
```

## Checking LLVM C++ Compiler

```bash
cpp --version
Apple LLVM version 5.1 (clang-503.0.40) (based on LLVM 3.4svn)
Target: x86_64-apple-darwin12.5.0
Thread model: posix
```

## Checking Perl Version

```bash
perl -version | head -3

This is perl 5, version 12, subversion 4 (v5.12.4) built for darwin-thread-multi-2level
(with 2 registered patches, see perl -V for more detail)
```

## Checking Ruby Version

```bash
ruby --version
ruby 1.8.7 (2012-02-08 patchlevel 358) [universal-darwin12.0]
```

## Checking Python Version

```bash
python --version
Python 2.7.2
```

## Checking Bash (Bourne Again Shell) Version

```bash
bash --version
GNU bash, version 3.2.48(1)-release (x86_64-apple-darwin12)
Copyright (C) 2007 Free Software Foundation, Inc.
```

## Checking Korn Shell Version

```bash
ksh --version
  version         sh (AT&T Research) 93u 2011-02-08
```

## Checking TCL (Tool Command Language)

```bash
echo 'puts $tcl_version;exit 0' | tclsh
8.5
```

## Checking Java Virtual Machine Environment

```bash
java -version
java version "1.6.0_65"
Java(TM) SE Runtime Environment (build 1.6.0_65-b14-466.1-11M4716)
Java HotSpot(TM) 64-Bit Server VM (build 20.65-b04-466.1, mixed mode)
```

## Checking PHP Version

```bash
php -v
PHP 5.3.26 (cli) (built: Jul  7 2013 19:05:08) 
Copyright (c) 1997-2013 The PHP Group
Zend Engine v2.3.0, Copyright (c) 1998-2013 Zend Technologies
```

## Checking GIT Version

```bash
git --version
git version 1.8.5.2 (Apple Git-48)
```