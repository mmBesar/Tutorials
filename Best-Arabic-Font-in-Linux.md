# Best Arabic Font in Linux

> This Guide is for Ubuntu, Fedora 36+ has these configs by default.

1. Update System

```sh
sudo apt update
```

2. Install `ubuntu-restricted-extras`

```sh
sudo apt install ubuntu-restricted-extras ubuntu-restricted-addons
```

3. Download and Install Fonts

- Download the below fonts

[Noto Sans Arabic](https://fonts.google.com/specimen/Noto+Sans+Arabic)  
[Arimo](https://fonts.google.com/specimen/Arimo)  
[Cousine](https://fonts.google.com/specimen/Cousine)  
[Tinos](https://fonts.google.com/specimen/Tinos)  

- Extract it to its folders

```bash
find . -name '*.zip' -exec sh -c 'unzip -d "${1%.*}" "$1"' _ {} \;
```

- Install it on the system

```bash
sudo cp -r Arimo Cousine Tinos Noto_Sans_Arabic /usr/share/fonts/
```

4. Config File

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

5. Update Fonts and Config

```bash
sudo fc-cache -fv
```

6. Firefox

Change Sans-serif Arabic font to `Noto Sans Arabic` or `Noto Sans Arabic UI`

7. Reboot

```bash
sudo reboot now
```

## For FlatPak apps

copy the `fonts.conf` file to `~/.var/app/<APP-FOLDER>/config/fontconfig/`

----

> Links from the old tutorial:  
https://bit.ly/3jdmH4a  
https://bit.ly/35TxicB  
https://bit.ly/35P6fPt  
https://bit.ly/3xQHi2d  
https://bit.ly/3qmvO42 