# PVE-OpenCore
# Better_OSX_on_PVE
[English](README.md)
[开发版分支](https://github.ink/laobamac/PVE-OpenCore/tree/dev)  
更加简单高效地在PVE安装macOS

# 优点
## 修复了KVM-OpenCore 3+个Bug....
## 拥有比 KVM-OpenCore 更小的体积！
1.易于使用（内置macOS在线安装的recovery环境）   

2.更新的OpenCore和macOS版本（在线安装的macOS总是最新版的）   

3.更简单地修改配置（在使用ultraiso解包后你可以用OCC,OCAT甚至记事本修改config.plist）

# 状态

* 系统版本: 已测试 11.0-14.x
* Opencore: 0.9.8
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
5. 安装后请修改ScanPolicy或删除com.apple.recovery.boot以隐藏安装项

# 引用
https://github.com/Leoyzen/KVM-Opencore/  
https://github.com/acidanthera/OpenCorePkg/  
https://github.com/thenickdude/KVM-Opencore/  
