### Host Installation
- virt-manager qemu qemu-utils
- sudo systemctl enable/start libvirtd

### Forward Ports
- qemu-system-i386 ... -net user,hostfwd=tcp:443::443 -redir tcp:80::80 -redir tcp:22::22 -hda storage.img -nographic

### Converting VMs
- qemu-img convert -f raw -O qcow "/dir/machine.vdi" "/dir/machine.img"

### Cloning VMs
- virt-clone --original /dir/c8n1.img --name "new name" --file c8n2.img
- virt-clone --original "c8n0" --name "c8n1" --auto-clone
- virt-clone --connect=qemu:///system -o "vm" -n "newvm" --auto-clone
- OR copy .img; then use virt-manager to create a new VM; use the .img

### Create a blank .img drive
- sudo qemu-img create -f raw drive.img 20G
- sudo gparted
- sudo fdisk -l

#### (!) When resize2fs use SAME type as creation (!)

### Increase .img size
- sudo qemu-img resize "/dir/vm.img" +10G (+20G, etc.)

#### Decrease .img size
- sudo qemu-img resize "/dir/vm.img" -10G (-20G, etc.)

#### Write .img to drive
- sudo dd if=/dir/qemu/vm.img of=/dev/sXX

#### Networking
- Packages: ebtables & dnsmasq
- Check box for Link State: Active

#### Audio
- Crash after every sound event?
- Install gstreamer plugins
- gst-plugins(star)
- reboot

#### GPU Passthrough to Windows 10 (Arch Linux: 220406)
```
yay -S system76-power
```
```
sudo systemctl enable com.system76.PowerDaemon.service
```
```
sudo systemctl start com.system76.PowerDaemon.service
```
- Consult https://wiki.archlinux.org/title/PCI_passthrough_via_OVMF for GPU indentification (vfio-pci.ids=)
- To add them via virt-manager GUI
    - Right click VM > Open > View Details > Add Hardware > PCI Host Device > ${vfio-pci.id}
    - Most modern GPUs have one ID for video, and one ID for HDMI audio (not to self: missing one ID can halt VM startup).
```
sudo system76-power graphics integrated && sudo vim /etc/default/grub
```
- Comment out existing GRUB_CMDLINE_LINUX_DEFAULT (the following line is for Thinkpad X1 Extreme G2 w/Nvidia 1650 Max-Q)
```
++ GRUB_CMDLINE_LINUX_DEFAULT="quiet loglevel=3 nowatchdog nvme_load=YES intel_iommu=on igfx_off kvm.ignore_msrs=1 vfio-pci.ids=10de:1f91,10de:10fa
```
```
update-grub
```
- Reboot
- To revert the process so that the host has GPU access comment out above and use this line instead
```
sudo vim /etc/default/grub
```
```
++ GRUB_CMDLINE_LINUX_DEFAULT="quiet loglevel=3 nowatchdog nvme_load=YES kvm.ignore_msrs=1
```
```
update-grub
```
- Reboot

### Video
- VRAM (Default: QXL 16M)
    - Go to preferences
    - Check box for XML editing
    - Go to VM video preferences
    - Exit XML and add vram="64000" #or whatever amount is needed
    - OR change vgamem="" for QXL
    - 16M=16384, 32M=32768, 64M=65536, 120M=122880, 240M=245760
- Install kernel-headers
- Virtio w/3D Acceleration
    - Virtio as GPU
    - Check 3D Acceleration & change VRAM to 32M+
    - Display Spice
        - Listen type: None
        - Check OpenGL
            - Select GPU
    - Guest needs mesa >= 11.2 compiled with option..
        - gallium-drivers=virgl

#### USB Passthrough
- sudo addgroup vbox
- sudo usermod -aG vbox chris
- Installing to USB via VMM
    - Add new USB device that points to USB drive in VMM console
        - Otherwise Live ISOs won't detect USB drives etc.

#### Guest Storage Basic (SATA)
- VirtIO Disk 1 > Virtual Disk > Advanced Options > Disk bus: SATA

#### Virsh
- Virsh w/vim
    - sudo EDITOR=vim virsh
- Static IPs
    - sudo virsh net-edit default
    - ```++ <host mac='' name='' ip=''/>```
    - sudo virsh net-destroy default
    - sudo virsh net-start default

#### Start VM with host startup
- Domain setup w/virt-manager
- virsh list --all
- virsh autostart <domain>
- virsh autostart <domain> --disable (if needed)
- virsh net-autostart default
- sudo systemctl enable libvirtd
- ++ Give wheel passwordless permission cuz reasons..
- vim /vm_autostart_script.sh
- ++ #!/bin/bash
- ++ sudo virt-viewer --domain <domain> -f
- ++ while pgrep -u $USER qemu > /dev/null; do
- ++    sleep 5
- ++ done
- ++ poweroff
- add script to startx.. add startx to ~/.profile..

#### Webdav
- Add hardware > Channel > spice webdav
- Install spice-webdav via guest
- Also: gvfs-fuse

#### Resources
- https://wiki.archlinux.org/title/PCI_passthrough_via_OVMF
