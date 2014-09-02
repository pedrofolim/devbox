# Getting Ruby-on-Rails on Ubuntu


This is set of instructions to install [Ruby-On-Rails](http://rubyonrails.org/) on Ubuntu.  You can omit rails and just install a git + ruby environment as well.  

Note that this installs a per project (that is user account) Ruby environment.  For System-wide, such as system ruby scripts, install ruby package on system wide bases.  RVMRC will override this on a per-user basis. 

These instructions were created on December 16, 2013.  

## STEP 1: Install Base set of libraries and tools

Install a base set of libraries, and install curl as this is needed to download and run RVM install script.

```bash
sudo apt-get update
sudo apt-get install git-core
sudo apt-get install curl
```

By doing the above, this will also install requirements, which essentially does:

```bash
sudo apt-get install libcurl4-gnutls-dev libexpat1-dev gettext \
libz-dev libssl-dev build-essential
```

## STEP 2: Get RVM

Install Ruby Version Manager to manage Ruby versions.

```bash
\curl -L https://get.rvm.io | bash -s stable
source ~/.rvm/scripts/rvm
rvm requirements
rvm install ruby
rvm use ruby --default
rvm rubygems current
```

## STEP 3: Install Bundler and Rake

[Bundler](http://bundler.io/) manages Ruby GEM library dependencies, and [Rake](https://github.com/jimweirich/rake) is a popular build tool that is needed for [Ruby-On-Rails](http://rubyonrails.org/).

```bash
gem install bundler
gem install rake
```

## STEP 4: Install Ruby on Rails

Installing Rails is really simple at this point:

```bash
gem install rails
```

## STEP 5: Install Heroku Tools (Optional)

If you are interested to use the online system called Heroku for testing, deploying, and hosting your [Rails](http://rubyonrails.org/) application, you can run through the following:

```bash
wget -qO- https://toolbelt.heroku.com/install-ubuntu.sh | sh
```

