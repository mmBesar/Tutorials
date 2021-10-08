## macOS Theme for Ubuntu

## Steps

  1. Download Packages
  ```bash
  sudo apt install git gnome-tweaks -y
  ```

  2. Install [Firefox Extension](https://extensions.gnome.org)

  3. Install Extensions
	- [Dash to Dock](https://extensions.gnome.org/extension/307/dash-to-dock)
		- Set Dock Position to the Bottom
		- Disable Intelligent autohide
	- [User Themes](https://extensions.gnome.org/extension/19/user-themes)

  4. Install the main theme, Open Terminal and Run: 
  ```bash
  cd Downloads
  git clone https://github.com/vinceliuice/WhiteSur-gtk-theme.git
  cd WhiteSur-gtk-theme
  ./install.sh -c dark -c light -i ubuntu -N mojave
  ./tweaks.sh -f -d
  ```

  5. Install icons 
  ```bash
  cd ..
  git clone https://github.com/vinceliuice/WhiteSur-icon-theme.git
  cd WhiteSur-icon-theme
  ./install.sh
  ```

  6. Install cursors 
  ```bash
  cd ..
  git clone https://github.com/vinceliuice/McMojave-cursors
  cd McMojave-cursors
  ./install.sh
  ```

  7. Install Wallpaper 
  ```bash
  cd ..
  wget https://codeload.github.com/vinceliuice/WhiteSur-gtk-theme/zip/wallpapers
  unzip wallpapers
  cd WhiteSur-gtk-theme-wallpapers
  sudo ./install-gnome-backgrounds.sh
  ```

  8. Install Ulauncher 
  ```bash
  sudo add-apt-repository ppa:agornostal/ulauncher
  sudo apt update
  sudo apt install ulauncher -y
  ```

  9. Install `wmctrl` for Wayland 
  ```bash
  sudo apt install wmctrl -y
  ```

  10. SET Super+u for `ulauncher-toggle`
