## Ubuntu Post Installation

* Remove Firefox Snap and Install Firefox Deb

    1. Remove Firefox Snap

    ```sh
    sudo apt remove --purge firefox
    ```
    ```sh
    sudo snap remove --purge firefox
    ```

    2. add Mozilla team PPA

    ```sh
    sudo add-apt-repository ppa:mozillateam/ppa
    ```

    3. set Mozilla team PPA as high Priority

    ```sh
    echo '
    Package: *
    Pin: release o=LP-PPA-mozillateam
    Pin-Priority: 1001
    ' | sudo tee /etc/apt/preferences.d/firefox
    ```

    or

    ```sh
    echo '
    Package: firefox*
    Pin: release o=LP-PPA-mozillateam
    Pin-Priority: 501
    ' | sudo tee /etc/apt/preferences.d/firefox
    ```

    - block the Ubuntu repo

    ```sh
    echo '
    Package: firefox*
    Pin: release o=Ubuntu*
    Pin-Priority: -1
    ' | sudo tee /etc/apt/preferences.d/firefox
    ```

    > **About Pin and PPA Priority:**  
    > *From apt man page*  
    > - P >= 1000:  
    causes a version to be installed even if this constitutes a downgrade of the package
    > - 990 <= P < 1000:  
    causes a version to be installed even if it does not come from the target release, unless the installed version is more recent
    > - 500 <= P < 990:  
    causes a version to be installed unless there is a version available belonging to the target release or the installed version is more recent
    > - 100 <= P < 500:  
    causes a version to be installed unless there is a version available belonging to some other distribution or the installed version is more recent
    > - 0 < P < 100:  
    causes a version to be installed only if there is no installed version of the package
    > - P < 0:  
    prevents the version from being installed
    > - P = 0:  
    has undefined behaviour, do not use it.


    4. set Firefox for automatic updates

    ```sh
    echo 'Unattended-Upgrade::Allowed-Origins:: "LP-PPA-mozillateam:${distro_codename}";' | sudo tee /etc/apt/apt.conf.d/51unattended-upgrades-firefox
    ```

    5. install Firefox DEB

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

* GNOME Tweaks and Extension Manager
```bash
sudo apt install gnome-tweaks gnome-shell-extension-manager
```