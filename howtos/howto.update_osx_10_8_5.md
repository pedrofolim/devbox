# Updating OS X 10.8 to OS X 10.8.5

My computer (Macbook Retina) came with OS X 10.8.3 pre-installed, and OS X 10.8.5 is the latest available.

To install the update for OS X 10.8.5, you can use *App Store* or you can manually download this, and install this yourself.  I prefer to manually install the update, as it puts the control in the hands of the user, and saves me time to download gigabytes should I ever need to install this again.

## Assumptions

* Operating System is OS X 10.8.x version that is earlier than OS X 10.8.5
* Unfiltered connection to Internet
* All software downloaded will be stored in ```$HOME/Downloads```
* Installation is from a user account, not ```root```.

## STEPS

### STEP 1: Download the Image

From Apple's Support site download the latest combo for OS X 10.8.5.  As of July 13, 2014, I was able to find this:

* http://support.apple.com/downloads/DL1676/en_US/OSXUpdCombo10.8.5.dmg

### STEP 2: Install the Package from the Image

```bash
hdiutil mount $HOME/Downloads/OSXUpdCombo10.8.5.dmg
sudo -S installer -verbose -pkg "/Volumes/OS X 10.8.5 Update Combo/OSXUpdCombo10.8.5.pkg" -target /
```

This should print out several lines ending with something like:

```
installer: The software was successfully installed......
installer: The upgrade was successful.
installer: The install requires restarting now.
```

### STEP 3: Clean-up

Perhaps this is not needed since we will restart the computer.

```bash
hdiutil unmount "/Volumes/OS X 10.8.5 Update Combo"
```

### STEP 4: Restart the Computer when Ready

Restart the computer, one way to do this is using this AppleScript command:

```bash
osascript -e 'tell app "System Events" to restart'
```

I tried ```shutdown -r```, but the system seemed to freeze.  The above AppleScript command seems to work better.