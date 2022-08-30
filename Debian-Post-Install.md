# Debian 11 Post Install

## Install `sudo` if not installed

```sh
su
apt install sudo
```

## Add User to `sudo` Group

```sh
su
gpasswd -a $USER sudo
```

## Enable None Free

```sh
cat /etc/apt/sources.list | grep "contrib non-free" || sudo sed -i "s/main/main contrib non-free/g" /etc/apt/sources.list
```

## Install Codecs, Microsoft Fonts and rar support (Ubuntu restricted-extras)

```sh
sudo apt install libavcodec-extra ttf-mscorefonts-installer rar unrar gstreamer1.0-libav gstreamer1.0-plugins-ugly gstreamer1.0-vaapi
```

## Microsoft Fonts alternatives for "Cambria, Calibri"

```sh
sudo apt install fonts-crosextra-caladea fonts-crosextra-carlito
```

## Install and Enable Firewall

```sh
sudo apt install ufw
sudo ufw enable
sudo ufw allow ssh
```

## Apps

```sh
sudo apt install plocate htop
sudo updatedb
```

## Flatpak Support

```sh
sudo apt install flatpak
sudo flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

## Nvidia Drivers

```sh
sudo apt install nvidia-detect
sudo nvidia-detect
```

## Better Software center (for Xfce Only)

```sh
sudo apt install gnome-software
sudo apt install gnome-software-plugin-flatpak
```
