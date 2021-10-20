# 浏览器指纹：插件

插件和浏览器附加组件不可混为一谈。附加组件是一种浏览器扩展程序，您通常可以从Chrome商店这样的地方下载。附加组件是在浏览器进程中运行的。浏览器附加组件的例子有AdBlock和Chostery。

相较之下，插件通常预装在浏览器中，或从第三方网站被下载。插件的例子有Flash和Widevine。插件通常在一个单独的进程中运行，它该进程拥有当前活跃用户的所有权利，从而可能导致各种漏洞。

## [#](liu-lan-qi-zhi-wen-cha-jian.md#开启插件的风险) 开启插件的风险 <a href="kai-qi-cha-jian-de-feng-xian" id="kai-qi-cha-jian-de-feng-xian"></a>

一些如Flash或Widevine这样的插件有一个记录在案的API，允许它从母机获取各种惟一可识别的数据点。 其他的插件也可能有这样一个API，无论是公共还是私有的，都可能会给在线隐私带来威胁。由于插件本质上是闭源的二进制文件，所以没有可靠的方法来评估某个插件可能拥有哪些安全漏洞。

## [#](liu-lan-qi-zhi-wen-cha-jian.md#通过枚举法生成指纹) 通过枚举法生成指纹 <a href="tong-guo-mei-ju-fa-sheng-cheng-zhi-wen" id="tong-guo-mei-ju-fa-sheng-cheng-zhi-wen"></a>

另一风险来自于浏览器插件枚举。即使网站不能或不愿通过插件API获取唯一可识别的数据，它仍然可以以插件列表的形式收集唯一可识别数据。一个包含每个版本的插件列表可以显著缩小用户所属的段。多个浏览会话可以基于这些数据单独链接在一起，或者与其他数据点相结合。x8浏览器就是通过这种方法来模拟插件指纹的。

Firefox和Chrome中的默认插件 默认情况下，Firefox没有安装插件。 Chrome则有四个捆绑插件：

Chrome PDF Chrome PDF viewer Native client （本机客户端） Widevine Content Decryption Module （Widevine内容解密模块）
