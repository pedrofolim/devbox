# Homebrew Meets Mountain Lion

These are instructions for setting up Homebrew and Cask on Mac OS X 10.8.5 (Mountain Lion).

Homebrew is now probably the most popular package management sytsem, and Casket extends Homebrew to install full applications, such as Sublime, Chrome, and Firefox.

Both of these, Homebrew and Casket, fetches content off the Internet, and as such the contents of the packages can change at any moment.  

Therefore, these instructions and results are only applicable as of July 2014.

On a side note, though Homebrew and Casket are very convenient, this throws a monkey wrench in testing.  To really perform real tests requires that the components do not change, as this introduces random variables into the system.  Having contents that can change on a whim goes against scientific methodology, as the control element is inconsistent. Thus the results cannot be fully trusted and in the worst case scenario can contribute to non-deterministic results.

# Homebrew
```
$ ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
==> This script will install:
/usr/local/bin/brew
/usr/local/Library/...
/usr/local/share/man/man1/brew.1

Press RETURN to continue or any other key to abort
==> /usr/bin/sudo /bin/mkdir /usr/local
Password:
==> /usr/bin/sudo /bin/chmod g+rwx /usr/local
==> /usr/bin/sudo /usr/bin/chgrp admin /usr/local
==> /usr/bin/sudo /bin/mkdir /Library/Caches/Homebrew
==> /usr/bin/sudo /bin/chmod g+rwx /Library/Caches/Homebrew
==> Downloading and installing Homebrew...
remote: Counting objects: 185728, done.
remote: Compressing objects: 100% (50947/50947), done.

$ brew doctor
Please note that these warnings are just used to help the Homebrew maintainers
with debugging if you file an issue. If everything you use Homebrew for is
working fine: please don't worry and just ignore them. Thanks!

Warning: The filesystem on / appears to be case-sensitive.
The default OS X filesystem is case-insensitive. Please report any apparent problems.
```

# Cask

```brew
$ brew install caskroom/cask/brew-cask
Cloning into '/usr/local/Library/Taps/caskroom/homebrew-cask'...
remote: Reusing existing pack: 46705, done.
remote: Counting objects: 57, done.
remote: Compressing objects: 100% (57/57), done.
remote: Total 46762 (delta 27), reused 6 (delta 0)
Receiving objects: 100% (46762/46762), 14.78 MiB | 904.00 KiB/s, done.
Resolving deltas: 100% (28955/28955), done.
Checking connectivity... done.
Tapped 1 formula
==> Cloning https://github.com/caskroom/homebrew-cask.git
Cloning into '/Library/Caches/Homebrew/brew-cask--git'...
remote: Counting objects: 1895, done.
remote: Compressing objects: 100% (1866/1866), done.
remote: Total 1895 (delta 30), reused 624 (delta 20)
Receiving objects: 100% (1895/1895), 5.01 MiB | 965.00 KiB/s, done.
Resolving deltas: 100% (30/30), done.
Checking connectivity... done.
Note: checking out '8db73ff33341f25fe3a44fb82a2b3bc83617e81f'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by performing another checkout.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -b with the checkout command again. Example:

  git checkout -b new_branch_name

==> Checking out tag v0.37.1
🍺  /usr/local/Cellar/brew-cask/0.37.1: 1730 files, 6.8M, built in 9 seconds
```