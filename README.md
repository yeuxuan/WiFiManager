#WiFiManager

##开发版本



带回退web配置门户的Espressif ESPx WiFi连接管理器



：警告：此文档已过期，请参阅下面的注释



![发布](https://img.shields.io/github/v/release/tzapu/WiFiManager?include_prereleases)



[！[构建CI状态](https://github.com/tzapu/WiFiManager/actions/workflows/compile_library.yml/badge.svg)](https://github.com/tzapu/WiFiManager/actions/workflows/compile_library.yml)



[！[构建CI状态示例](https://github.com/tzapu/WiFiManager/actions/workflows/compile_examples.yaml/badge.svg)](https://github.com/tzapu/WiFiManager/actions/workflows/compile_examples.yaml)



[！[arduino图书馆徽章](https://www.ardu-badge.com/badge/WiFiManager.svg?)](https://www.ardu-badge.com/WiFiManager)



[！[使用PlatformIO构建](https://img.shields.io/badge/PlatformIO-Library-orange?)](https://platformio.org/lib/show/567/WiFiManager/installation)



[！[ESP8266](https://img.shields.io/badge/ESP-8266-000000.svg?longCache=true&style=flat&colorA=CC101F)](https://www.espressif.com/en/products/socs/esp8266)



[！[ESP32](https://img.shields.io/badge/ESP-32-000000.svg?longCache=true&style=flat&colorA=CC101F)](https://www.espressif.com/en/products/socs/esp32)

[！[ESP32](https://img.shields.io/badge/ESP-32S2-000000.svg?longCache=true&style=flat&colorA=CC101F)](https://www.espressif.com/en/products/socs/esp32-s2)

[！[ESP32](https://img.shields.io/badge/ESP-32C3-000000.svg?longCache=true&style=flat&colorA=CC101F)](https://www.espressif.com/en/products/socs/esp32-c3)



会员间支持/聊天



[！[在以下位置加入聊天：https://gitter.im/tablatronix/WiFiManager](https://badges.gitter.im/tablatronix/WiFiManager.svg)](https://gitter.im/tablatronix/WiFiManager?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge）



[！[不和谐](https://img.shields.io/badge/Discord-WiFiManager-%237289da.svg?logo=discord)](https://discord.gg/dkjJbHwC)



配置门户是一种固定的类型，因此在各种设备上，只要您连接到创建的接入点，它就会显示配置对话框。



**这适用于ESP8266 Arduino平台**



[https://github.com/esp8266/Arduino](https://github.com/esp8266/Arduino)



**这适用于ESP32 Arduino平台**



[https://github.com/espressif/arduino-esp32](https://github.com/espressif/arduino-esp32)



###已知问题

*需要更新文档，请参阅[https://github.com/tzapu/WiFiManager/issues/500](https://github.com/tzapu/WiFiManager/issues/500)

-------



##内容

-[工作原理]（#工作原理）

-[Wishlist]（#Wishlist）

-[快速启动]（#快速启动）

-安装

-[Arduino-通过库管理器]（#通过库管理者安装）

-[Arduino-来自Github]（#从GitHup结帐）

-[PlatformIO]（#使用Platformios安装）

-[使用]（#Using）

-[文档]（#文档）

-[接入点密码]（#密码保护配置接入点）

-[回调]（#回调）

-[配置入口超时]（#配置入口超时）

-[按需配置]（#按需配置门户）

-[自定义参数]（#自定义参数）

-[自定义IP配置]（#自定义IP配置）

-[过滤低质量网络]（#过滤网络）

-[调试输出]（#Debug）

-[故障排除]（#故障排除）

-[发布]（#发布）

-[贡献者]（#贡献和感谢）




##它是如何工作的

-当ESP启动时，它会将其设置为Station模式，并尝试连接到以前保存的接入点

-如果不成功（或未保存以前的网络），则将ESP移动到接入点模式，并启动DNS和Web服务器（默认ip 192.168.4.1）

-使用带有浏览器（计算机、手机、平板电脑）的任何支持wifi的设备连接到新创建的接入点

-由于捕获门户和DNS服务器，您将获得“加入网络”类型的弹出窗口，或者将您尝试访问的任何域重定向到配置门户

-选择一个扫描的访问点，输入密码，单击保存

-ESP将尝试连接。如果成功，它会将控制权交还给您的应用程序。如果没有，请重新连接到AP并重新配置。

-可以选择更改此行为或独立手动启动configportal和webportal，以及在非阻塞模式下运行它们。



##看起来怎么样

![ESP8266 WiFi专属门户主页](http://i.imgur.com/YPvW9eql.png) ![ESP8266 WiFi专属门户配置](http://i.imgur.com/oicWJ4gl.png)



##愿望清单

-[x]删除对EEPROM库的依赖

-[x]将HTML字符串移动到PROGMEM

-[x]清理和简化代码（尽管这是正在进行的）

-[x]如果设置了超时，则在AP模式下获取页面时将其扩展

-[x]添加配置比ssid/密码更多参数的功能

-[x]可能允许在重新启动后设置ESP的ip

-[x]添加到Arduino库管理器

-[x]添加到PlatformIO

-[]添加多组网络凭据

-[x]允许用户自定义CSS

-[]重写文档