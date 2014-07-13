# The Dev Box

Here is a repository of various scripts used to configure a development system that can be used for scripting and development (compiled code) in a variety of languages and application virtual machines.

These are the topic areas that I generally use.  If there is a tool or area, drop me a note, and I can add a section.

## Mac OS X and Windows NT Environments

This is a vehicle to test various operating systems and packaging environments.  On most distributions, the process is pretty straight forward, but for Microsoft Windows and Mac OS X, this can get challenging.  


* Mac OS X
  * Mac Ports [https://www.macports.org/] - multi-user system 
  * HomeBrew [http://brew.sh/] - single user system that overrides /usr/local and fetches content off the Internet and compiles it locally.
    * Cask [http://caskroom.io/] - uses HomeBrew to install applications, such as Chrome.
    * Ruby Version Manager [https://rvm.io/] - manages Ruby versions; requires homebrew 
  * Rudix [http://rudix.org/] - packaging system that offers fully self-contained packages using Mac OS X native packaging system (.pkg files)
* Windows NT Environment and Package System* 
  * CygWin [https://www.cygwin.com/] - build tools and Unix-like environment; uses libraries offer comptability layer to Windows.
    * Apt-Cyg [https://code.google.com/p/apt-cyg/] - Alternative to CygWin's GUI package management system, so that package for command-line can be installed by the command-line.
  * GNU-Win32 [http://gnuwin32.sourceforge.net/] - GNU utilities that work in Windows Command Shell environment and do not require any special build environment or library, except for Microsoft's C++ Runtime.
  * MingGW [http://www.mingw.org/] - build tools that allow porting Unix tools to Windows and requires no special library.
    * MSYS [http://www.mingw.org/wiki/msys] - set of GNU command line tools that support MingGW environment.  These tools are fully functional in Windows command shell environment.
    * msysgit [http://msysgit.github.io/] - essentially msys bundled with git tools.
  * NuGet [https://www.nuget.org] - library package system for .NET environment.
    * Chcolately [https://chocolatey.org/] - goes beyond NuGet to install system wide packages, libraries, and applications.  Content is fetched off the Internet.
   
* Windows NT marketed under different names: Windows 2000, Windows XP, Windows 7, WIndows 8.1, etc.  

