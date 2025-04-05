# ThinkPad T14 Gen1 Ventura OpenCore 1.0.3
<img style="float:right" src="/images/aboutThisMachine.png" alt="Lenovo Thinkpad T14 Gen1 Hackintosh OpenCore" width="280">

[![macOS](https://img.shields.io/badge/macOS-13.7-blue)](https://developer.apple.com/documentation/macos-release-notes)
[![OpenCore](https://img.shields.io/badge/OpenCore-1.0.3-green)](https://github.com/acidanthera/OpenCorePkg)
[![ThinkPad](https://img.shields.io/badge/ThinkPad-T14Gen1.i7-orange)](https://think.lenovo.com.cn/index.html)


**免责声明:**

### 作者：[@wjxwang](https://github.com/wjxwang)
此仓库主要作为我的备份使用。
在开始之前，请阅读整个自述文件。
我对可能造成的任何损失不承担任何责任。
如果您发现错误或有任何改进（无论是在配置中还是在文档中），请考虑打开问题或拉取请求。

## 简介
- 此仓库为ThinkPad T14 Gen1 i7创建。
- 固态更换为WD Blue SN550。
- 声卡 layout-id = 96，内置麦克风无输入（尚未解决）。
- 可外接eGPU使用，外接显卡型号为RX5500XT 8G。
- 支持 Ventura、Monterey。
- 支持 同盘EFI引导win10。
- USBmap为自制，不适用于其他代产品。
- 支持YogaSMC，支持风扇转速查看与调节。
- 需卸载OCLP补丁后进行小版本的升级。

## 硬件信息
``` 
- CPU：Intel Core i7-10510U
- 集成显卡：Intel(R) UHD Graphics 620 (支持HDMI)
- eGPU：雷凌Pro显卡扩展坞 + AMD Radeon RX 5500 XT 8G (可实现内屏、HDMI、eGPU三屏显示，HEVC正常)
- 声卡：ALC257 (Intel SST内置麦克风无输入，common issue laptop with Intel Smart Sound Technology)
- 无线网卡：Intel(R) Wi-Fi 6 AX201
- 硬盘： WD Blue SN550 (原自带三星硬盘无解)
```

## 升级Sequoia(15.3.1) 详解
``` 
1、升级时，需加载RestrictEvents.kext，boot-args添加revpatch=auto,sbvmm,asset，屏蔽兼容性检测，否则无法下载更新包。
2、升级时，需将Misc->Security->SecureBootModel设为Disabled,DmgLoading设为Any。否则无法完成重启后的正式安装升级。
3、升级后，AirportItlwm驱动无法加载，需配合OCLP打补丁使用原ventura驱动。具体方法为：
①加载AMFIPass.kext、IOSkywalkFamily.kext、IO80211FamilyLegacy.kext、IO80211FamilyLegacy.kext/Contents/PlugIns/AirPortBrcmNIC.kext。
②boot-args添加 -amfipassbeta ipc_control_port_options=0。
③Misc->Delete->7C436110-AB2A-4BBB-A880-FE41995C9F82添加csr-active-config，boot-args。
④Misc->Add->7C436110-AB2A-4BBB-A880-FE41995C9F82添加csr-active-config：03080000。
⑤Kernel->Block阻止IOSkywalkFamily。Identifier填写：com.apple.iokit.IOSkywalkFamily，Enabled 设置为 true，MinKernel 设置为： 23.0.0。
⑥然后使用OCLP进行intel无线网卡打补丁。
4、升级后，Bluetooth无法使用，将IntelBluetoothFirmware.kext更新至2.5.0，BlueToolFixup.kext更新至2.6.9，boot-args添加bluetoothExternalDongleFailed=00，bluetoothInternalControllerInfo=00000000 00000000 D03C1F69 C21E(后12位为蓝牙的MAC地址)。
5、升级后，OCLP补丁将会导致增量系统更新将不再起作用，每次更新需下载完整的 macOS 安装程序。故在增量更新前需卸载补丁，升级完毕后重新打补丁。

``` 


##
## 参考

- [@CLAY-BIOS](https://github.com/CLAY-BIOS/Lenovo-ThinkPad-T450s-Hackintosh-OpenCore) ThinkPad X250 OpenCore
- [@Baio1977](https://github.com/Baio1977/Lenovo-Thinkpad-T14) Lenovo-Thinkpad-T14
- [@askwakhid](https://github.com/askwakhid/ThinkPad-T14-macOS-OpenCore) ThinkPad-T14-macOS-OpenCore