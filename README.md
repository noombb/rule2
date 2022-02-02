500 / Simple Config GeoIP for Quantumult X (QuantumultX) / Clash 预配置文件: Apple News 解锁规则 + 捷径, 去广告分流规则, TikTok 解锁 Rewrite, 神机分流规则, VIP 视频解析重写 + 捷径

## 简介
> + 整合多个 Quantumult X 配置文件, 利用 GeoIP 特性, 剔除部分规则, 精简规则和配置文件
- [使用方法](https://github.com/smxl/500#使用方法)
- [分流规则和重写](https://github.com/smxl/500#分流规则和重写)
- [捷径](https://github.com/smxl/500#捷径)
- [小工具](https://github.com/smxl/500#小工具)
- [Clash 配置](https://github.com/smxl/500#clash-配置)
- [配置文件更新](https://github.com/smxl/500#配置文件更新)
- [推荐](https://github.com/smxl/500#推荐)

## 声明

本项目在多个 [Quantumult X](https://apps.apple.com/us/app/quantumult-x/id1443988620) 配置文件上进行了修改、整理、收集和拓展

本项目 Github 地址: [https://github.com/smxl/500](https://github.com/smxl/500)

由 Vercel 提供的托管地址: [https://cnn.vercel.app](https://cnn.vercel.app)

##  使用方法

如你不使用本配置的证书, 可下载配置文件后删除 p12= 后面的字符, 修改的文件导入 Quantumult X 从 3 开始操作

1. 下载或复制配置文件

文件|地址|说明
-|-|-
23_03.cer|[23_03.cer](https://github.com/smxl/500/blob/main/static/23_03.cer?raw=true)|证书, Thor 生成无需 passphrase, 500-cnn-cert.conf 需安装
500-cnn-cert.conf|[500-cnn-cert.conf](https://github.com/smxl/500/raw/main/500-cnn-cert.conf)|需安装证书的配置文件, 已填写 p12 且无需 passphrase, 链接为 vercel.app 重定向

2. Quantumult X - 风车 - 配置文件 -下载 - 粘贴 - 确定

3. 可选: Mitm - 生成证书 - 配置证书 - 安装证书

4. 系统 - 设置 - 通用 - 关于 - 信任证书

5. Quantumult X - 风车 - 节点 - 引用 (订阅) - 右上角添加 - 填写标签和资源路径 (自己的机场订阅链接)

6. Quantumult X - 风车 - 其他设置 - GeoLite2 来源 添加 GeoIP

7. GeoIP2-CN 二选一 (复制链接或下载导入)
> - [Hackl0us](https://github.com/Hackl0us/GeoIP2-CN/raw/release/Country.mmdb)
> - [soffchen](https://github.com/soffchen/GeoIP2-CN/raw/release/Country.mmdb)

8. 如你没有自己的订阅链接, 可直接使用, 若需要使用自己的订阅, 可把配置文件中 [server_remote] 下方 https://(500|cnn).pages.dev/xv-sub 改为你的订阅链接

9. 启动, 由于 Quantumult X 不支持 url schema / url-schema 启动, 建议打开 其他设置 - VPN - 始终开启, 剩余开关按需选择

注: 本配置文件默认的订阅链接为网上公开的信息, 对隐私需求较高的用户不建议长期使用, 另外本配置使用了公开的 MITM 证书, 如果你也有 Thor, 建议自行生成替换 (生成证书后, 导出时不输入密码即可跳过 passphrase)

## 分流规则和重写

tag 名|类型|短链|介绍
-|-|-|-
ads|规则|https://cnn.vercel.app/xf-ads|去广告阻止
cn|规则|https://cnn.vercel.app/xf-cn|大陆服务直联
global|规则|https://cnn.vercel.app/xf-global|国际服务
hijacking|规则|https://cnn.vercel.app/xf-hijacking|防劫持
privacy|规则|https://cnn.vercel.app/xf-privacy|隐私
tg|规则|https://cnn.vercel.app/xf-tg|Telegram
unbreak|规则|https://cnn.vercel.app/xf-unbreak|规则修正
-|||-
adlite|重写|https://cnn.vercel.app/xr-adlite|复写去广告
ads|重写|https://cnn.vercel.app/xr-ads|重写去广告
adscript|重写|https://cnn.vercel.app/xr-adscript|脚本去广告
apple|重写|https://cnn.vercel.app/xr-apple|解锁受限的 Apple 服务, Apple News, AQI US, Siri 建议
aqi|重写|https://cnn.vercel.app/xr-aqi|AQI US, 单独使用
bili|重写|https://cnn.vercel.app/xr-bili|Bilibili 界面优化
box|重写|https://cnn.vercel.app/xr-box|BoxJS
emby|重写|https://cnn.vercel.app/xr-emby|Emby 解锁, 无通知
fake|重写|https://cnn.vercel.app/xr-fake|Fake Pro 解锁, lk 的基础上进行了精简, 并增加了 Spotify Pro
jike|重写|https://cnn.vercel.app/xr-jike|即刻去直播
js|重写|https://cnn.vercel.app/xr-js|~~脚本去广告和比价~~
jsc|重写|https://cnn.vercel.app/xr-jsc|脚本获取 Cookies
lk|重写|https://cnn.vercel.app/xr-lk|国外服务 Fake VIP
tiktok|重写|https://cnn.vercel.app/xr-tiktok|TikTok US
upgrade|重写|https://cnn.vercel.app/xr-upgrade|屏蔽APP更新检查
youtube|重写|https://cnn.vercel.app/xr-youtube|YouTube 去广告
embyplus|重写|https://cnn.vercel.app/xr-embyplus|Emby 下载
jikeplus|重写|https://cnn.vercel.app/xr-jikeplus|即刻去直播, 去日记
res|重写|https://cnn.vercel.app/xr-res|大陆软件优化
search|重写|https://cnn.vercel.app/xr-search|DuckDuckGo 搜索引擎重写
v|重写|https://cnn.vercel.app/xr-v|VIP 视频解析重写
video|重写|https://cnn.vercel.app/xr-video|视频重写 3in1, 含 VIP 视频解析重写, TikTok US, YouTube 去广告

FAQ: 你可以根据自己的情况调整上述规则和重写是否需要启用, 举例: 如果你很少使用海外软件, 那么 ```lk 重写 https://cnn.vercel.app/xr-lk 国外服务 Fake VIP``` 其中提供的多款软件的 VIP/Pro 解锁则对你无用 [其中部分重写已经失效], 同理如此 ```fake https://cnn.vercel.app/xr-fake Fake Pro 解锁``` 是该规则的精简

## 捷径

演示效果:
- https://cnn.vercel.app/archive/apple-news-hevc.mp4
- https://cnn.vercel.app/archive/vip-video-hevc.mp4

捷径|作用|链接
-|-|-
Apple News QX|访问 Apple News 的捷径, 配合本配置文件|https://cnn.vercel.app/sc-news
Pade|捷径打开: 支付宝 [主扫 + 被扫 + 健康码], 云闪付 [被扫 + 乘车码], 微信 [主扫]|https://cnn.vercel.app/sc-pade
VIP Free|生成 VIP 视频解析网址的捷径, 可配合电视浏览器 + 远程输入法使用|https://cnn.vercel.app/sc-vip

FAQ: 你需要完成手机的基本设置才可以使用 Apple News QX, 比如修改 - 设置 - 通用 - 语言和地区 - 区域 - 美国 etc.

## 小工具

演示效果:
- https://cnn.vercel.app/archive/shu-ipa-hevc.mp4

工具|作用|链接/补充
-|-|-
无需重写||
ipa 安装|通过 shu 安装名为 app.ipa 的旧版本应用|https://cnn.vercel.app/static/ https://cnn.vercel.app/static/
V 视频|高可用解析, 在当前窗口播放视频|https://cnn.vercel.app/v?vv=视频地址 https://cnn.vercel.app/v.html?vv=视频地址 现已支持参数传入, 替换中文部分为网址即可使用
需要重写||
快速搜索|设置 Safari 默认搜索引擎为 DuckDuckGo|默认谷歌, 前缀两个字母指定其他搜索引擎 Baidu:bd/Magi:mm/Twitter:tt/YouTube:yt/WolframAlpha:wa + 空格 + 关键词
V 视频|高可用解析, 在当前窗口播放视频|https://v.im/v?vv=视频地址 现已支持参数传入, 替换中文部分为网址即可使用

[TikTok 21.0.0](https://transfer.sh/eFAkw1/TikTok%2021.0.0%20plist%20removed.ipa?cYGngGphgS7n) 11.09.2021 实测可用, ipa 已经去除 iTunesMetadata.plist 文件, 请用自己账户下载的 ipa 用 7zip 打开后替换安装

[YouTube 16.39.6](https://transfer.sh/iNfMMf/YouTube%2016.39.6%20plist%20removed.ipa?Y6QN9t6hWK8M) 12.01.2021 实测可用, ipa 已经去除 iTunesMetadata.plist 文件, 请用自己账户下载的 ipa 用 7zip 打开后替换安装, 此版本去广告后不会造成跳回视频片头

建议下载旧版本 [iTunes 12.6.5.3](https://support.apple.com/zh-cn/HT208079) 配合 [iOS旧版应用下载v5.1](https://wwx.lanzoui.com/iBE4Emzgbkj) 抓包或通过 [Fiddler](https://telerik-fiddler.s3.amazonaws.com/fiddler/FiddlerSetup.exe) 输入 ```bpu MZBuy.woa``` 添加断点, 手动修改版本 ID 为 ```843820050```

FAQ: 你需要使用非香港地区的代理才可以使用 TikTok, 这也是本配置文件默认不启用香港节点的原因

## Clash 配置

本项目同时提供了 Clash 配置文件, 使用了 proxy-providers, rule-providers 所以配置文件干净又简单

下载: [500-min-clash.yaml](https://github.com/smxl/500/raw/main/500-min-clash.yaml) 需要使用 [Premium Core](https://github.com/Dreamacro/clash/releases/tag/premium)

如果需要使用自己的订阅, 你需要替换字段 https://api.10101.io/sub?target=clash&url=https://gitee.com/sobweb/usefulScripts/raw/master/vmesslite|https://github.com/freefq/free/blob/master/v2?raw=true&list=true

你也可以修改注释中的 ```你的订阅链接```, 然后取消掉配置中全部注释

```
proxy-providers:
  # My: # 你也可以将 url 换成你的 clash 节点订阅链接
  #   type: http
  #   path: ./my.yaml
  #   url: https://api.10101.io/sub?target=clash&url=你的订阅链接&list=true
...
```

## 配置文件更新

500-cnn-cert.conf

[https://github.com/smxl/500/raw/main/500-cnn-cert.conf](https://github.com/smxl/500/raw/main/500-cnn-cert.conf)

[https://cnn.vercel.app/q](https://cnn.vercel.app/q)

500-min-clash.yaml

[https://github.com/smxl/500/raw/main/500-min-clash.yaml](https://github.com/smxl/500/raw/main/500-min-clash.yaml)

[https://cnn.vercel.app/c](https://cnn.vercel.app/c)

## 推荐

本配置文件引用了一些项目或服务, 你可以在 vercel.json 找到他们

为方便访问原项目, 配置文件中的引用方式均使用了 https://github.com/用户/项目/raw/分支/目录/文件 的形式
