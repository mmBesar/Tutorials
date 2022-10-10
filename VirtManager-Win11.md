# Install Windows 11 in Virt Manager

## Requirements

- Download [Windows 11 ISO](https://www.microsoft.com/software-download/windows11)
- Download [VirtIO WIN ISO](https://github.com/virtio-win/virtio-win-pkg-scripts)
- Install `swtpm` and `edk2-ovmf` as shown below:

Fedora

```sh
sudo dnf install swtpm edk2-ovmf
```

Ubuntu

```sh
sudo apt install swtpm ovmf
```

Arch

```sh
sudo pacman -S swtpm edk2-ovmf
```

## Creat new VM with

- Create `qcow2` file (find out [how](https://www.youtube.com/watch?v=B4ExUl3mnco))
- Add Hardware TPM (Emulated - CRB - 2.0)
- Firmware to UEFI x86_64 with secure boot (OVMF_CODE.secboot.fd)
- Set Disk to `VirtIO`
- Add 2nd cdrom with `virtio-win.iso` mounted
- Set network card to `VirtIO`
- Set Display to `Spice`
- Set Video to `QXL`

## Boot the VM
- Where do you want to install windows ?
    - Click `Load driver`
    - Browse
    - VirtIO CDrom
    - amd64
    - w11
    - OK
    - Next
    - New
    - Apply
    - OK
    - Next
## Post Install
- Shutdown the system and add new `Channel` to the VM with `org.qemu.guest_agent.0` as a Name and Device Type `UNIX socket (unix)`
- Start the system and Install `virtio-win-guest-tools` from VirtIO ISO.
- Restart