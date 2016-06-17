# Development overview

<p><span style="font-size: 18pt;"><strong>开发概述</strong></span></p>
<p>&nbsp;</p>
<p>开发HoloLens全息应用将使用UWP平台（<a href="https://dev.windows.com/en-us/getstarted" target="_blank">Universal Windows Platform</a>），所有的HoloLens应用都是Win10通用应用，所有UWP通用应用都可以在HoloLens上运行。通过Windows 10和Unity这样的中间工具，我们可以现在开始构建全息应用的体验。</p>
<p>&nbsp;</p>

<p><strong><span style="font-size: 18pt;">全息开发基础&nbsp;<span id="Basics_of_a_holographic_development" class="doc-headline">Basics of a holographic development</span></span></strong></p>
<p>&nbsp;</p>
<p>为了尽可能实现<a href="http://www.cnblogs.com/mantgh/p/5306265.html" target="_blank">全息场景</a>，Windows暴露了一系列全新的特性给开发者。对混合现实全息应用来说，涉及到6个基础构建领域。</p>
<p>&nbsp;</p>
<ul>
<li>世界坐标&nbsp;<a href="https://dev.windows.com/zh-cn/holographic/coordinate_systems">World coordinates</a></li>
<li>凝视输入&nbsp;<a href="https://dev.windows.com/zh-cn/holographic/gaze">Gaze input</a></li>
<li>手势输入&nbsp;<a href="https://dev.windows.com/zh-cn/holographic/gestures">Gesture input</a></li>
<li>声音输入&nbsp;<a href="https://dev.windows.com/zh-cn/holographic/voice_input">Voice input</a></li>
<li>空间声音&nbsp;<a href="https://dev.windows.com/zh-cn/holographic/spatial_sound">Spatial sound</a></li>
<li>空间匹配&nbsp;<a href="https://dev.windows.com/zh-cn/holographic/spatial_mapping">Spatial mapping</a></li>
</ul>
<p>&nbsp;</p>
<p>与HoloLens的交互被设计成凝视、手势和声音。这有时被联想到GGV。例如坐标、空间声音和空间匹配的这样的环境感知特性提供了用户与周围环境全息交互的能力。</p>
<p>&nbsp;</p>
<p>全息场景是由依赖<a href="https://dev.windows.com/zh-cn/holographic/rendering" target="_blank">渲染</a>的光和声音构成的。理解做为<a href="https://dev.windows.com/zh-cn/holographic/hololens_shell_overview" target="_blank">HoloLens Shell</a>示范操作中的物体放置和持续存在的体验是一个能让你融入用户体验的好方式。</p>
<p>&nbsp;</p>
<p><strong><span style="font-size: 18pt;">用于开发HoloLens的工具&nbsp;<span id="Tools_for_developing_on_HoloLens" class="doc-headline">Tools for developing on HoloLens</span></span></strong></p>
<p>&nbsp;</p>
<p><span class="doc-headline">你将用于创建应用的工具取决于应用的类型。</span></p>
<p>&nbsp;</p>
<ul>
<li><span class="doc-headline"><a href="https://dev.windows.com/zh-cn/holographic/building_2d_apps" target="_blank">2D应用</a>可以使用任何可以开发UWP应用的工具开发，例如用来开发PC、平板和Windows Phoned通用应用的工具。这种应用将被表现为2D投影，并且能够跨设备运行。</span></li>
<li>全息应用需要使用基于Windows 全息API（<a href="https://dev.windows.com/zh-cn/holographic/documentation">Windows Holographic APIs</a>）设计的工具来开发。特别说一下，如果你想开发全息应用，我们<a href="https://dev.windows.com/zh-cn/holographic/unity_development_overview" target="_blank">推荐使用Unity</a>。对于那些想要构建自己引擎的开发者来说，可以使用DirectX和其它Windows API。</li>
</ul>
<p>&nbsp;</p>
<p>考虑到你要开发应用的类型，这些工具将会提高你的开发体验：</p>
<ul>
<li><a href="https://dev.windows.com/zh-cn/holographic/using_visual_studio">Visual Studio and the Windows SDK</a></li>
<li><a href="https://dev.windows.com/zh-cn/holographic/using_the_windows_device_portal">Windows Device Portal</a></li>
<li><a href="https://dev.windows.com/zh-cn/holographic/using_the_hololens_emulator">HoloLens emulator</a></li>
</ul>
<p>&nbsp;</p>
<h2><span id="Getting_started" class="doc-headline">开始开发 Getting started</span></h2>
<p>&nbsp;</p>
<p><span class="doc-headline">在<a href="https://dev.windows.com/zh-cn/holographic/install_the_tools" target="_blank">安装了这些工具</a>后，我们推荐下面这些在<a href="https://dev.windows.com/zh-cn/holographic/academy" target="_blank">HoloLens Academy</a>中的教程。在你完成应用开发后，<a href="https://dev.windows.com/zh-cn/holographic/submitting_an_app_to_the_windows_store" target="_blank">Windows应用商店</a>就是你发布应用的地方，使得其它HoloLens用户也能使用。</span></p>
<p>&nbsp;</p>
<p><span class="doc-headline"><img style="display: block; margin-left: auto; margin-right: auto;" title="HoloLens" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/buy_panel_image.jpg" alt="HoloLens" width="720" height="384"></span></p>
<p>&nbsp;</p>
