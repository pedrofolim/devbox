# Getting Java 6 on Mac OS 10.8

Apple no longer bundles Java with OS X, but you can fetch a version from their support site.

These steps are for getting the default Java SE Runtime Environment 6 from Apple's support site.  Newer versions will come from Oracle.

These instructions are valid as of July 13, 2014 and tested with OS X 10.8.3.

## Assumptions

* Unfiltered connection to Internet
* All software downloaded will be stored in ```$HOME/Downloads```
* Clean configuration; no previous version Java has been installed.

## STEPS

### STEP 1: Download the Packages

Download Java from Apple's Support site.

* http://support.apple.com/downloads/DL1572/en_US/JavaForOSX2014-001.dmg

### STEP 2: Install Java from Image

Install the package from the image.

```bash
hdiutil mount $HOME/Downloads/JavaForOSX2014-001.dmg
sudo -S installer -verbose -pkg "/Volumes/Java for OS X 2014-001/JavaForOSX.pkg" -target /
```

### Step 3: Verify Version

After installation, verify the version.

```bash
java -version
```

This will print out something like:

```
java version "1.6.0_65"
Java(TM) SE Runtime Environment (build 1.6.0_65-b14-466.1-11M4716)
Java HotSpot(TM) 64-Bit Server VM (build 20.65-b04-466.1, mixed mode)
```

### Step 4: Clean Up

```bash
hdiutil unmount "/Volumes/Java for OS X 2014-001"
```
