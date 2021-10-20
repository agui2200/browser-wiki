# 浏览器指纹：WebGL

WebGL是一种JavaScript浏览器API，用于在网页上呈现3D图像。网站可利用WebGL来识别您的设备指纹。通常，网站可以用两种方法来做到这一点：

WebGL报告——完整的WebGL浏览器报告表是可获取、可被检测的。在一些情况下，它会被转换成为哈希值以便更快地进行分析。 WebGL图像 ——渲染和转换为哈希值的隐藏3D图像。由于最终结果取决于进行计算的硬件设备，因此此方法会为设备及其驱动程序的不同组合生成唯一值。这种方式为不同的设备组合和驱动程序生成了唯一值。 您可以通过Browserleaks test检测网站来查看网站可以通过该API获取哪些信息。

## [#](liu-lan-qi-zhi-wen-webgl.md#webgl图像噪声功能) WebGL图像噪声功能 <a href="webgl-tu-xiang-zao-sheng-gong-neng" id="webgl-tu-xiang-zao-sheng-gong-neng"></a>

当您在WebGL设置中选择噪声模式时，x8浏览器会拦截网站所请求的WebGL读出，并向其加上一个特殊噪声。噪声值在浏览器配置文件中保持一致性，这意味着该文件的所有WebGL图像读出都会以相同的方式被更改。举个例子，不同页面上同样的WebGL图像会以相同的方式被更改；不同浏览器会话中相同的图像也会以相同的方式被更改。

这使得一个浏览器配置文件中唯一的指纹具有持续性。

由于WebGL图像读出被添加了随机的噪声，如果网站应用了数据分析技术，便会发现指纹是100%唯一的。

## [#](liu-lan-qi-zhi-wen-webgl.md#webgl元数据掩蔽) WebGL元数据掩蔽 <a href="webgl-yuan-shu-ju-yan-bi" id="webgl-yuan-shu-ju-yan-bi"></a>

当您将WebGL设为噪音模式时，WebGL元数据就会被x8浏览器所掩蔽。这是一种旧有机制，以后我们将通过分别隐藏WebGL元数据和图像来改进这一功能。

启用元数据掩蔽后，x8浏览器将根据从指纹数据库中获取的值来更改WebGL供应商和渲染器参数。
