# elementary OS 6 - Post Install

## Update and Clean

* Update

```bash
sudo apt update && sudo apt upgrade -y
```

* Clean

```bash
sudo apt autoremove && sudo apt autoclean
```

## Change the Hostname

1. Change the hostname using `hostnamectl`

```bash
sudo hostnamectl set-hostname NEW-NAME
```

2. Edit the /etc/hosts file

```bash
sudo nano /etc/hosts
```

## Install Pantheon Tweaks

Install the required packages

```bash
sudo apt install -y software-properties-common
```

Add the repository

```bash
sudo add-apt-repository -y ppa:philip.scott/pantheon-tweaks
```

Install Pantheon Tweaks

```bash
sudo apt install -y pantheon-tweaks
```

## Flatpak

Add Flathub as a system remote:

```bash
flatpak remote-add --if-not-exists flathub --system https://flathub.org/repo/flathub.flatpakrepo
```

Install Apps (e.g. VLC)

* system-wide:

```bash
flatpak install --system flathub org.videolan.VLC
```

* user:

```bash
flatpak install --user flathub org.videolan.VLC
```
