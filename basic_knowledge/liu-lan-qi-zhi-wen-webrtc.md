# 浏览器指纹：WebRTC

WebRTC是一种浏览器插件，通常被需要快速直接连接的网络应用程序所应用。WebRTC通过UDP协议来建立连接，因此它并不会通过你在浏览器配置文件中使用的代理服务器进行路由。即便您使用了代理，网站也能借此获取您真实的公共和本地IP地址。该插件可被用于泄漏你的本地IP地址或追踪媒体设备。

WebRTC插件会泄漏什么信息： 外网IP地址、 内网IP地址

## [#](liu-lan-qi-zhi-wen-webrtc.md#webrtc的不同模式) WebRTC的不同模式 <a href="webrtc-de-bu-tong-mo-shi" id="webrtc-de-bu-tong-mo-shi"></a>

**外网IP地址**

“基于IP配置WebRTC外网IP（Fill WebRTC Public IP based on the IP）”选项意味着，当您启动浏览器配置文件时，它首先会连到我们的服务器。我们将检测该浏览器配置文件的真实外部IP，将其返回并设置WebRTC的外网IP。如果你的IP在会话中途发生变更，WebRTC的外网IP地址也会立即相应地进行调整。

禁用此选项意味着网站无法通过您的浏览器Webrtc插件获取到您的IP地址。

**内网IP地址**

您在内网IP地址处点击“随机”，可以随机一个内网的IP地址。

有效的本地IP范围

192.168.0.0 to 192.168.255.255

一些本地IP地址的例子：

192.168.0.21 192.168.0.23

注意：如果您使用的是动态代理IP，建议您禁用Webrtc功能。
