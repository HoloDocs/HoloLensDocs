# Using Visual Studio

<p>不论你是否使用DirectX或Unity来开发全息应用，你都会使用Visual Studio 2015来进行调试和部署应用。在本部分，你将会学习以下内容：</p>
<ul>
<li>如何通过Visual Studio将你的应用部署到HoloLens上</li>
<li>Visual Studio 2015如何使用内置的HoloLens模拟器</li>
<li>如何去调试全息应用</li>
</ul>
<p>&nbsp;</p>
<h2>先决条件&nbsp;<span class="doc-headline">Prerequisites</span></h2>
<hr>
<h2>&nbsp;</h2>
<ol>
<li><a href="http://www.cnblogs.com/mantgh/p/5352703.html" target="_blank"><span class="doc-headline">安装好开发工具</span></a></li>
<li>对于2D应用，在Visual Studio 2015 Update 1及更高版本中创建一个UWP项目。或者开始使用Unity来开发全息应用。HoloLens支持C#、C++和JavaScript项目。</li>
</ol>
<p>&nbsp;</p>
<h2>开启开发者模式&nbsp;<span class="doc-headline">Enabling Developer Mode</span></h2>
<hr>
<h2>&nbsp;</h2>
<p><span class="doc-headline">在开始连接开发者工具到HoloLens之前，你首先需要在设备上开启开发者模式。</span></p>
<ol>
<li><span class="doc-headline">打开设备电源，并穿戴上HoloLens</span></li>
<li><span class="doc-headline">使用绽开（bloom）手势启动开始菜单</span></li>
<li><span class="doc-headline">凝视设置菜单，然后使用点击手势。通过第二次点击放置<strong>设置应用</strong>到你的环境中。设置应用会在你放置好之后启动</span></li>
<li><span class="doc-headline">选中<strong>更新</strong>菜单</span></li>
<li><span class="doc-headline">选中<strong>开发者选项</strong>菜单</span></li>
<li><span class="doc-headline">开启<strong>开发者模式</strong>。这允许你从Visual Studio中部署应用到HoloLens</span></li>
<li><span class="doc-headline">可选操作：滚动界面，然后打开<strong>设备控制台（device portal）</strong>选项。这将允许你从浏览器连接到HoloLens上的Windows设备控制台（Windows Device Portal）。</span></li>
</ol>
<p>&nbsp;</p>
<h2><span class="doc-headline">通过Wi-Fi部署应用 Deploying an app over Wi-Fi</span></h2>
<hr>
<h2>&nbsp;</h2>
<p><span class="doc-headline">将你的应用的编译配置设为<strong>x86</strong></span></p>
<p>&nbsp;</p>
<p><span class="doc-headline"><strong><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/X86Setting.png" alt="x86 build configuration in Visual Studio"></strong></span></p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>部署目标选择<strong>远程机器（Remote Machine）</strong></p>
<p>&nbsp;</p>
<p><img src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/RemoteMachineSetting.png" alt="Remote machine deployment target in Visual Studio"></p>
<p>&nbsp;</p>
<p><span class="doc-headline">对于C++和JavaScript项目，前往&nbsp;<strong>Project &gt; Properties &gt; Configuration Properties &gt; Debugging</strong>。对于C#项目，一个配置连接的弹窗会自动出现。</span></p>
<ol>
<li><span class="doc-headline">输入设备<strong>IP地址或者设备名称</strong>。在HoloLens上，你可以在<strong>Settings &gt; Network &amp; Internet &gt; Advanced Options</strong>中找到的你的IP地址，或者直接询问Cortana：“我的IP地址是什么？”（What is my IP address?）</span></li>
<li><span class="doc-headline">将验证模式设为<strong>Universal (Unencrypted protocol)</strong></span></li>
</ol>
<p>&nbsp;</p>
<p><span class="doc-headline"><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/RemoteDeploy.png" alt="Remote connection dialog in Visual Studio"></span></p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>选中<strong>&nbsp;Debug &gt; Start debuggin</strong>以开始部署和调试</p>
<p>&nbsp;</p>
<p><span class="doc-headline"><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/DeployNoDebugging.png" alt="Start Without Debugging in Visual Studio"></span></p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>第一次部署应用到HoloLens上，会需要验证PIN码，需要遵循以下<strong>配对设备</strong>指引。</p>
<p>&nbsp;</p>
<h2>配对你的设备 Pairing your device</h2>
<hr>
<h2>&nbsp;</h2>
<p>你第一次从Visual Studio部署应用到HoloLens，你将需要验证PIN码。在HoloLens上，通过启动设置应用来生成一个PIN码，具体操作是前往<strong>Update &gt; For Developers</strong>，然后点击<strong>配对</strong>。一个PIN将会显示在HoloLens上，然后在Visual Studio中输入此PIN码。配对结束后，点击<strong>完成（Done）</strong>按钮来隐藏此提示框。此时PC已与HoloLens配对，你将可以自动部署应用到HoloLens上。为每一台用于开发的不同PC重复此步骤。</p>
<p>为了解除HoloLens和PC直接的配对，可以启动设置应用，前往<strong>Update &gt; For Developers</strong>，然后点击<strong>清除（Clear）</strong>。</p>
<p>&nbsp;</p>
<h2>部署应用到HoloLens模拟器 Deploying an app to the HoloLens Emulator</h2>
<hr>
<h2>&nbsp;</h2>
<ol>
<li>确保你安装了HoloLens模拟器</li>
<li>将你的应用的编译配置设为<strong>x86</strong></li>
</ol>
<p><strong><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/X86Setting.png" alt="x86 build configuration in Visual Studio"></strong></p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p style="margin-left: 30px;">3.部署目标选中为<strong>HoloLens模拟器</strong></p>
<p style="margin-left: 30px;">&nbsp;</p>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/DeployEmulator.png" alt="Emulator target in Visual Studio"></p>
<p>&nbsp;</p>
<p style="margin-left: 30px;">4.选中<strong>&nbsp;Debug &gt; Start debuggin</strong>以开始部署和调试</p>
<p style="margin-left: 30px;">&nbsp;</p>
<p style="margin-left: 30px;"><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/DeployNoDebugging.png" alt="Start Without Debugging in Visual Studio"></p>
<h2>&nbsp;</h2>
<h2><strong><span class="doc-headline">图形调试 Graphic Debugger</span></strong></h2>
<hr>
<h2>&nbsp;</h2>
<p><span class="doc-headline">当你开发和优化全息应用时，Visual Studio图形调试分析工具是非常有用的。到MSDN<a href="https://msdn.microsoft.com/en-us/library/hh315751.aspx" target="_blank">上查看更多细节。</a></span></p>
<p>&nbsp;</p>
<p><strong><span class="doc-headline">为了对HoloLens开始使用图形调试器</span></strong></p>
<ol>
<li><span class="doc-headline">按照以上指引将部署目标设为HoloLens设备或模拟器</span></li>
<li><span class="doc-headline">前往<strong>Debug &gt; Graphics &gt; Start Diagnostics</strong></span></li>
<li><span class="doc-headline">当你第一次这么做的时候，会得到一个“拒绝访问（access denied）”的错误。重启HoloLens以允许权限更新，然后再做同样的尝试。</span></li>
</ol>
<p>&nbsp;</p>
<h2><span class="doc-headline">性能分析 Profiling</span></h2>
<hr>
<h2>&nbsp;</h2>
<p><span class="doc-headline">Visual Studio性能分析工具允许你分析应用的性能和资源利用率。它包含了分析CPU、内存、图形性能、网络利用率的工具。在<a href="https://msdn.microsoft.com/en-us/library/dn957936.aspx" target="_blank">MSDN上可以看到更多细节</a>。</span></p>
<p><strong><span class="doc-headline">对HoloLens开始使用性能分析器</span></strong></p>
<ol>
<li><span class="doc-headline">按照以上指引将部署目标设为HoloLens设备或模拟器</span></li>
<li><span class="doc-headline">前往<strong>Debug &gt; Start Diagnostic Tools Without Debugging...</strong></span></li>
<li><span class="doc-headline">选中你想使用的工具</span></li>
<li><span class="doc-headline"><span class="doc-headline">点击<strong>开始</strong></span></span></li>
<li><span class="doc-headline">当你第一次这么做的时候，会得到一个“拒绝访问（access denied）”的错误。重启HoloLens以允许权限更新，然后在做同样的尝试。</span></li>
</ol>
<p>&nbsp;</p>
