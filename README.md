# ThinkPad T14 Gen1 Monterey OpenCore 0.8.3
<img align="right" src="/images/aboutThisMachine.png" alt="Lenovo Thinkpad T14 Gen1 Hackintosh OpenCore" width="400">

[![macOS](https://img.shields.io/badge/macOS-12.6-blue)](https://developer.apple.com/documentation/macos-release-notes)
[![OpenCore](https://img.shields.io/badge/OpenCore-0.8.3-green)](https://github.com/acidanthera/OpenCorePkg)
[![ThinkPad](https://img.shields.io/badge/ThinkPad-T14Gen1-orange)](https://think.lenovo.com.cn/index.html)


**免责声明:**

### 作者：[@wjxwang](https://github.com/wjxwang)
此仓库主要作为我的备份使用。
在开始之前，请阅读整个自述文件。
我对可能造成的任何损失不承担任何责任。
如果您发现错误或有任何改进（无论是在配置中还是在文档中），请考虑打开问题或拉取请求。

## 简介
- 此仓库位ThinkPad T14 Gen1创建。
- 固态更换为WD Blue SN550。
- 声卡默认 layout-id = 86，内置麦克风无输入（尚未解决）。
- 可外接eGPU使用，外接显卡型号为RX5500XT 8G。
- 支持 Monterey。
- 支持 同盘EFI引导win10。

## 硬件信息
``` 
- CPU：Intel Core i7-10510U
- 集成显卡：Intel(R) UHD Graphics 630 (支持HDMI)
- eGPU：雷凌Pro显卡扩展坞 + AMD Radeon RX 5500 XT (可实现内屏、HDMI、eGPU三屏显示，HEVC正常)
- 声卡：ALC257 (内置麦克风无输入，其他OK)
- 无线网卡：Intel(R) Wi-Fi 6 AX201
- 硬盘： WD Blue SN550 (原自带三星硬盘无解)
```


##
## 参考

- [@CLAY-BIOS](https://github.com/CLAY-BIOS/Lenovo-ThinkPad-T450s-Hackintosh-OpenCore) ThinkPad X250 OpenCore
