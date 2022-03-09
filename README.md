
fros固件openwrt框架源码，通过该源码编译出来的固件可以安装应用过滤、上网审计、上网认证、游戏管控等fros插件  

## 演示视频  

https://www.bilibili.com/video/BV1Yq4y167Qu

## 固件下载地址  
https://destan19.github.io/download-bin/  


编译脚本和ipk持续更新中  
## 如何编译
> 编译方法和openwrt编译方法一样

1. clone源码
```
git clone https://github.com/destan19/openfros.git
```
2. 下载安装第三方包(feeds)   
如果你想要集成第三方插件，可以在feeds config文件中增加，或者直接放在package目录  

```
./scripts/feeds  update -a
./scripts/feeds  install -a
```
如果这一步报错，切换网络或者搭建梯子后编译  

3. 选择产品并编译固件  
make menuconfig 选择你要编译的产品   
并选择你想要编译的插件，如果需要集成第三方插件，可以先下载到package目录然后make menuconfig进行选择 
必需选择的库：  
libjson-c libblobmsg-json libubox libubus

make V=s  完成固件编译

## 源码说明
该源码基于lean 的lede源码，仓库地址  
https://github.com/coolsnowwolf/lede.git 

### 特性
- 内核版本较少变动  
保持内核版本稳定不变，主要是为了方便安装一些内核模块插件，  
因为内核模块依赖内核版本，内核版本没必要追新，稳定够用就可以了。  
并且商用固件内核版本一般还是3.x，所以不要过度关注内核版本。  
- 加入内核补丁  
用于支持内核模块的开发，需要增加一些内核patch  

## 插件安装
在release中会定期发布fros ipk文件，可以选择安装，也可以用一键脚本安装
安装插件注意保持安装顺序，先要安装库的依赖
可以参考一键脚本：
安装脚本为install.sh
卸载脚本为remove.sh

安装过程中如果报了依赖错误，可以编译出对应库并进行安装。  

## 免责声明
插件不会包含任何后门，不会窃取用户隐私数据。  
应用识别采用标准的协议分析，  
都是公开的标准协议，统计数据只用于本地页面显示，不会上报任何服务器，请大家放心使用。  
插件不会在每个产品一测试，如果安装后有问题，可以恢复出厂或者卸载。  
该插件引起的任何问题，与作者无关。  

## 插件发布
新版本发布会通过微信公众号第一时间通知，请关注微信公众号: OpenWrt  


