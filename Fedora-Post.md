# Fedora Post-installation Steps

## General Steps

* Speed up DNF

Set fastestmirror

```sh
sudo echo 'fastestmirror=true' | sudo tee -a /etc/dnf/dnf.conf
```

Set deltarpm #optional
 
```sh
echo 'deltarpm=true' | sudo tee -a /etc/dnf/dnf.conf
```

Set parallel downloads #optional

```sh
echo 'max_parallel_downloads=5' | sudo tee -a /etc/dnf/dnf.conf
```

* Enable [RPM Fusion](https://docs.fedoraproject.org/en-US/quick-docs/setup_rpmfusion/) 

    1. free
    
    ```sh
    sudo dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm
    ```
    
    2. nonfree
    
    ```sh
    sudo dnf install https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
    ```

* Update

```sh
sudo dnf --refresh upgrade
```

* [Flatpak](https://flatpak.org/setup/Fedora)

```sh
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

* Enable Third-Party Repositories

* Install [NVIDIA Drivers](https://rpmfusion.org/Howto/NVIDIA)

* Installing plugins for playing [video and audio](https://docs.fedoraproject.org/en-US/quick-docs/assembly_installing-plugins-for-playing-movies-and-music/)

```sh
sudo dnf install gstreamer1-plugins-{bad-\*,good-\*,base} gstreamer1-plugin-openh264 gstreamer1-libav --exclude=gstreamer1-plugins-bad-free-devel
```

```sh
sudo dnf install lame\* --exclude=lame-devel
```

```sh
sudo dnf group upgrade --with-optional Multimedia
```

* Install [ZSH](https://www.youtube.com/watch?v=fDuGKsQ3bV4)

* Install Your Favorite Apps

* Backups and Snapshots !!


## Fedora Workstation ONLY

* Install GNOME Tweaks

```sh
sudo dnf install gnome-tweaks
```

* Install file-roller

```sh
sudo dnf install file-roller
```

* Install [Extension Manager](https://flathub.org/apps/details/com.mattjakeman.ExtensionManager) from flathub

```sh
flatpak install flathub com.mattjakeman.ExtensionManager
```

* Install Your [Extensions](https://www.youtube.com/watch?v=6yEJ43LLIJg)

## Fedora KDE Plasma ONLY

* Enable Video Thumbnails in Dolphin

1. Install `ffmpegthumbs`

```sh
sudo dnf install ffmpegthumbs
```

2. Enable it in Dolphin:

From Dolphin Open:  
Menu > Configure > Configure Dolphin > General > Previews > Video Files (ffmpegthumbs)