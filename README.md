# gnome-terminal
This repository holds a patch for gnome terminal, to allow automatic profile switching.

This adds a new property to the profiles : match_string . If match_string matches the title (ie : the title contains match_string), the profile is automatically selected. The order of selection depends on the order of the profiles (sorted alphabetically).

Currently, no interface is provided to edit the settings, so you need to do it via dconf-editor.  
