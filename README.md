说明
---

翻译内容大部分机翻（因为有些词组比较简单）新人对编译不是很懂，官方luci-app-mwan3又没有中文包，迫于需求便顺带练手翻译了一下（其实没啥技术含量），除了摸索一下编译的文件结构外，都是靠搬运大神代码稍作修改利用，因为网上找不到现成的也就发出来分享一下！<br/>
对一些网络名词也不是很懂，所以翻译过程都凭感觉，觉得不好的直接修改/i18n/mwan3.zh-cn.po文件就好.

编译方法
---

从 OpenWrt 的 [SDK][openwrt-sdk] 下载编译工具

```bash
# 解压 SDK 工具
tar xjf OpenWrt-SDK-<Platform>-for-linux-x86_64-gcc-<version>-linaro-uClibc-<version>.tar.bz2
cd OpenWrt-SDK-<Platform>-for-linux-x86_64-gcc-<version>-linaro-uClibc-<version>

# Clone 项目
git clone https://github.com/sunkai2012sky/mwan3-zh-cn.git package/luci-i18n-mwan3

# 编译 po2lmo
pushd package/luci-i18n-mwan3/tools/po2lmo
make && sudo make install
popd

# 进入 LuCI -> X. Lcui-i18n -> luci-i18n-mwan3 按M键选中并保存退出
make menuconfig

# 开始编译
make package/luci-i18n-mwan3/compile V=99
```

[openwrt-sdk]: https://wiki.openwrt.org/doc/howto/obtain.firmware.sdk
