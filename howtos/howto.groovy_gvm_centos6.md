# Getting Groovy with GVM on Cent OS 6

This is a small guide for installing Groovy on Cent OS 6.5 using the [Groovy enVironment Manager](http://gvmtool.net/).  

These instructions were tested on 2015-08-03.

## Assumptions

There are no assumptions other than this has been tested on Cent OS 6.5.  Different configurations may require adjustments to these steps.

These steps are for a single user's environment, as GVM supports a single user environment.  Any admistrative access, such as using ```yum```, you may have to ```sudo``` or ```su``` into an administrative account.

## Requirements

* Java is required before installing Groovy.  This has been tested on Java 1.6 and Java 1.7.  

## The Steps

### STEP 1: Check for Java

We need some sort of Java installed.  Check for version installed:

```bash
java -version
java version "1.7.0_65"
OpenJDK Runtime Environment (rhel-2.5.1.2.el6_5-x86_64 u65-b17)
OpenJDK 64-Bit Server VM (build 24.65-b04, mixed mode)
```

You can also see if the package is installed:

```bash
yum list installed | grep java-
```

On my system, this lists:
```
java-1.7.0-openjdk.x86_64
```

If you do not have that package, you can easily install it:

```bash
sudo yum install java-1.7.0-openjdk
```

### STEP 2: Configure JAVA_HOME

Before we even touch GVM, we need to configure the ```JAVA_HOME``` environment variables.  First we need to find out where it is located:

```bash
alternatives --display java | grep 'jre:' | awk '{ print $3 }'
```

On my system, this outputs:

```
/usr/lib/jvm/jre-1.7.0-openjdk.x86_64
```

Cent OS 6.5 seems to like ```.bashrc``` so we can append this line to that file.

```bash
echo export JAVA_HOME=/usr/lib/jvm/jre-1.7.0-openjdk.x86_64 >> $HOME/.bashrc
```

Note that that you will need update ```JAVA_HOME``` if you change your version of Java.

### STEP 3: Install GVM

From a user account where you want to use GVM, run these commands:

```bash
curl -s get.gvmtool.net | bash
source $HOME/.bashrc
```

### STEP 4: Install Groovy

Now we can install the latest Groovy, which as of this writing (2014-08-03) is Groovy 2.3.6.

```bash
gvm install groovy
```
