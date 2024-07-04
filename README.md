# PVE-OpenCore
# Better_OSX_on_PVE
[中文](README_CN.md)
[Dev version](https://github.com/laobamac/PVE-OpenCore/tree/dev)

To install macOS on PVE more easily.

<div align="center">
  <a href="https://github.com/laobamac"><img width="100px" alt="logo" src="https://github.com/laobamac/PVE-OpenCore/raw/stable/po-logo.svg"/></a>
  <p><em>🖥A macOS bootloader for PVE, based on OpenCore, powered by laobamac.</em></p>
<div>
  <a href="https://github.com/laobamac/PVE-OpenCore/blob/main/LICENSE">
    <img src="https://img.shields.io/github/license/laobamac/PVE-OpenCore" alt="License" />
  </a>
  <a href="https://github.com/laobamac/PVE-OpenCore/releases">
    <img src="https://img.shields.io/github/release/laobamac/PVE-OpenCore" alt="latest version" />
  </a>
</div>
</div>

# Advantages
## Fewer bugs amd smaller file than KVM-OpenCore
1.Easy to use(due the macos basesystem inside)（the macOS recovery won't be provided after [V20240224](https://github.com/laobamac/PVE-OpenCore/releases/tag/V20240224),a single recovery image will take its place）   

2.Newer OC and macOS version(Installing online is always the newest version of macOS)   

3.Easy to change settings(You could use OCC or OCAT even Notepad to edit the config.plist after uncompress the .img with ultraiso)

# Status

* OS: tested in 11.0-15.0(❗️Sequoia need adding a arg:-lilubetaall（Until now！！）,latest release doesn't has it!Please add it by yourself.❗️)
* Opencore: 1.0.0
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
5. Unnecessary startup items will be automatically hidden after installation, and only macOS will be kept. If you find any redundant items, modify the ScanPolicy by following [dortania's installation guide] (https://dortania.github.io/OpenCore-Install-Guide/) or other documentation or delete com.apple.recovery.boot to hide the installation items

# Credits
https://github.com/Leoyzen/KVM-Opencore/  
https://github.com/acidanthera/OpenCorePkg/  
https://github.com/thenickdude/KVM-Opencore/  

 # Notes
 1.If you're having trouble, try the approach mentioned in the closed feedback first, and then open an issue if it's still not resolved. Meaningless issues will be closed.</br>
 2.This project is mainly for the Q35 model, the i4400fx model will not be actively maintained, but this project will also include a version adapted to the i4400fx to support the hackintosh of the pass-through iGPU.</br>
 3.If you're also a Hackintosh enthusiast and have experience with PVE, I'm looking forward to welcoming new people to the project!</br>
 4.The branch files (*.zip) of this project will not be actively updated, and major versions will be released in the release. So please do not download sources.zip without special needs. Only significant changes will update the corresponding EFI folder, and only *.img and single*.img will be published in all other cases.
