# gnome-terminal
This repository holds a patch for gnome terminal, to allow automatic profile switching.

This adds a new property to the profiles : match_string . If match_string matches the title (ie : the title contains match_string), the profile is automatically selected. The order of selection depends on the order of the profiles (sorted alphabetically).

Currently, no interface is provided to edit the settings, so you need to do it via dconf-editor.  

The master branch is currently targeted for debian buster. A branch is created
for each release, so use the patch that correspond to your release.

# How to use

In an empty directory, run the following commands :

```
$ apt source gnome-terminal
```

and, as root

```
# apt build-deb gnome-terminal
```

It should download some files, and create a directory named gnome-terminal-< version >.

Enter this directory, and run :
```
$ echo "magicprofile-jbc" >> debian/patches
$ dch
```

Edit the patch by changing the version in the first line, changing it as something like 

```
gnome-terminal (3.30.2-2.jbc) UNRELEASED; urgency=medium
```

Save and exit, and run

```
$ dpkg-buildpackage
```

And then, as root

```
# dpkg -i ../gnome-terminal-data_<version>.deb ../gnome-terminal_<version>.deb
``` 