# ThinkPad T14 Gen1 Ventura OpenCore 1.0.3
<img align="right" src="/images/aboutThisMachine.png" alt="Lenovo Thinkpad T14 Gen1 Hackintosh OpenCore" width="300">

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
- 支持YogaSMC，支持风扇转速查看于调节。
- 支持小版本的自动升级。

## 硬件信息
``` 
- CPU：Intel Core i7-10510U
- 集成显卡：Intel(R) UHD Graphics 620 (支持HDMI)
- eGPU：雷凌Pro显卡扩展坞 + AMD Radeon RX 5500 XT (可实现内屏、HDMI、eGPU三屏显示，HEVC正常)
- 声卡：ALC257 (内置麦克风无输入，其他OK)
- 无线网卡：Intel(R) Wi-Fi 6 AX201
- 硬盘： WD Blue SN550 (原自带三星硬盘无解)
```


##
## 参考

- [@CLAY-BIOS](https://github.com/CLAY-BIOS/Lenovo-ThinkPad-T450s-Hackintosh-OpenCore) ThinkPad X250 OpenCore
- [@Baio1977](https://github.com/Baio1977/Lenovo-Thinkpad-T14) Lenovo-Thinkpad-T14
- [@askwakhid](https://github.com/askwakhid/ThinkPad-T14-macOS-OpenCore) ThinkPad-T14-macOS-OpenCore