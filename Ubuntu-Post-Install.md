* Remove Firefox Snap and Install Firefox Deb
```bash
sudo snap remove --purge firefox
```
```bash
sudo apt install firefox
```

* Update
```bash
sudo apt update && sudo apt upgrade -y
```

* Install Ubuntu Restricted Extras
```bash
sudo apt install ubuntu-restricted-extras
```

* Minimize on Click
```bash
gsettings set org.gnome.shell.extensions.dash-to-dock click-action minimize
```

* Timeshift
```bash
sudo apt install timeshift
```

* Flatpak
```bash
sudo apt install gnome-software gnome-software-plugin-flatpak flatpak
```
```bash
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

* Extensions Support
```bash
sudo apt install chrome-gnome-shell gnome-shell-extension-prefs
```

* GNOME Tweaks
```bash
sudo apt install gnome-tweaks
```