# Better_OSX_on_PVE
[中文](https://github.ink/laobamac/Better_OSX_on_PVE/blob/main/README_CN.md)
To install macOS on PVE more easily.

# Advantages
1.Easy to use(due the macos basesystem inside)   

2.Newer OC and macOS version(Installing online is always the newest version of macOS)   

3.Easy to change settings(You could use OCC or OCAT even Notepad to edit the config.plist after uncompress the .img with ultraiso)

# Status

* OS: tested in 11.0-14.x
* Opencore: 0.9.8
    * NVRAM: native
    * AppleHotKey: works
    * FileVault: Maybe?
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
https://github.ink/Leoyzen/KVM-Opencore/  
https://github.ink/acidanthera/OpenCorePkg/  
https://github.ink/thenickdude/KVM-Opencore/  
