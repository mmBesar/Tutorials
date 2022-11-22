# Ubuntu 22.10 Post Installation

## Update

```sh
sudo apt update && sudo apt upgrade -y
```

## Remove Firefox Snap and Install Firefox Deb

1. ### Remove Firefox Snap

```sh
sudo apt remove --autoremove firefox
```

```sh
sudo snap remove --purge firefox
```

2. ### Add Mozilla Team PPA

```sh
sudo add-apt-repository ppa:mozillateam/ppa
```

3. ### Set Mozilla team PPA as high Priority

```sh
echo '
Package: *
Pin: release o=LP-PPA-mozillateam
Pin-Priority: 1001
' | sudo tee /etc/apt/preferences.d/firefox-ppa-priority
```

4. ### Block the Ubuntu repo

```sh
echo '
Package: firefox*
Pin: release o=Ubuntu*
Pin-Priority: -1
' | sudo tee /etc/apt/preferences.d/firefox-ubuntu-block
```

5. ### Set Firefox for automatic updates
```sh
echo 'Unattended-Upgrade::Allowed-Origins:: "LP-PPA-mozillateam:${distro_codename}";' | sudo tee /etc/apt/apt.conf.d/51unattended-upgrades-firefox
```

6. ### Update

```sh
sudo apt update
```

7. ### Install Firefox DEB

```sh
sudo apt install firefox
```

## Install Ubuntu Restricted Extras

```sh
sudo apt install ubuntu-restricted-extras
```

## Minimize on Click

### Minimize on Click the old style

```sh
gsettings set org.gnome.shell.extensions.dash-to-dock click-action 'minimize'
```

### Minimize on Click 22.10 style

```sh
gsettings set org.gnome.shell.extensions.dash-to-dock click-action 'focus-minimize-or-appspread'
```

## Flatpak and Flathub

```sh
sudo apt install flatpak
```
```sh
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

## Gnome Software

```sh
sudo apt install gnome-software gnome-software-plugin-flatpak
```

## AppImage Support

```sh
sudo apt install libfuse2
```

## Gnome Extensions

```sh
sudo apt install chrome-gnome-shell gnome-shell-extension-prefs gnome-shell-extension-manager
```

## Gnome Tweaks

```sh
sudo apt install gnome-tweaks
```

## Enable ‘New Documents’ context menu

```sh
touch ~/Templates/new
```

## Arabic Keyboard

## System Backup with Timeshift

```sh
sudo apt install timeshift
```

## Backup your files with [Deja Dup](https://flathub.org/apps/details/org.gnome.DejaDup)

## Update again

```sh
sudo apt update && sudo apt upgrade -y && flatpak update -y && sudo snap refresh
```