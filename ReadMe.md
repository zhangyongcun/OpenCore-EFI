## 配置清单

参考文档：[OpenCore](https://dortania.github.io/OpenCore-Install-Guide/)

CPU：[i7 8700K](https://ark.intel.com/content/www/cn/zh/ark/products/126684/intel-core-i7-8700k-processor-12m-cache-up-to-4-70-ghz.html)

主板：[Z370 Pro4](https://www.asrock.com/mb/Intel/Z370%20Pro4/index.asp)

内存： 64G DDR4 

硬盘：[Intel® SSD 750 Series](https://ark.intel.com/content/www/us/en/ark/products/86742/intel-ssd-750-series-400gb-2-5in-pcie-3-0-20nm-mlc.html)

显卡：  [RX580 8G](https://www.gigabyte.com/tw/Graphics-Card/GV-RX580GAMING-8GD-rev-10-11-12#kf)

蓝牙：USB 蓝牙适配器，CSR 芯片，蓝牙版本为 4.0

键盘：秒控键盘 1代

鼠标：罗技蓝牙鼠标 M558

显示器：LG HDR 4K

![bigsur](img/bigsur.png)

## 安装步骤

### 设置 BIOS

##### BIOS：

- 【Fast Boot】  **Disabled**
- 【GSM Support】 **Disabled** （推荐关闭，我测试不关闭不影响）

##### Peripherals：

- 【USB Configuration > XHCI Hand-off】  **Enabled**  （重要！！！）

##### Chipset

- VT-d Disabled
