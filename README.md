# This is the master branch!
This repository is going to keep using the term "**master**". It **never changes**.
I **refuse** to switch to "main".

## R2S 基于原生OpenWRT 的固件 (AS IS, NO WARRANTY!!!)

### 发布地址：
（可能会翻车，风险自担，需要登录GitHub账号后才能下载，不提供任何形式的技术支持）  
https://github.com/KaneGreen/R2S-OpenWrt/actions  
![OpenWrt for R2S](https://github.com/KaneGreen/R2S-OpenWrt/workflows/OpenWrt%20for%20R2S/badge.svg?branch=master&event=push)

### 本地一键编译命令：
安装依赖（测试编译环境为Ubuntu 18.04）：
```shell
sudo -E apt-get install -y build-essential rsync asciidoc binutils bzip2 gawk gettext git libncurses5-dev libz-dev patch unzip zlib1g-dev lib32gcc1 libc6-dev-i386 subversion flex uglifyjs git-core gcc-multilib g++-multilib p7zip p7zip-full msmtp libssl-dev texinfo libreadline-dev libglib2.0-dev xmlto qemu-utils upx libelf-dev autoconf automake libtool autopoint ccache curl wget vim nano python python3 python-pip python3-pip python-ply python3-ply haveged lrzsz device-tree-compiler scons
wget -O - https://raw.githubusercontent.com/friendlyarm/build-env-on-ubuntu-bionic/master/install.sh | bash
```
为你的Git设置用户名和邮箱（已经配置过的请跳过）：
```shell
git config --global user.name "YourName" && git config --global user.email "noreply@example.com"
```
一键编译：
```shell
git clone https://github.com/KaneGreen/R2S-OpenWrt.git && cd R2S-OpenWrt && bash onekeyr2s.sh
```
（注意：本仓库对该脚本的维护较为消极，可能需要更具实际情况yml文件具体内容修改后才能使用。）
### 注意事项：
1. 登陆IP：`192.168.1.1`，密码：无。

2. OpenWrt内置升级可用

3. SSRP使用姿势： ①添加你要的订阅链接 ②再在最后加一行空行 ③右下角点一下保存并应用 ④更新所有订阅服务器节点。

4. LAN WAN 已交换，和原厂接口定义相反（现在LAN口是远离电源接口的那一个RJ45接口）；LAN 和 WAN 的灯可能不亮。

5. 遇到上不了网的，请自行排查自己的IPv6连接情况，或禁用IPv6（同时禁用WAN和LAN的IPv6）

6 .LAN灯不亮是openwrt上游的问题，请耐心等待上游修复，sys灯引导时闪烁，启动后常亮，也是上游的设定，有疑问请联系OpenWrt官方社区

### 版本信息：
其他模块版本：SNAPSHOT（当日最新）

LUCI版本：19.07（当日最新）

### 特性及功能：
1. O3编译，核心频率1.5GHz，获得更高的理论性能。

2. 内置四款主题，包含SSRP，OpenClash，PASSWALL，AdGuard Home，SQM，网络唤醒，DDNS，UPNP，FullCone（默认开启），流量分载（软件或SFE，二选一，防火墙中手动开启），BBR（默认开启）。  
[完整功能列表](./featurelist.md)

3. Github Actions里面的编译结果包含SHA256哈希校验和MD5哈希校验文件。同样的内容也会显示在Actions的编译日志的`Cleaning and hashing`步骤（倒数第四步）里。**请注意核对和校验固件文件的完整性！**

4. [清盘刷机教程](./howto_cleanflash.md)  [变更日志](./CHANGELOG.md)

### 其他信息
由于添加了`shadow-utils`组件，管理页面上的`更改密码`功能失效。  
请使用SSH空密码登陆后，执行`passwd`命令并根据提示设置密码。

### 三代壳OLED相关
未编译安装OLED的luci-app，有需要者自行寻找软件包安装，或者下载源码后使用本固件自带的gcc和make编译。

### 感谢
* [QiuSimons](https://github.com/QiuSimons/R2S-OpenWrt)  
* [quintus-lab](quintus-lab/Openwrt-R2S)
* 以及其他所有曾为R2S做出努力的贡献者们。
