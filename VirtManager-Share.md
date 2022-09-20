# Virt Manager - Share with Linux Guest

## ClipBoard, Drag and Drop - مشاركة النصوص

- Debian - Ubuntu

```sh
sudo apt install spice-vdagent
```

- Fedora

```sh
sudo dnf install spice-vdagent
```

- Arch

```sh
sudo pacman -S spice-vdagent
```

- NixOS

add the below line to `configuration.nix`

```nix
services.spice-vdagentd.enable = true;
```

---------

## Shared Folder - مشاركة الملفات

### Requirements

- qemu-kvm version 5.0 at least

```sh
qemu-kvm -version
```

### On Host

- creat the folder you want to share

- Open VM settings > Memory and enable `shared memory` or add:

```xml
<memoryBacking>
  <source type="memfd"/>
  <access mode="shared"/>
</memoryBacking>
```

- Add Hardware and chose Filesystem:

    - Driver `virtiofs`
    - Source path `/shared/folder/on/host`
    - Target path `shared-folder-name-on-guest`

Or add

```xml
<filesystem type="mount" accessmode="passthrough">
  <driver type="virtiofs"/>
  <source dir="/shared/folder/on/host"/>
  <target dir="shared-folder-name-on-guest"/>
  <address type="pci" domain="0x0000" bus="0x07" slot="0x00" function="0x0"/>
</filesystem>
```

- Start your VM

### On Guest

- Creat a folder to mount the share

```sh
mkdir host-share
```

- Run:

```sh
sudo mount -t virtiofs shared-folder-name-on-guest /path/to/mount/on/guest
```

- auto mount

```sh
sudo nano /etc/fstab
```

append

```s
shared-folder-name-on-guest  /path/to/mount/on/guest  virtiofs  defaults  0  0
```

or 

```sh
echo "shared-folder-name-on-guest  /path/to/mount/on/guest  virtiofs  defaults  0  0" | sudo tee -a /etc/fstab
```

- Mount

```sh
sudo mount -a
```

or

```sh
sudo reboot now
```

### NixOS Guest

```sh
sudo nano /etc/nixos/configuration.nix
```

```nix
  systemd.mounts = [
    {
      what = "shared-folder-name-on-guest";
      where = "/path/to/mount/on/guest";
      type = "virtiofs";
      wantedBy = [ "multi-user.target" ];
      enable = true;
    }
  ];
```

```sh
sudo nixos-rebuild switch
```

```sh
sudo reboot now
```