## how to install

### Via AppImage Launcher

- Download the [app](https://github.com/TheAssassin/AppImageLauncher)

- Install it

- Run the `AppImage` Program

### Manual

- Make `AppImage` executable

```sh
chmod a+x <AppImageFile>
```

- Get `.png` icon

- create `.desktop` file

```ini
[Desktop Entry]
Type=Application
Name=APPNAME
Exec=PATH/TO/APP/APPIMAGE
Icon=PATH/TO/APP/ICON
Categories=EX"AudioVideo;Video;"
Comment=ABOUT THE APP
GenericName=APP GENERAL NAME
Terminal=false
```

- Copy the new `.desktop` file to:

```
$HOME/.local/share/applications/
```

## Make appimages fully portable.

- Create a dir named `AppImageFile.home`

## Advanced: Extract AppImge

```sh
./AppImageFile --appimage-extract
```

## Advanced: `desktop-file-utils`

- Validate `.desktop`

```sh
desktop-file-validate app.desktop
```

- Install `.desktop`

```sh
desktop-file-install --dir=$HOME/.local/share/applications /path/to/app.desktop
```

- Update desktop database

```sh
update-desktop-database ~/.local/share/applications
```

---

>Reference:  
[desktop entries - arch wiki](https://wiki.archlinux.org/title/desktop_entries)  
[desktop entry specifications - freedesktop](https://specifications.freedesktop.org/desktop-entry-spec/desktop-entry-spec-latest.html)  
[menu specifications - freedesktop](https://specifications.freedesktop.org/menu-spec/menu-spec-latest.html)  
[Xdg-menu - arch wiki](https://wiki.archlinux.org/title/Xdg-menu)  
[portable appimage](https://docs.appimage.org/user-guide/portable-mode.html)  