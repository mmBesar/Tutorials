# Fedora 37 Post-installation Steps

## Speed up DNF

- Set fastestmirror

```sh
echo 'fastestmirror=true' | sudo tee -a /etc/dnf/dnf.conf
```

- Set deltarpm #optional
 
```sh
echo 'deltarpm=true' | sudo tee -a /etc/dnf/dnf.conf
```

- Set parallel downloads #optional

```sh
echo 'max_parallel_downloads=5' | sudo tee -a /etc/dnf/dnf.conf
```

## Enable [RPM Fusion](https://docs.fedoraproject.org/en-US/quick-docs/setup_rpmfusion/) Free and None-Free

```sh
sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
```

```sh
sudo dnf --refresh upgrade
```

```sh
sudo dnf groupupdate core
```

## [Flathub](https://flatpak.org/setup/Fedora)

```sh
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

## Enable Third-Party Repositories if You Didn't

## Install [NVIDIA Drivers](https://rpmfusion.org/Howto/NVIDIA)

## Hardware acceleration

### Hardware acceleration for AMD and Intel

```sh
sudo dnf swap mesa-va-drivers mesa-va-drivers-freeworld
```

### Hardware acceleration for AMD

```sh
sudo dnf swap mesa-vdpau-drivers mesa-vdpau-drivers-freeworld
```

## Installing plugins for playing [video and audio](https://docs.fedoraproject.org/en-US/quick-docs/assembly_installing-plugins-for-playing-movies-and-music/)

```sh
sudo dnf install gstreamer1-plugins-{bad-\*,good-\*,base} gstreamer1-plugin-openh264 gstreamer1-libav --exclude=gstreamer1-plugins-bad-free-devel
```

```sh
sudo dnf install lame\* --exclude=lame-devel
```

```sh
sudo dnf group upgrade --with-optional Multimedia
```

## Install Your Favorite Apps

```sh
sudo dnf install unrar
```

## Backup system with Timeshift

```sh
sudo dnf install timeshift
```

## Backup your data with [Deja Dup](https://flathub.org/apps/details/org.gnome.DejaDup)

```sh
flatpak install flathub org.gnome.DejaDup
```

## Fedora Workstation ONLY

### Install GNOME Tweaks

```sh
sudo dnf install gnome-tweaks
```

### Install [Extension Manager](https://flathub.org/apps/details/com.mattjakeman.ExtensionManager) from flathub

```sh
flatpak install flathub com.mattjakeman.ExtensionManager
```

### Install Your [Extensions](https://www.youtube.com/watch?v=6yEJ43LLIJg)

## Install [ZSH](https://www.youtube.com/watch?v=fDuGKsQ3bV4)

## Fedora KDE Plasma ONLY

### Enable Video Thumbnails in Dolphin

- Install `ffmpegthumbs`

```sh
sudo dnf install ffmpegthumbs
```

- Enable it in Dolphin:

From Dolphin Open:  
Menu > Configure > Configure Dolphin > General > Previews > Video Files (ffmpegthumbs)

## Fedora Xfce ONLY

```sh
sudo dnf install tumbler tumbler-extras ffmpegthumbnailer
```