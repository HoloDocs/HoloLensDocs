# Install the tools 配置开发环境

<p>随着Build 2016开发者大会的结束，HoloLens开发包也正式开放下载。Hololens没有独立的SDK，开发特性被集成到最新的Visual Studio Update 2中。如果你没有HoloLens真机，那么可以安装HoloLens模拟器。</p>
<p>&nbsp;</p>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="http://unity3d.com/profiles/unity3d/themes/unity/images/pages/windows/hololens/get-started1.jpg" alt=""></p>
<p>&nbsp;</p>
<p><strong><span style="font-size: 18pt;">安装清单</span></strong></p>
<p>&nbsp;</p>
<p><span style="font-size: 13px;"><span style="color: #ff0000;">注意:&nbsp;</span>这里为了方便大家顺利下载安装，HoloLens模拟器等安装包下载地址被我替换成百度云链接。官方下载地址请访问：<a href="https://developer.microsoft.com/zh-cn/windows/holographic/install_the_tools" target="_blank">https://developer.microsoft.com/zh-cn/windows/holographic/install_the_tools</a>。</span></p>
<p>&nbsp;</p>
<ul>
<li><a href="https://developer.microsoft.com/zh-cn/windows/downloads" target="_blank">Visual Studio 2015 Update 2</a>，安装时确保最新的Windows SDK and Tools选项被勾选。</li>
<li><a href="http://pan.baidu.com/s/1qXPpLXq" target="_blank">HoloLens模拟器</a>，用于模拟器中运行HoloLens应用，提供了VS项目模板。</li>
<li>Unity HoloLens Technical Preview Beta 10，对于开发HoloLens应用，Unity是推荐选项。</li>
</ul>
<ol>
<li>首先安装<a href="http://pan.baidu.com/s/1boIoIcv" target="_blank">Unity引擎</a></li>
<li>然后安装<a href="http://pan.baidu.com/s/1jItokSY" target="_blank">UWP Runtime</a></li>
<li>最后可以根据需要安装<a href="http://pan.baidu.com/s/1c2iBfxu" target="_blank">离线文档</a>工具</li>
</ol>
<p>&nbsp;</p>
<p><strong><span style="font-size: 18pt;">安装要求</span></strong></p>
<p>&nbsp;</p>
<p>Windows 10 SDK最好运行在Windows 10系统上. Windows 10 SDK也支持Windows 8.1, Windows 8, Windows 7, Windows Server 2012, Windows Server 2008 R2. 注意并不是所有的工具都能被老系统支持. Visual Studio 2015也有<a href="https://www.visualstudio.com/zh-cn/downloads/visual-studio-2015-system-requirements-vs.aspx" target="_blank">硬件要求</a>。</p>
<p>&nbsp;</p>
<p>HoloLens模拟器基于Hyper-V和RemoteFx硬件图形加速。为了使用模拟器，请确保你的模拟器满足一下要求：</p>
<ul>
<li>64位Windows 10 Pro, Enterprise, or Education系统(家庭版不支持Hyper-V)</li>
<li>64位CPU</li>
<li>8G或更多内存</li>
<li>在BOIS中，以下特性必须被支持和启用：<span style="line-height: 1.5;"><span style="line-height: 1.5;">&nbsp;</span></span>
<ul>
<li><span style="line-height: 1.5;">硬件虚拟化（Hardware-assisted virtualization）</span></li>
<li>二级地址翻译（Second Level Address Translation (SLAT)）</li>
<li>基于硬件的数据执行预防（Hardware-based Data Execution Prevention (DEP)）</li>
</ul>
</li>
<li>GPU (模拟器可能可以使用不支持的GPU运行, 但是将会很慢)
<ul>
<li style="list-style-type: none;">
<ul>
<li>DirectX 11.0或更新</li>
<li>WDDM 1.2 driver 或更新</li>
</ul>
</li>
</ul>
</li>
</ul>
<p>&nbsp;</p>
<p><strong><span style="font-size: 18pt;">问题诊断</span></strong></p>
<p>&nbsp;</p>
<p>当你安装模拟器时，可能会看到如下错误：&nbsp;<em>"Visual Studio 2015 Update 1 and UWP tools version 1.2"</em>.</p>
<p>错误原因可能有2个：</p>
<ul>
<li>你没有安装VS 2015 Update 1或Update 2，可以根据提示安装最新的Update 2.</li>
<li>&nbsp;你安装了VS 2015 Update 1或更新的Update，但是没有启用或安装UWP开发工具。你需要在安装VS 时启用此特性。</li>
</ul>
<p>&nbsp;</p>
<p><strong><span style="font-size: 18pt;">模拟器运行效果</span></strong></p>
<p>&nbsp;</p>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/Emulator.PNG" alt="HoloLens emulator main window"></p>
<p>&nbsp;</p>
