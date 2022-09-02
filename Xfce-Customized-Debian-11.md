# Xfce Customized - Debian 11

## Install packages

```sh
sudo apt-get install gnome-themes-extra gtk2-engines-murrine gtk2-engines-pixbuf git wget
```

## Wallpaper

- Download the [Wallpaper](https://www.wallpaperflare.com/debian-linux-mountains-river-forest-nature-wallpaper-ypoud)

- Rename the file to `debian-wallpaper.jpg`

- Copy it to `/usr/share/backgrounds/`

```sh
sudo mv debian-wallpaper.jpg /usr/share/backgrounds/
```

- open Desktop or `xfdesktop-settings` and set the wallpaper

- in Icons TAB set `icon type` to `NONE` if you dont need desktop shortcuts

## Install Theme

```sh
cd Downloads
```

```sh
git clone https://github.com/vinceliuice/Graphite-gtk-theme.git
```

```sh
cd Graphite-gtk-theme
```

```sh
sudo ./install.sh -d /usr/share/themes
```

## Install Icons

```sh
cd ..
```

```sh
git clone https://github.com/vinceliuice/Tela-circle-icon-theme.git
```

```sh
cd Tela-circle-icon-theme
```

```sh
sudo ./install.sh -d /usr/share/icons
```

## Install Cursors

```sh
cd ..
```

```sh
git clone https://github.com/vinceliuice/Graphite-cursors.git
```

```sh
cd Graphite-cursors
```

```sh
sudo ./install.sh
```

## Install grub2 theme

```
cd ../Graphite-gtk-theme/other/grub2
```

```sh
sudo ./install.sh
```

## Install Fonts

```sh
cd ~/Downloads
```

```sh
mkdir fonts && cd fonts
```

```sh
wget https://fonts.google.com/download?family=Noto%20Sans%20Arabic -O NotoSansArabic.zip /
wget https://fonts.google.com/download?family=Arimo -O Arimo.zip /
wget https://fonts.google.com/download?family=Cousine -O Cousine.zip /
wget https://fonts.google.com/download?family=Tinos -O Tinos.zip /
wget https://fonts.google.com/download?family=Roboto -O Roboto.zip /
wget https://github.com/be5invis/Iosevka/releases/download/v15.6.3/ttf-iosevka-term-15.6.3.zip -O IosevkaTerm.zip
```

- Extract it to its folders

```sh
find . -name '*.zip' -exec sh -c 'sudo unzip -d /usr/share/fonts/"${1%.*}" "$1"' _ {} \;
```

- Config File

- Create `fontconfig` Folder

```bash
mkdir ~/.config/fontconfig
```

- Create `fonts.conf` file

```bash
nano ~/.config/fontconfig/fonts.conf
```

- Copy the below to the file

```xml
<?xml version='1.0'?>
<!DOCTYPE fontconfig SYSTEM 'fonts.dtd'>
<fontconfig>
  <!-- Set preferred serif, sans serif, and monospace fonts. -->
  <alias>
   <family>sans-serif</family>
   <prefer>
    <family>Arimo</family>
    <family>Noto Sans Arabic</family>
   </prefer>
  </alias>

  <alias>
   <family>serif</family>
   <prefer>
    <family>Tinos</family>
    <family>Noto Sans Arabic</family>
   </prefer>
  </alias>

  <alias>
   <family>Sans</family>
   <prefer>
    <family>Arimo</family>
    <family>Noto Sans Arabic</family>
   </prefer>
  </alias>

  <alias>
   <family>monospace</family>
   <prefer>
    <family>Cousine</family>
    <family>Noto Sans Arabic</family>
   </prefer>
  </alias>
  <!-- Aliases for commonly used MS fonts. -->
  <match>
    <test name="family"><string>Arial</string></test>
    <edit name="family" mode="assign" binding="strong">
      <string>Arimo</string>
    </edit>
  </match>
  <match>
    <test name="family"><string>Helvetica</string></test>
    <edit name="family" mode="assign" binding="strong">
      <string>Arimo</string>
    </edit>
  </match>
  <match>
    <test name="family"><string>Verdana</string></test>
    <edit name="family" mode="assign" binding="strong">
      <string>Arimo</string>
    </edit>
  </match>
  <match>
    <test name="family"><string>Tahoma</string></test>
    <edit name="family" mode="assign" binding="strong">
      <string>Arimo</string>
    </edit>
  </match>
  <match>
    <!-- Insert joke here -->
    <test name="family"><string>Comic Sans MS</string></test>
    <edit name="family" mode="assign" binding="strong">
      <string>Arimo</string>
    </edit>
  </match>
  <match>
    <test name="family"><string>Times New Roman</string></test>
    <edit name="family" mode="assign" binding="strong">
      <string>Tinos</string>
    </edit>
  </match>
  <match>
    <test name="family"><string>Times</string></test>
    <edit name="family" mode="assign" binding="strong">
      <string>Tinos</string>
    </edit>
  </match>
  <match>
    <test name="family"><string>Courier New</string></test>
    <edit name="family" mode="assign" binding="strong">
      <string>Cousine</string>
    </edit>
  </match>
</fontconfig>
```

- Press CTRL+O to Save

- Press CTRL+X to Exit

- Update Fonts and Config

```bash
sudo fc-cache -fv
```

---

## Set Theme

- Open Appearance Settings

  * set Style to Graphite-Dark
  * set Icons to Tela circle dark
  * set Default Font to Roboto Regular
  * set Default Monospcae Font to Iosevka Term Regular

- Open Mouse and Touchpad
  * set Theme to Graphite light Cursors

- Open Window Manager Settings

- in Style
  * set theme to Graphite-Dark
  * set Title Font to Roboto Regular

- Open Window Manager Tweaks Settings

  * in Copositor
  * set Opacity to your liking
  * uncheck Show shadows under dock windows

---

## Xfce Panel 

- Open Panel Preferences

- in Display: 

  * set Mode to Deskbar  
  * set Row size to 50  

- in Appearance:  

  * set Fixed icon size (pixels) to 23
  * set Opacity Enter to `80` and Leave to `80`
- in Items
  * add Whisker Menu and move it to the top
  * remove Applications Menu
  * remove Window Buttons
  * remove the first Separator
  * select the second Separator and set its Appearance to Expand
  * remove Workspace Switcher
  * add System Load Monitor
  * remove Clock
  * add DateTime item for DATE only and set Font
  * add DateTime item for TIME only and set Font
  * add Keyboard Layouts and configure it

- open Settings for Action Buttons on the panel

  * Set Appearance to Action Buttons
  * uncheck all items but `LogOut..`
  * check Show comfirmation dialog

- open Settings for Status Tray Items

  * Set Fixed icon size (pixels) to 16


- add Weather item and set it up



- REMOVE PANAEL 2

---

## Whisker Menu

open Whisker Menu settings

- In Appearance

  * Select Show as list
  * uncheck Show Category Names
  * uncheck Show application tooltip
  * uncheck Show application descriptions
  * uncheck Position categories next to panel button
  * Set Application icon size to Small
  * Set Background opacity to 80

- in Panel Button

  * Click on the Icon
  * set Select icon from to All Icons
  * Search for Search Icon and select it and hit OK
  * check Use a single panel row

- in Behavior

  * set Default Category to All Applications
  * for Menu Check Switch categories by hovering

- in Commands
  * uncheck all

- Open the Whisker Menu and expand it to the bottom of the screen

- Set Super Key open Whisker Menu

  * Open Keyboard Settings > Application Shortcuts  
  * Click Add  
  * Command: `xfce4-popup-whiskermenu`


## Plank Dock

- Install plank dock

```sh
sudo apt install plank
```

- open it from the app menu

- Theme it

```sh
mkdir ~/.local/share/plank/themes/shade && wget https://raw.githubusercontent.com/kennyh7279/plank-themes/main/shade/dock.theme -O ~/.local/share/plank/themes/shade/dock.theme
```

- open plank settings

```sh
plank --preferences
```

in Appearance

Set Theme to shade  
Set Icon Size to 40  
Enable Icon Zoom and set it to 135  

in Docklets

add Desktop to the Dock

- close the pank settings

- add your apps to the dock

- add plank to start up apps

Open Session and Startup settings > Application Autostart

add new item

Name: Plank Dock  
Description: Plank Dock  
Command: plank  
Trigger: on login  

---

## Ulauncher

- Donwload [Ulauncher](https://ulauncher.io/#Download)

- Install the DEB file
```bash
sudo apt install ./ulauncher*.deb -y
```

- Create a Dir for theme

```sh
mkdir -p ~/.config/ulauncher/user-themes
```

- Download and install Matcha-Dark-Azul

```sh
git clone https://github.com/matbme/Matcha-dark-aliz-for-ULauncher.git ~/.config/ulauncher/user-themes/Matcha-dark-aliz
```

- Make Sure it auto start from ULauncher Settings

---

## slick-greeter

- Install slick-greeter

```sh
sudo apt install slick-greeter lightdm-settings
```

- Open Login Window

in Appearance Set the Theme and Background

in Users Turn OFF `Hide the user list`

- Restart the system

## ZSH

- Install Packages

```bash
sudo apt install zsh ranger
```

- Create the Folders

```bash
mkdir -p ~/.config/zsh/plugins && mkdir -p ~/.cache/zsh
```

- Move '.zshrc' file to '$HOME/.config/zsh'

```sh
echo -e '\n\n# zsh\nexport ZDOTDIR="$HOME/.config/zsh"\n[[ ! -f "$HOME/.local/bin/" ]] || PATH="$PATH:$HOME/.local/bin/"\nexport LESSHISTFILE=-' >> ~/.zshenv
```

- Download Fonts

```bash
wget https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf -P ./MesloLGS-NF
```

- Install Fonts

```bash
sudo mv MesloLGS-NF /usr/share/fonts
```

- Set the shell font

Set the shell font to MesloLGS NF Regular

> Close and reopen the terminal

Set the shell font to MesloLGS NF Regular

- Download Plugins

```sh
git clone https://github.com/zsh-users/zsh-autosuggestions.git ~/.config/zsh/plugins/autosuggestions && git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.config/zsh/plugins/syntax-highlighting && git clone --depth 1 -- https://github.com/marlonrichert/zsh-autocomplete.git ~/.config/zsh/plugins/autocomplete && git clone https://github.com/spaceship-prompt/spaceship-prompt.git --depth=1 ~/.config/zsh/plugins/spaceship-prompt
```

- Create `.zshrc` file


```sh
nano ~/.config/zsh/.zshrc
```

- copy the below to the file

```sh
# Aliases
alias ls='ls --color=auto'
alias ll='ls -lah --color=auto'
alias grep='grep --color=auto'
alias update='sudo apt update && sudo apt upgrade -y && flatpak update -y'
alias clean='sudo apt autoremove -y && sudo apt autoclean -y && flatpak remove --unused -y'


# Use vi keybindings even if our EDITOR is set to vi
bindkey -e

setopt histignorealldups sharehistory autocd extendedglob nomatch notify

# history
HISTFILE=~/.config/zsh/.histfile
HISTSIZE=10000
SAVEHIST=10000

# Use modern completion system
autoload -Uz compinit
compinit

#--- Plugins Options ---#

source ~/.config/zsh/plugins/syntax-highlighting/zsh-syntax-highlighting.zsh
source ~/.config/zsh/plugins/autosuggestions/zsh-autosuggestions.zsh
source ~/.config/zsh/plugins/autocomplete/zsh-autocomplete.plugin.zsh
source ~/.config/zsh/plugins/spaceship-prompt/spaceship.zsh

# ranger-cd
function ranger-cd {
    tempfile="$(mktemp -t tmp.XXXXXX)"
    /usr/bin/ranger --choosedir="$tempfile" "${@:-$(pwd)}"
    test -f "$tempfile" &&
    if [ "$(cat -- "$tempfile")" != "$(echo -n `pwd`)" ]; then
        cd -- "$(cat "$tempfile")"
    fi  
    rm -f -- "$tempfile"
}

#ranger-cd will run by alt+r
bindkey -s "^\er" "ranger-cd\n"
```

- Press CTRL+O to Save

- Press CTRL+X to Exit

- ZSH as the default shell 

* for `root`

```bash
sudo -s
```

```bash
chsh -s /bin/zsh root
```

```bash
exit
```

* for `user`

```bash
chsh -s /bin/zsh $USER
```

- Restart the System