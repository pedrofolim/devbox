# Getting Python 2.7 using Homebrew on OS X 10.8.5

These are instructions for installing Python, PIP, and Setuptools using Homebrew.

## Requirements

Homebrew needs to be installed before using these instructions. See [Homebrew on OS X 10.8.5](https://github.com/darkn3rd/devbox/blob/master/howtos/howto.homebrew.md) for more details.

## Assumptions

* Unfiltered connection to Internet
* Clean configuration; no previous version Python, VritualEnv, Pip, or Setuptools installed.

## STEP 1: Install Python using Homebrew

```bash
brew install python
```

Note that when installing Python 2.7.  There are some dependencies.  Issuing the above command will install the follwoing Homebrew bottles: 

* Dependencies:
  * readline-6.3.6.mountain_lion.bottle.tar.gz
  * sqlite-3.8.5.mountain_lion.bottle.tar.gz
  * gdbm-1.11.mountain_lion.bottle.tar.gz
  * openssl-1.0.1h.mountain_lion.bottle.tar.gz
* Python 2.7.8: 
  * python-2.7.8.mountain_lion.bottle.tar.gz

## STEP 2: Check Versions installed

Test Pip Version:

```bash
pip --version
pip 1.5.6 from /usr/local/Cellar/python/2.7.8/Frameworks/Python.framework/Versions/2.7/lib/python2.7/site-packages/pip-1.5.6-py2.7.egg (python 2.7)
```

Test Python Version:

```bash
PATH=/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin
python --version
Python 2.7.8
```