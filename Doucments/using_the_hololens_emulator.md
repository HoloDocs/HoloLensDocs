# Using the HoloLens emulator 使用HoloLens模拟器


<p><a href="http://go.microsoft.com/fwlink/?LinkID=724053" target="_blank">首先下载HoloLens模拟器</a></p>
<p>&nbsp;</p>
<p>HoloLens模拟器运行在没有真机的情况下在你的PC上测试应用，属于<a href="https://developer.microsoft.com/en-us/windows/holographic/install_the_tools" target="_blank">HoloLens开发工具系列</a>。模拟器使用了Hyper-V虚拟机。通常通过传感器获取的人体和环境输入通过键盘、鼠标或者Xbox手柄来模拟。应用不用修改即可运行在HoloLens模拟器上，它们也不知道它们没有在真实设备上运行。</p>
<p>&nbsp;</p>
<h2>部署应用到HoloLens模拟器上 Deploying apps to the HoloLens emulator</h2>
<hr>
<h2>&nbsp;</h2>
<ol>
<li>在Visual Studio 2015里载入应用解决方案
<ul>
<li>注意：使用Unity是，通常在Unity里生成项目，然后再在VS中载入编译好的项目。</li>
</ul>
</li>
<li>确保目标平台是<strong>x86</strong></li>
<li>选择<strong>HoloLens模拟器</strong>作为目标设备</li>
<li>前往Debug &gt; Start Debugging或按 F5键启动模拟器部署应用及调试</li>
</ol>
<p>&nbsp;</p>
<p>第一次启动模拟器时，可能会花费较长时间启动。我们建议在调试期间一直保持模拟打开，这可以快速部署和调试应用。</p>
<p>&nbsp;</p>
<h2>基础模拟器输入 Basic emulator input</h2>
<hr>
<h2>&nbsp;</h2>
<p>控制模拟器和玩3D游戏体验类似。可使用的输入选项包括键盘、鼠标或Xbox手柄。通过控制模拟器，你可以模拟用户穿戴HoloLens时的各种行为。在模拟器上模拟的行为将会被像真实设备那样回应。</p>
<ol>
<li><strong>前后左右走动</strong> - 使用W、A、S、D按键或者xbox手柄上的左操纵杆</li>
<li><strong>上下左右看</strong> - 使用鼠标点击拖拽、键盘上的箭头按键或者xbox手柄上的右操纵杆</li>
<li><strong>点击手势</strong> - 使用鼠标右键、点击键盘enter键或xbox手柄上A按钮</li>
<li><strong>绽开手势（Bloom）</strong> - 点击键盘上Windows键或F2键、或者xbox手柄上B按钮</li>
<li><strong>用手拖拽</strong> - 按住Alt键，按住鼠标右键，然后上下移动鼠标、或者在xbox手柄上按住RT和A按钮，然后使用右操纵杆上下移动。</li>
</ol>
<p>&nbsp;</p>
<h2>详解HoloLens模拟器 Anatomy of the HoloLens emulator</h2>
<hr>
<h2>&nbsp;</h2>
<p>&nbsp;</p>
<h3><strong>主窗口 Main window</strong></h3>
<p>&nbsp;</p>
<p>模拟器启动后，你会看到HoloLens系统显示的主窗口。</p>
<p>&nbsp;</p>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/Emulator.PNG" alt="HoloLens emulator main window"></p>
<p>&nbsp;</p>
<h3>工具栏 Toolbar</h3>
<p>&nbsp;</p>
<p>模拟器右边，你会看到模拟器工具栏。工具栏包含以下按键：</p>
<p>&nbsp;</p>
<ul>
<li><img src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/emulator_close.png" alt="Close icon">&nbsp;<strong>Close：</strong>关闭模拟器</li>
<li><img src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/emulator_minimize.png" alt="Minimize icon">&nbsp;<strong>Minimize：</strong>最小化模拟器窗口</li>
<li><img src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/emulator_control.png" alt="Human input icon">&nbsp;<strong>Human Input：</strong>鼠标键盘被用于模拟人工输入</li>
<li><img src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/emulator_input.png" alt="Keyboard and mouse input icon">&nbsp;<strong>Keyboard and Mouse Input：</strong>键盘鼠标直接被用于对HoloLens系统的输入，就像你连接蓝牙键鼠那样。</li>
<li><img src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/emulator_fit.png" alt="Fit to screen icon">&nbsp;<strong>Fit to Screen:</strong>自动调整模拟器尺寸以适应屏幕</li>
<li><img src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/emulator_zoom.png" alt="Zoom icon"><strong>&nbsp;Zoom：</strong> 缩放模拟器</li>
<li><img src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/emulator_help.png" alt="Help icon">&nbsp;<strong>Help：</strong> 打开模拟器帮助</li>
<li><img src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/emulator_deviceportal.png" alt="Open device portal icon">&nbsp;<strong>Open Device Portal：</strong>打开HoloLens模拟器设备控制台</li>
<li><img src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/emulator_tools.png" alt="Tools icon">&nbsp;<strong>Tools：</strong> 打开额外的工具面板</li>
</ul>
<p>&nbsp;</p>
<h3>模拟标签栏 Simulation tab</h3>
<p>&nbsp;</p>
<p>额外工具面板中默认是模拟标签栏。</p>
<p>&nbsp;</p>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/emulator_simulation.png" alt="HoloLens emulator &amp;#39;Additional Tools&amp;#39; pane"></p>
<p>&nbsp;</p>
<p>模拟标签页显示了模拟器内模拟出的传感器的状态参数。光标悬浮在任何一个值上面，都会出现一个如何控制该数值的工具提示。</p>
<p>&nbsp;</p>
<h3>房间标签页 Room Tab</h3>
<p>&nbsp;</p>
<p>模拟器通过模拟“房间”来模拟周边世界的空间匹配数据。这个标签页可以让你选择载入哪个房间模型来替代默认房间。</p>
<p>&nbsp;</p>
<p><img src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/emulator_room.png" alt="HoloLens emulator &amp;#39;Rooms&amp;#39; tab"></p>
<p>&nbsp;</p>
<p>模拟的房间对于在不同环境中测试应用很有用。一旦你安装好模拟器后，几个房间模型就会被传递进来，你可以在路径&nbsp;%ProgramFiles(x86)%\Program Files (x86)\Microsoft XDE\10.0.11082.0\Plugins\Rooms下发现它们。所有的房间都是用HoloLens在真实世界中捕获得到：</p>
<ul>
<li><strong>DefaultRoom.xef</strong> - 一个有电视、咖啡桌、2个沙发的小客厅。启动模拟器时会被默认载入。</li>
<li><strong>Bedroom1.xef</strong> - 有一个桌子的小卧室</li>
<li><strong>Bedroom2.xef</strong> - 有一张大床、梳妆台、床头柜和衣橱的卧室</li>
<li><strong>GreatRoom.xef</strong> - 带有客厅、晚餐桌和厨房的一个开放空间的大房间</li>
<li><strong>LivingRoom.xef</strong> - 一个有壁炉、沙发、扶手椅和放着花瓶的茶几的客厅</li>
</ul>
<p>&nbsp;</p>
<p>你可以使用你的HoloLens设备控制台上模拟页面来记录自己的房间，用来在HoloLens模拟器中使用。</p>
<p>在模拟器上，你将只能看到你渲染出来的全息图像而没法看到全息图像后模拟的房间。</p>
<p>这与真实设备不同，真实设备上所有内容都会被展现。如果你想在HoloLens模拟器上看到模拟的房间，你需要更新的应用以在场景中渲染空间匹配网格。</p>
<p>&nbsp;</p>
