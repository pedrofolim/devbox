# Installing Ruby 1.9 on Windows 7

These instructions are for setting up an Ruby environment on Windows using tools like PIK and Chocolately.  

These steps were tested on Windows 7 on September 3rd, 2013.


# STEP 1: Install Chocolately

[Chocolately](http://chocolatey.org/) is an package management tool that leverages off of NuGet to download and install system-wide packages for Windows.  After installing this solution, it will be easy to install other packages, such as Ruby or PIK.

```batch
@powershell -NoProfile -ExecutionPolicy unrestricted -Command "iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))" && SET PATH=%PATH%;%systemdrive%\chocolatey\bin
```

# STEP 2: Install Ruby 1.9

Install Ruby 1.9 or other desired version for Ruby.

```batch
cinst ruby -Version 1.9.3.44800
```

# STEP 3: Install PIK (Optional)

[PIK](https://github.com/vertiginous/pik) is a tool to manage Ruby versions on Windows without the need for a UNIX simulation to use tools like RVM.  This can be used to install Ruby or select the default Ruby.

```batch
cinst pik
```

# STEP 4: Update GEMS and Install Bundler

[Bundler](http://bundler.io/) manages Ruby GEM library dependencies.

```batch
gem update --system
gem install bundler
```
