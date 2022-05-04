

- `.desktop` file path `~/.local/share/applications`

```
[Desktop Entry]
Type=Application
Name=APP NAME
Path=PATH/TO/APP/DIR
Exec=PATH/TO/APP/APPIMAGE
Icon=PATH/TO/APP/ICON
Categories=EX"AudioVideo;Video;"
Comment=ABOUT THE APP
GenericName=APP GENERAL NAME
```

```
[Desktop Entry]

# The type as listed above
Type=Application

# The version of the desktop entry specification to which this file complies
Version=1.0

# The name of the application
Name=jMemorize

# A comment which can/will be used as a tooltip
Comment=Flash card based learning tool

# The path to the folder in which the executable is run
Path=/opt/jmemorise

# The executable of the application, possibly with arguments.
Exec=jmemorize

# The name of the icon that will be used to display this entry
Icon=jmemorize

# Describes whether this application needs to be run in a terminal or not
Terminal=false

# Describes the categories in which this entry should be shown
Categories=Education;Languages;Java;
```

Validation `desktop-file-utils`

```sh
desktop-file-validate <your desktop file>
```

Installation

```sh
desktop-file-install --dir=$HOME/.local/share/applications ~/app.desktop
```

Update database of desktop entries

```sh
update-desktop-database ~/.local/share/applications
```