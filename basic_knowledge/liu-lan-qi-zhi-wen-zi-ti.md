# 浏览器指纹：字体

字体指纹识别是一种身份验证的方式。基于用户所使用的字体种类及字体在浏览器中被绘出的方式，网站可以进行指纹追踪。通常，网站在浏览器指纹识别时有两种运用字体的方法。

* 枚举字体列表
* 基于字体测量的指纹识别

您可以通过Borwserleaks.com查看这些方法是如何被应用的。

## [#](liu-lan-qi-zhi-wen-zi-ti.md#枚举字体列表) 枚举字体列表 <a href="mei-ju-zi-ti-lie-biao" id="mei-ju-zi-ti-lie-biao"></a>

收集电子设备上已安装的字列表的最常用方法是CSS的自我检测。简而言之，该方法通过测量浏览器上特定字体显示的一个短语的宽度来获取您的字体列表。如果宽度匹配，就意味着您安装了这种字体。如不匹配，则推定这种字体没有被安装。

通过循环检测可能安装的字体列表及宽度，网站可准确窥探一台设备安装了哪些字。

x8浏览器使用一种特殊算法来对抗这种探测方法，允许您控制可供网站枚举的字体以反追踪。

当您创建和保存一个浏览器配置文件时，x8浏览器会自动生成一个随机字体表，将其显示给网站终端。

## [#](liu-lan-qi-zhi-wen-zi-ti.md#基于字体测量的指纹识别-unicode-glyphs和domrect) 基于字体测量的指纹识别（Unicode glyphs和DOMRect） <a href="ji-yu-zi-ti-ce-liang-de-zhi-wen-shi-bie-unicodeglyphs-he-domrect" id="ji-yu-zi-ti-ce-liang-de-zhi-wen-shi-bie-unicodeglyphs-he-domrect"></a>

基于字体测量的指纹识别技术，即测量HTML元素的边界和尺寸，HTML元素可以用有着特定字体系列的文本进行填充。接着测量结果会被转换成哈希字符串标识符，以用于更精确的指纹识别。这种技术可被划为两种子分支。

* Unicode glyphs, 是针对特定字体系列中的单个字符的测量。
* DomRect (也被称为 getClientRects), 是对HTML元素的测量，其中的文本以特定字体系列呈现。

x8浏览器利用一系列不同的方法来对抗基于测量的字体指纹识别，最终，每个浏览器配置文件都会有一个唯一的Unicode glyphs和DOMRect哈希值。
