# Best Arabic Font in Linux

* Create `fonts.conf` in `~/.config/fontconfig/` with the below content

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

then run

```bash
fc-cache -fv
```

or

```bash
sudo fc-cache -f -v
```

----

## Step by Step

`sudo apt install ubuntu-restricted-extras ubuntu-restricted-addons`

1. Download and Install Fonts

`NotoSansArabic-hinted` `Arimo` `Cousine` `Tinos` Fonts and extract and run

https://bit.ly/3jdmH4a  
https://bit.ly/35TxicB  
https://bit.ly/35P6fPt  
https://bit.ly/3xQHi2d  
https://bit.ly/3qmvO42  

https://google.com/get/noto/#sans-arab  
https://fonts.google.com/specimen/Arimo  
https://fonts.google.com/specimen/Cousine  
https://fonts.google.com/specimen/Tinos  

```bash
find . -name '*.zip' -exec sh -c 'unzip -d "${1%.*}" "$1"' _ {} \;
```

Set Permistions to `NotoSansArabic-hinted` folder

```bash
chmod 644 NotoSansArabic-hinted/*
```

Install on System

```bash
sudo cp -r Arimo Cousine Tinos NotoSansArabic-hinted /usr/share/fonts/
```

2. Config File

```bash
mkdir ~/.config/fontconfig
```

```bash
cp font-conf/fonts.conf ~/.config/fontconfig
```

3. Update Fonts and Config

```bash
sudo fc-cache -fv
```

4. Firefox

Change Sans-serif Arabic font to `Noto Sans Arabic` or `Noto Sans Arabic UI`

5. Reboot

```bash
sudo reboot now
```

## For FlatPak apps

copy the `fonts.conf` file to `~/.var/app/APP-FOLDER/config/fontconfig/`