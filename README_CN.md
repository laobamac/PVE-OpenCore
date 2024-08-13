# PVE-OpenCore
# Better_OSX_on_PVE
[English](README.md)
[开发版分支](https://github.com/laobamac/PVE-OpenCore/tree/dev)  <br>QQ交流群 734284448<br>
更加简单高效地在PVE安装macOS

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

# 优点
## 修复了KVM-OpenCore 3+个Bug....
## 拥有比 KVM-OpenCore 更小的体积！
1.易于使用（内置macOS在线安装的recovery环境）（在[V20240224](https://github.com/laobamac/PVE-OpenCore/releases/tag/V20240224)后不再提供包含recovery的引导，将会单独提供recovery镜像！）   

2.更新的OpenCore和macOS版本（在线安装的macOS总是最新版的）   

3.更简单地修改配置（在使用ultraiso解包后你可以用OCC,OCAT甚至记事本修改config.plist）

# 状态

* 系统版本: 已测试 11.0-15.0b5
* Opencore: 1.0.1 Mod
    * NVRAM: 原生
    * AppleHotKey: 没问题！
    * FileVault: 没问题！（已对打了AVX2补丁的版本添加Patch！）
    * Boot-Audio: 直通声卡后可以！（虚拟卡暂不清楚）
    * OVMF: 就该用这个！
* SMBIOS: iMacPro1,1
* NIC: vmxnet3/e1000-82545em/virtio-net/直通网卡
* CPU:
    * 只试了Intel Host，但是Penryn和打香草补丁后的AMD应该也可以
* GPU 直通: 没问题！
    * HDMI/DP Audio: 没问题
    * Metal : 支持
    * H264 硬解: 支持
    * H265 硬解: 支持
* Handoff: 直通可驱动的博通网卡后可以，默认关闭了博通卡驱动，请自行启用
* USB(直通控制器): 没问题
* 电源管理
  * Sleep: 支持，你也可以用PVE挂起虚拟机
  * CPU AGPM: 没必要，PVE自带的按需模式足够
  * GPU AGPM: 可以，自带了iMacPro的AGPM.kext

# 使用
1. 从[Releases](https://github.ink/laobamac/Better_OSX_on_PVE/releases)下载最新版本引导文件
2. 上传到PVE 8
3. 正确创建一个虚拟机并使用引导文件启动
4. 开始在线安装macOS
5. 安装后会自动隐藏多余启动项，仅保留macOS。若发现多余项目，请按照[dortania的安装指导](https://dortania.github.io/OpenCore-Install-Guide/)或其他文档修改ScanPolicy或删除com.apple.recovery.boot以隐藏安装项

# 引用
https://github.com/Leoyzen/KVM-Opencore/  
https://github.com/acidanthera/OpenCorePkg/  
https://github.com/thenickdude/KVM-Opencore/  

# 备注
1.如果你遇到了问题，请先尝试已关闭的反馈中提到的方法，如果仍未解决再提出issue。无意义的issue将被直接关闭。</br>
2.本项目主要针对Q35机型，i4400fx机型不会主动维护，但本项目还将包括适配i4400fx的版本，以支持直通iGPU的hackintosh。</br>
3.如果你也是Hackintosh的爱好者，并且有PVE的经验，我期待着欢迎新人加入这个项目！</br>
4.本项目的分支文件（*.zip）不会主动更新，主要版本将在发布中发布。因此，请不要在没有特殊需求的情况下下载sources.zip。只有重大更改才会更新相应的 EFI 文件夹，并且在所有其他情况下只会发布 *.img 和 single*.img。
