# Share a folder with Windows guest in Virt Manager

## Host Steps

- Create a `/shared/folder/on/host` on the Host.
- Open VM settings > Memory and enable `shared memory` or add:

```xml
<memoryBacking>
  <source type="memfd"/>
  <access mode="shared"/>
</memoryBacking>
```

- Add Hardware - Filesystem:

> Change `source dir` and `target dir` to fit your setup

```xml
<filesystem type="mount" accessmode="passthrough">
  <driver type="virtiofs" queue="1024"/>
  <source dir="/shared/folder/on/host"/>
  <target dir="shared-folder-name-on-guest"/>
  <address type="pci" domain="0x0000" bus="0x06" slot="0x00" function="0x0"/>
</filesystem>
```

- Download [WinFsp](https://github.com/winfsp/winfsp/releases/latest)
- Start Windows VM

## Windows VM Steps

- Copy `WinFsp` file to the VM and Install it
- Open Services and find `VirtIO-FS Service` set it to `Automatic` and start it.
- Restart