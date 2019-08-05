#### 硬件配置

主板：[技嘉 BM250M](http://www.gigabyte.cn/Motherboard/GA-B250M-D3H-rev-10)

CPU: [i7 7700](https://ark.intel.com/content/www/us/en/ark/products/97128/intel-core-i7-7700-processor-8m-cache-up-to-4-20-ghz.html)

显卡: [RX 580 8G](https://www.amd.com/en/products/graphics/radeon-rx-580)

内存：32 GB 2666 MHz DDR4

硬盘：SSD（256GB） + HDD（2T）

蓝牙： USB 蓝牙适配器，CSR 芯片，蓝牙版本为 4.0

键盘： NiZ 静电容键盘

鼠标：罗技蓝牙鼠标 M558

![](https://github.com/Titzanyic/Clover/blob/rx580/other/10.14.png)

#### 下载镜像

使用 **macOS Mojave 10.14.6 18G87 正式版 with Clover**  版本更方便，驱动大部分都已经集成并更新至适合当前系统的状态，基本上不用调整可以直接安装。推荐 [黑苹果小兵](https://blog.daliansky.net/)，有详细的安装步骤和资源文件。[点击使用迅雷下载系统](https://mirrors.dtops.cc/iso/MacOS/daliansky_macos/macOS%20Mojave%2010.14.6%2818G87%29%20Installer%20with%20Clover%205033.dmg)

#### 制作引导盘

使用 [etcher](https://etcher.io/) 工具把下载的镜像写入到 U 盘中。

#### 从引导启动

开机通过快捷键进入启动方式切换，选择 **UEFI：XXXX，Partition** 通过 U盘引导的方式启动。

#### 格式化硬盘

进入系统后，选择磁盘工具，格式化需要电脑中的硬盘，格式我选择 APFS。

#### 安装 Mac OS

退出磁盘工具后，直接选择系统安装，磁盘选择我们格式化的电脑硬盘。

#### 重新启动

重启后，再次进入 Clover，这次选择从 MacOS 启动，也就是本地磁盘。直接安装系统就可以了。

#### 驱动情况

网卡：正常，局域网传输文件可以达到千兆。

显卡：正常，支持 4K 显示器输出，支持多屏幕输出。

蓝牙： 正常， 可以连接蓝牙鼠标和键盘，不支持接力和隔空传送（没有无线网卡）。

USB： 正常，USB 3.0 可以读取可以达到硬盘的理论值速度。

#### 声卡调试

唯独只有声音不正常，打开 Clover Configurator.app 挂载 EFI 分区，通过 Clover Configurator.app 打开 cconfig.list 文件，选择【设备设置】，在 Audio 区域，选择注入，并设置参数为 1，重启电脑，打开 【系统偏好设置】选择【声音】，输入和输出都选择内建，声音就可以正常输出了。

![](https://github.com/Titzanyic/Clover/blob/rx580/other/voice.png)



#### 其它问题

- 调试声卡的时候，由于在【系统偏好设置】中默认输出不是内建，一直以为是驱动和配置的问题，其实切换下就可以了。
- 罗技的蓝牙鼠标不支持系统驱动中设置的自定义按键，通过卸载并重新安装罗技的驱动恢复正常。
- 安装的时候虽然对硬盘格式化为 Mac OS 扩展（日志式），但是在安装的时候仍然无法识别。原因是这个硬盘之前安装 Window 10 的时候，分区表类型为 MBR 格式，使用 DiskGenius 转换为 GUID 格式就可以了。

- MacOS 10.14 系统更新是在系统偏好设置中，如果不更新会有红点提示，强迫症难受。通过在终端执行一下命令就可以实现隐藏。

```shell
defaults write com.apple.systempreferences AttentionPrefBundleIDs 0
killall Dock
```

更多分享欢迎关注公众号：

![](http://img.yingxiaoshi.com//20190220174803.jpg)
