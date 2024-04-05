# PVE-OpenCore
# Better_OSX_on_PVE
[中文](README_CN.md)  

### ⚠️⚠️⚠️ You are viewing the Dev branch! There may be unavailable push notifications here, please use [stable branch](https://github.com/laobamac/PVE-OpenCore/)in production environment.The issue proposed in Dev will not be merged into a stable branch until it is officially released! ⚠️⚠️⚠️

To install macOS on PVE more easily.

# Advantages
## Fewer bugs amd smaller file than KVM-OpenCore
1.Easy to use(due the macos basesystem inside) （the macOS recovery won't be provided after [V20240224](https://github.com/laobamac/PVE-OpenCore/tree/V20240224),a single recovery image will take its place）  

2.Newer OC and macOS version(Installing online is always the newest version of macOS)   

3.Easy to change settings(You could use OCC or OCAT even Notepad to edit the config.plist after uncompress the .img with ultraiso)

# Status

* OS: tested in 11.0-14.x
* Opencore: 0.9.8
    * NVRAM: native
    * AppleHotKey: works
    * FileVault: OK（Already patched for machines which have AVX2 patches）
    * Boot-Audio: works with onboard audio passthrough
    * OVMF: you can use latest version other than the old way(patched one).More information please try it yourself.
* SMBIOS: iMacPro1,1
* NIC: vmxnet3/e1000-82545em/virtio-net/passthrough
* CPU:
    * Only tested Intel Host,but the AMD Host(with patches) or Penryn should work,too.
* GPU Passthrough: works
    * HDMI/DP Audio: works
    * Metal Support: works
    * H264 Hardware Decoding: works
    * H265 Hardware Decoding: works
* Handoff: works with specific Wifi/Bluetooth(Already disable BRCM drivers)
* USB(Passthrough): works
* Power Manages
  * Sleep: works,you can also use PVE to suspend the VM
  * CPU AGPM: wo don't need CPU AGPM because hypervisor handled it well, this is for GPU AGPM
  * GPU AGPM: works

# Usage
1. Download the img file from releases page
2. Upload the .img to you PVE 8
3. Create a VM correctly and boot with the .img
4. Start installing macOS online

# Credits
https://github.com/Leoyzen/KVM-Opencore/  
https://github.com/acidanthera/OpenCorePkg/  
https://github.com/thenickdude/KVM-Opencore/  
