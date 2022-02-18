## 配置清单

参考文档：[OpenCore](https://dortania.github.io/OpenCore-Install-Guide/)

产品链接：[optiplex-3080-micro-desktop](https://www.dell.com/en-us/work/shop/desktops-all-in-one-pcs/optiplex-3080-micro-desktop/spd/optiplex-3080-micro)

CPU：[i3-10100T](https://ark.intel.com/content/www/cn/zh/ark/products/199284/intel-core-i310100t-processor-6m-cache-up-to-3-80-ghz.html)

内存： 16G DDR4 

硬盘：Intel SSD

显卡：英特尔® 超核芯显卡 630

无线模块：BCM943602CS

键盘：秒控键盘 1代

触控板：秒控板 3 代

显示器：LG HDR 4K

系统版本： macOS Monterey 12.1

## 安装步骤

### 设置 BIOS

- System Configuration > SATA Operation: AHCI

- Video > Primary Display: Intel HD Graphics
- Intel Software Guard Extensions > Intel SGX Enable: Disable
- Preformance > Intel Truboboost: 勾选
- DST Behavior > Adapter Wamings > 去掉勾选
- Virtualization Support > Virtualization: 去掉勾选
- Virtualization Support > VT for Direct I/O: 去掉勾选

### 修改 CFG Lock 和 DVMT

> 建议参考视频操作，视频来源：https://www.bilibili.com/video/BV1fo4y197Y4?from=search&seid=10436882289844670066&spm_id_from=333.337.0.0

1. 格式化 U盘尾 FAT32，并复制文件夹下 BIOS修改引导 EFI 文件夹到 U 盘，设置开启进入 U 盘系统；
2. 进入系统后按 ESC，“Alt” + “=” 进入菜单，”Ctrl“ + "F" 进入搜索；
3. 搜索 cpusetup，搜索两次，修改   Y 轴：0030 ；X 轴： 0E ，把默认值 01 修改为 00 ，回车确定，按 “Crtl” + “W”  保存修改；
4. 搜索 sasetup，Y 轴：00F0 ；X 轴： 05，把默认值 01 修改为 02。按 “Crtl” + “W”  保存修改；
5. 按 “ALT” + Q 退出；

## 解锁功能

- 随航
- 隔空投送
- Apple 解锁 Mac
- AirPlay to Mac
- 通用粘贴板、接力
