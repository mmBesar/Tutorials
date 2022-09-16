# Virt Manager KVM

## support الدعم

### Hardware support المعالج

KVM requires that the virtual machine host's processor has virtualization support (named **VT-x** for Intel processors and **AMD-V** for AMD processors). You can check whether your processor supports hardware virtualization with the following command:

```sh
lscpu | grep Virtualization
```

If nothing is displayed after running th command, then your processor does not support hardware virtualization, and you will not be able to use KVM.

>Note: You may need to enable virtualization support in your BIOS. All x86_64 processors manufactured by AMD and Intel in the last 10 years support virtualization. If it looks like your processor does not support virtualization, it is almost certainly turned off in the BIOS.

### Kernel support النواة

ensure that the kernel modules are automatically loaded, with the command:

```sh
lsmod | grep kvm
```

## Install التنصيب

### Fedora 36 +

- حزم أساسية

```sh
sudo dnf install virt-manager qemu-kvm libvirt virt-viewer virt-install python3-libguestfs virt-top bridge-utils guestfs-tools libguestfs-tools libvirt-devel 
```

- حزم إضافية

```sh
sudo dnf install genisoimage dnsmasq libosinfo libosinfo-devel
```

For More [Fedora Docs](https://docs.fedoraproject.org/en-US/quick-docs/getting-started-with-virtualization/)

### Ubuntu 22.04 + 

```sh
sudo apt install virt-manager
```

For More [Ubuntu Docs](https://help.ubuntu.com/community/KVM/VirtManager)

### Arch

Find the steps at [Arch WiKi](https://wiki.archlinux.org/title/Virt-Manager)

## Add user to `kvm` and `libvirt` groups

```sh
sudo usermod -aG kvm,libvirt $USER
```

## Restart the system

## Dynamically Allocated Disk in KVM - إنشاء وحدة تخزين ذات مساحة متغيرة

- Create a 120 GB Disk:

```sh
qemu-img create -f qcow2 -o preallocation=off 120-disk.qcow2 120G
```

- Script:

```sh
#!/bin/sh

read -p "Enter the disk size in GBs like "80G": " a
while [[ -z "$a" ]]; do
	read -p "Enter the disk size, please! " a
done

qemu-img create -f qcow2 -o preallocation=off $a-disk.qcow2 $a
```