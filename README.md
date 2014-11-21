# The Dev Box

Here is a repository of various scripts used to configure a development system that can be used for scripting and development (compiled code) in a variety of languages and application virtual machines.

These are the topic areas that I generally use.  If there is a tool or area, drop me a note, and I can add a section.

## Mac OS X and Windows NT Environments

This is a vehicle to test various operating systems and packaging environments.  On most distributions, the process is pretty straight forward, but for Microsoft Windows and Mac OS X, this can get challenging.  


* :dvd: ***OS X***
  * **Mac Ports** [https://www.macports.org/] - multi-user system
  * **HomeBrew** [http://brew.sh/] - single user system that overrides /usr/local and fetches content off the Internet and compiles it locally.
    * **Cask** [http://caskroom.io/] - uses HomeBrew to install applications, such as Chrome.
    * **Ruby Version Manager** [https://rvm.io/] - manages Ruby versions; now requires HomeBrew
  * **Rudix** [http://rudix.org/] - packaging system that offers fully self-contained packages using Mac OS X native packaging system (.pkg files)
* :dvd: ***Windows***
  * **CygWin** [https://www.cygwin.com/] - build tools and Unix-like environment; uses libraries offer compatibility layer to Windows.
    * **Apt-Cyg** [https://code.google.com/p/apt-cyg/] - Alternative to CygWin's GUI package management system, so that package for command-line can be installed by the command-line.
  * **GNU-Win32** [http://gnuwin32.sourceforge.net/] - GNU utilities that work in Windows Command Shell environment and do not require any special build environment or library, except for Microsoft's C++ Runtime.
  * **MingGW** [http://www.mingw.org/] - build tools that allow porting Unix tools to Windows and requires no special library.
    * **MSYS** [http://www.mingw.org/wiki/msys] - set of GNU command line tools that support MingGW environment.  These tools are fully functional in Windows command shell environment.
    * **msysgit** [http://msysgit.github.io/] - essentially msys bundled with git tools.
  * **NuGet** [https://www.nuget.org] - library package system for .NET environment.
    * **Chcolately** [https://chocolatey.org/] - goes beyond NuGet to install system wide packages, libraries, and applications.  Content is fetched off the Internet.
  * **UWIN** [http://www2.research.att.com/~astopen/download/uwin/uwin.html] - Are a set of SVR4 Unix tools and the Korn shell ported to work in the Windows environment.

I have explored the Interix environment on Windows [http://en.wikipedia.org/wiki/Windows_Services_for_UNIX], which is supported as an extra add-on (either free or with later versions of Windows at an expensive cost).  This environment includes tools that are not generally available outside the Interix environment, and since it is not freely available, it will not be tested.

# Target Environments and Tools

## Unix Shell Environment and Unix Tools

These are the lovable shell and shell tools, such as awk, sed, and grep, that one comes to expect in working with Unix or Linux.  

### POSIX Shell and POSIX Tools

The POSIX shell is essentially the classic Bourne Shell with enhancements to make it compatible with POSIX specification.  One can get a ash or dash to test out POSIX shell scripts.  

### Korn Shell and SVR Unix Tools

This is the Korn shell and tools that might be unique for SVR4 Unix environments, such as pax and nawk.  

### Bash and GNU Tools

This is Bourne Again Shell and various popular GNU tools such as Core-Utils and GNU bc.  

## Scripting Languages

Popular scripting languages like Perl, Python, PHP, and Ruby.  And throw in TCL for good measure.

## Development Environment

Compilers for C, C++, and Objective-C using GNU GCC.

## Java Virtual Machine

Environment to compile and run Java applications.

### Groovy

Groovy is a popular language used for automating build environments, web applications, and other chores.

## CLR Virtual Machine

This will be Microsoft's .NET environment and Mono.

### PowerShell

PowerShell as most may know is a scripting environment that runs on .NET (CLR VM).  This is Microsoft's designated scripting automation environment for Microsoft Windows operating system.  There is a movement to port PowerShell to non-Windows systems [https://github.com/Pash-Project/Pash].

## Windows NT Only Environments

On Windows environment only, grab the latest WSH (Windows Script Host) environment available. Windows Script Host supports a variety languages, with JScript and VBScript supported from Microsoft.  Occasionally, there is a need to use some script that has not yet been rewritten in Powershell or other language.
