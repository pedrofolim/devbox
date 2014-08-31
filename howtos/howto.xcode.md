# The Dev Box / OS X:  Getting XCode

In order to get anywhere in life on a computer you need some compiler, and on OS X this is certainly true.  You need compilers to install numerous open source software available on the Internet.  Package managers such as MacPorts or Homebrew require these compilers.

On OS X, the compilers called Xcode are available either through *App Store* or by registering and downloading the software from https://developer.apple.com/.

I recommend downloading the packages from https://developer.apple.com/, because you can reinstall them on other Macintoshes, or should you need to reinstall your operating system, you can have these packages available, saving further trips to *App Store* and the needs to re-download gigabytes of data.

## Requirements

You need to have the following:

* Registers and Create an account with https://developer.apple.com/
* Updated OS X 10.8.5

## Assumptions

* Unfiltered connection to Internet
* All software downloaded will be stored in ```$HOME/Downloads```
* Clean configuration; no previous version Xcode has been installed.

## Notes

* These steps were tested as of July 2014.

## STEPS

### STEP 1: Download the Packages

Manually download the file ```xcode_5.1.1.dmg``` and ```command_line_tools_for_osx_mountain_lion_april_2014.dmg``` from https://developer.apple.com/downloads/index.action.

### STEP 2: Install Xcode

Follow these steps from the command line:

```bash
hdiutil mount $HOME/Downloads/xcode_5.1.1.dmg
sudo cp -R "/Volumes/Xcode/Xcode.app" /Applications
```

### STEP 3: Agree to License

Follow these steps from the command line:

```bash
sudo xcodebuild -license
```

### STEP 4: Test the Results

Follow these steps from the command line:

```bash
/Applications/Xcode.app/Contents/Developer/usr/bin/gcc --version
```

This will print out

```
Configured with: --prefix=/Applications/Xcode.app/Contents/Developer/usr --with-gxx-include-dir=/usr/include/c++/4.2.1
Apple LLVM version 5.1 (clang-503.0.40) (based on LLVM 3.4svn)
Target: x86_64-apple-darwin12.5.0
Thread model: posix
```

### STEP 5: Install Command Line Tools

Follow these steps from the command line:

```bash
hdiutil mount $HOME/Downloads/command_line_tools_for_osx_mountain_lion_april_2014.dmg
sudo -S installer -verbose -pkg "/Volumes/Command Line Tools (Mountain Lion)/Command Line Tools (Mountain Lion).mpkg" -target /

### STEP 6: Remove Mounted Volumes

Follow these steps from the command line:

```bash
hdiutil unmount /Volumes/Xcode
hdiutil unmount "/Volumes/Command Line Tools (Mountain Lion)"
```

### STEP 7: Test the Results

Follow these steps from the command line:
```bash
cd $HOME
gcc --version
```

This should print out:
```
Configured with: --prefix=/Applications/Xcode.app/Contents/Developer/usr --with-gxx-include-dir=/usr/include/c++/4.2.1
Apple LLVM version 5.1 (clang-503.0.40) (based on LLVM 3.4svn)
Target: x86_64-apple-darwin12.5.0
Thread model: posix
```