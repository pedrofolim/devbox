# Getting Ruby using Homebrew

This is a simple installation of Ruby using Homebrew.  These instructions were tested on July 13, 2014.

## Requirements

Homebrew needs to be installed before using these instructions. See [Homebrew on OS X 10.8.5](https://github.com/darkn3rd/devbox/blob/master/howtos/howto.homebrew.md) for more details.

## Assumptions

* Unfiltered connection to Internet
* Clean configuration; no previous version Ruby, RVM, or Bundler installed.
* Installation is from a user account, not ```root```.

## STEP 1: Install Ruby using Homebrew

```bash
brew install ruby
```

This should print something like:

```
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
```

### STEP 2: Test Ruby Version

Install your desired version of Ruby.  Here's an example of installing both Ruby 1.9 and Ruby 2.0.

```bash
ruby --version
ruby 2.1.2p95 (2014-05-08 revision 45877) [x86_64-darwin12.0]
```

### STEP 2: Test Gem Version

```bash
gem --version
2.2.2
```