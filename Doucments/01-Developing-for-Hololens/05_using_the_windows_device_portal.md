# Using the Windows device portal 使用Windows设备控制台

<p>Windows设备控制台允许你通过Wi-Fi或USB来远程控制你的HoloLens设备。设备控制台是HoloLens上的一个Web Server，你可以通过PC的浏览器来连接到它。设备控制台包含了很多帮助你管理、调试和优化HoloLens设备的工具。</p>
<p>&nbsp;</p>
<h2>设置HoloLens以使用Windows设备控制台 Setting up HoloLens to use Windows Device Portal</h2>
<hr>
<h2>&nbsp;</h2>
<ol>
<li>打开HoloLens，并穿戴上</li>
<li>使用绽开手势打开开始菜单</li>
<li>选中设置应用，在你放置它以后会自动启动</li>
<li>选中更新选项</li>
<li>选中开发者选项</li>
<li>打开开发者模式</li>
<li>滑动页面，打开设备控制台选项</li>
</ol>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/DevicePortalSettings.png" alt="" width="638" height="433"></p>
<p>&nbsp;</p>
<h2>通过Wi-Fi连接 Connecting over Wi-Fi</h2>
<hr>
<h2>&nbsp;</h2>
<ol>
<li>将HoloLens连上Wi-Fi</li>
<li>找到你的IP地址</li>
<li>在PC浏览器上前往https://&lt;你设备的IP&gt;
<ul>
<li>浏览器会显示以下信息，“浏览器的证书存在问题”。这是因为Windows设备控制台的证书是测试证书，你现在可以忽略这个证书错误。</li>
</ul>
</li>
</ol>
<p>&nbsp;</p>
<h2>通过USB连接 Connecting over USB</h2>
<hr>
<h2>&nbsp;</h2>
<p>&nbsp;</p>
<ol>
<li>安装好开发工具，确保PC上已有Visual Studio 2015 Update 1及更新版本和Windows 10开发者工具。这保证了USB连接性。</li>
<li>将HoloLens设备通过USB连接到PC</li>
<li>在PC浏览器上前往http://127.0.0.1:10080</li>
</ol>
<p>&nbsp;</p>
<h2>连接到模拟器 Connecting to an emulator</h2>
<hr>
<h2>&nbsp;</h2>
<p>你也可以在模拟器上使用设备控制台。可以使用toolbar连接到设备控制台。点击下面这个图标：</p>
<ul>
<li><img src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/emulator_deviceportal.png" alt="" width="31" height="30">&nbsp;Open Device Portal： 打开HoloLens模拟器的设备控制台</li>
</ul>
<p>&nbsp;</p>
<h2>创建用户名和密码 Creating a Username and Password</h2>
<hr>
<h2>&nbsp;</h2>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/windows-device-portal-credentials-reset-page.png" alt="" width="1176" height="438"></p>
<p>&nbsp;</p>
<p>你首次连接到HoloLens上的设备控制台时，需要创建一个用户名和密码。</p>
<ol>
<li>在PC浏览器上访问HoloLens的IP地址，会打开一个设置页面</li>
<li>点击<strong>Request pin</strong>，然后在HoloLens上查看生成的pin码</li>
<li>输入设备上出现的pin码</li>
<li>输入一个用户名用于连接HoloLens，不必是微软账户或者域账号</li>
<li>重复输入密码，密码至少要有7个字符。不必是微软账号或者域账号密码。</li>
<li>点击 Pair按钮来连接到HoloLens</li>
</ol>
<p>&nbsp;</p>
<p>任何时候如果你想修改用户名和密码，你可以点击页面顶部Security链接访问设备安全页面，或者直接访问：https://&lt;YOUR_HOLOLENS_IP_ADDRESS&gt;/devicesecurity.htm。</p>
<p>&nbsp;</p>
<h2>安全证书 Security certificate</h2>
<hr>
<h2>&nbsp;</h2>
<p>如果你在浏览器里看到证书错误提示，可以通过信任HoloLens设备证书来修复此问题。</p>
<p>每台HoloLens设备都会生成一个自签名的证书用于SSL连接。默认情况下，此证书不会被你的浏览器信任，并显示证书错误。通过下载此证书，并在PC上信任它，你就可以安全的连接到设备了。</p>
<ol>
<li>确保处在安全的网络下</li>
<li>从设备控制台安全（Security）页面下载设备证书</li>
<li>安装证书到PC上的“受信任的信任根证书发行机构（Trusted Root Certification Authority）”目录</li>
<li>重启浏览器</li>
</ol>
<p>&nbsp;</p>
<h2>设备控制台页面 Device Portal Pages</h2>
<hr>
<h2>&nbsp;</h2>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/windows-device-portal-home-page.png" alt="" width="1280" height="902"></p>
<p>&nbsp;</p>
<p>设备管理会话起始于首页。从左边导航栏点击Home即可进入首页。</p>
<p>顶部工具栏提供了设备状态和一些特性内容。</p>
<ul>
<li>Online：指示设备是否连接到了Wi-Fi</li>
<li>Shutdown：关闭设备</li>
<li>Restart：重启</li>
<li>Security：打开安全页面</li>
<li>Cool：指示设备温度</li>
<li>A/C：指示设备是否在充电</li>
<li>Help：打开REST接口文档页</li>
</ul>
<p>首页显示了以下信息：</p>
<ul>
<li>设备状态：监视设备健康及报告致命错误</li>
<li>Windows信息：显示HoloLens名字和当前系统版本</li>
<li>偏好设置 Preference区块包括以下内容：
<ul>
<li>&nbsp;IPD：设定瞳距，这是指用户直视前方瞳孔中心之间的距离，单位是毫米。此值被设置后自动生效，设备默认值是自动计算的。</li>
<li>&nbsp;设备名：分配一个名字给设备，改名后必须重启后才能生效。</li>
<li>休眠设置：设置设备进入休眠前等待的时长。</li>
</ul>
</li>
</ul>
<p>&nbsp;</p>
<h2>3D视图 3D View</h2>
<hr>
<h2><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/windows-device-portal-3d-view-page.png" alt="" width="1280" height="596"></h2>
<p>&nbsp;</p>
<p>使用3D视图页面来了解HoloLens如何解析周围环境。使用鼠标可以调整视图内容：</p>
<ul>
<li>旋转：按住鼠标左键移动</li>
<li>平移：按住鼠标邮件移动</li>
<li>缩放：滚动鼠标滚轮</li>
<li>追踪选项：通过勾选Force visual tracking打开持续可视化追逐。勾选Pause会暂停追踪。</li>
<li>视图选项：
<ul>
<li>Tracking：指示可视化追踪是否激活</li>
<li>Show floor：显示一个方格平面图</li>
<li>Show frustum：显示一个视锥</li>
<li>Show stabilization plane：显示HoloLens用于稳定运动的平面</li>
<li>Show mesh：显示周围环境的表面映射网格</li>
<li>Show details：显示实时变化时，手的位置，头部转动参数，以及设备初始矢量</li>
<li>Full screen按钮：全屏模式显示3D视图，按Esc键可退出</li>
</ul>
</li>
<li>Surface reconstruction：点击Update按钮会显示最新的空间映射网格，有时候这个过程可能会花费一点时间。3D视图中的空间网格不会自动更新，你必须手动点击更新按钮来从设备中载入最新的网格数据。点击保存按钮可以将当前空间映射网格保存为obj文件存储到PC上。</li>
</ul>
<p>&nbsp;</p>
<h2>混合现实捕获 Mixed Reality Capture</h2>
<hr>
<h2>&nbsp;</h2>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/windows-device-portal-mixed-reality-capture-page.png" alt="" width="1280" height="424">&nbsp;</p>
<p>使用<a href="https://developer.microsoft.com/zh-cn/windows/holographic/using_mixed_reality_capture" target="_blank">混合现实捕获</a>可以保存来自HoloLens设备的媒体流。</p>
<ul>
<li>&nbsp;Settings：通过选中以下选项来控制媒体流
<ul>
<li>Holograms：捕获全息内容到视频流。全息图像已单声道渲染，而不是立体声</li>
<li>PV camera：从摄像头捕获视频流</li>
<li>Mic Audio：捕获麦克风阵列的声音</li>
<li>App Audio：捕获当前应用的声音</li>
<li>Live preview quality：为实时预览视频选择分辨率、帧率和流速</li>
</ul>
</li>
<li>点击Live preview按钮来预览当前捕捉流内容。Stop live preview按钮用于停止预览捕捉流</li>
<li>点击Record按钮来开始使用指定设置来记录混合现实流。Stop recording用于结束纪录，并保存它</li>
<li>点击Take photo按钮从捕获流里获取一张照片</li>
<li>Videos and photos：显示捕获的视频和照片列表</li>
</ul>
<p>注意：当你从设备控制台纪录或实时预览捕获流时，HoloLens应用将不能捕获MRC视频或者照片</p>
<p>&nbsp;</p>
<h2>性能追踪 Performance Tracking</h2>
<hr>
<h2>&nbsp;</h2>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/windows-device-portal-performance-tracing-page.png" alt="" width="1280" height="402">&nbsp;</p>
<p>用于从HoloLens捕获Windows性能记录器（WPR）追踪内容</p>
<ul>
<li>Available profiles：选择WPR配置后点击Start开始性能追踪</li>
<li>Custom profile：点击Browse从PC选择一个WPR配置文件。点击Upload and start开始性能捕捉</li>
</ul>
<p>为了停止性能追踪，点击stop。停留在此页面直到性能追踪文件下载完成。</p>
<p>捕获到的ETL文件可以被<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/hh448170.aspx" target="_blank">Windows性能分析器</a>打开并分析。</p>
<p>&nbsp;</p>
<h2>进程 Processes</h2>
<hr>
<h2>&nbsp;</h2>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/windows-device-portal-running-processes-page.png" alt="" width="1280" height="615"></p>
<p>显示当前运行进程的细节。包括了所有系统和应用进程。</p>
<p>&nbsp;</p>
<h2>系统性能 System Performance</h2>
<hr>
<h2>&nbsp;</h2>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/windows-device-portal-system-performance-page.png" alt="" width="1215" height="855"></p>
<p>&nbsp;</p>
<p>显示系统实时诊断图形信息，例如使用电量、帧速和CPU负载。</p>
<p>以下是可获得的内容指标：</p>
<ul>
<li>SoC电源：平均每分钟瞬时系统芯片电量利用率</li>
<li>System power：平均每分钟瞬时系统电量利用率</li>
<li>Frame rate：每秒帧数，每秒丢失的空白帧数以及持续丢失的帧数</li>
<li>GPU：GPU引擎利用率</li>
<li>I／O：读写速度</li>
<li>Network：接收到和发出的流量大小</li>
<li>Memory：总内存、使用中、修改的、分页的以及不分页的内存情况</li>
</ul>
<p>&nbsp;</p>
<h2>应用 Apps</h2>
<hr>
<h2>&nbsp;</h2>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/windows-device-portal-apps-page.png" alt="" width="1280" height="673"></p>
<p>&nbsp;</p>
<p>管理安装在HoloLens上的应用。</p>
<ul>
<li>Installed apps：移除和开始应用</li>
<li>Running apps：列出当前正在运行的应用</li>
<li>Install app：从电脑上选择应用包来安装</li>
<li>Dependency：添加安装包依赖项</li>
<li>Deploy：部署应用和其依赖项到HoloLens</li>
</ul>
<p>&nbsp;</p>
<h2>应用崩溃纪录页面 App Crash Dumps Page</h2>
<hr>
<h2>&nbsp;</h2>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/windows-device-portal-dev-apps-crash-dumps-page.png" alt="" width="1280" height="414">&nbsp;</p>
<p>这个页面允许你收集旁加载应用的崩溃日志。为每一个你想收集崩溃日志的应用选中 Crash Dump Enable，然后返回此页面收集崩溃日志。dump文件可以使用Visual Studio打开来<a href="https://msdn.microsoft.com/en-us/library/d5zhxt22.aspx" target="_blank">调试</a>。</p>
<p>&nbsp;</p>
<h2>Kiosk模式 Kiosk Mode</h2>
<hr>
<h2><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/windows-device-portal-kiosk-mode-page.png" alt="" width="1280" height="428"></h2>
<p>&nbsp;</p>
<p>开启Kiosk模式后，会限制用户启动新应用或者改变正在运行应用的能力。Bloom手势和Cortana也将不能使用，环境中放置的其他应用也不会被显示。</p>
<p>选中Enable Kiosk Mode来使HoloLens进入kiosk模式。从Startup app里选择一个应用。点击Save来保存设定。</p>
<p>注意：即使Kiosk模式没有开启，应用也会在HoloLens启动时运行。选择 None则没有应用会开机启动。</p>
<p>&nbsp;</p>
<h2>日志 Logging</h2>
<hr>
<h2><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/windows-device-portal-logging-page.png" alt="" width="1280" height="574"></h2>
<p>管理HoloLens上的Windows实时事件追踪（ETW）。</p>
<p>选中Hide providers以仅显示事件列表</p>
<ul>
<li>Registered providers：选择ETW提供者和追踪级别。追踪级别会是以下其中之一：<ol>
<li>Abnormal exit or termination 异常退出和终止</li>
<li>Servere errors 严重错误</li>
<li>Warnings 警告</li>
<li>Non-error Warnings 无错误警告</li>
</ol></li>
</ul>
<p>点击Enable按钮开始追踪。被追踪者将会被添加到Enable Providers下拉框。</p>
<ul>
<li>Custom Providers：选择一个自定义ETW来源喝追踪级别。通过GUID来标志提供者。GUID不要包含括号</li>
<li>Enable Providers：启动的ETW提供者来源</li>
<li>Providers history：显示当前会话中被选中的ETW提供者</li>
<li>Events：从选中的提供者以列表形式列出ETW事件</li>
<li>Filters：允许你筛选通过ID、关键词、级别、提供者名字、任务名字或文本收集的ETW事件</li>
</ul>
<p>&nbsp;</p>
<h2>仿真 Simulation</h2>
<hr>
<h2>&nbsp;</h2>
<p><img src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/windows-device-portal-simulation-page.png" alt="" width="1278" height="565"></p>
<p>&nbsp;</p>
<p>允许你纪录喝回放用于测试的输入数据。</p>
<ul>
<li>Capture room：用于下载一个包含用户周边环境空间映射网格数据的仿真房间文件，点击Save可以保存到本地计算机。房间文件可以导入到HoloLens模拟器使用。</li>
<li>Recording：选中用于纪录的流，命名纪录后，开始进行纪录。在你的HoloLens上操作，然后点击Stop按钮将数据保存为.xef文件到PC上。此文件可以被HoloLens模拟器使用。</li>
<li>Playback：点击 Upload recording按钮从PC上选择一个xef文件，然后发送数据到HoloLens上。</li>
<li>Control mode：从下拉框选择 Default或者Simulation，点击Set按钮在HoloLens上启用此模式。选中“Simulation”，将会禁用HoloLens上真实的传感器，而使用上传的模拟数据。如果启用Simulation模式，HoloLens将不会响应真实用户直到切换回Default模式。</li>
</ul>
<p>&nbsp;</p>
<h2>网络 Networking</h2>
<hr>
<h2>&nbsp;</h2>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/windows-device-portal-networking-page.png" alt="" width="1280" height="908"></p>
<p>&nbsp;</p>
<p>管理HoloLens上的Wi-Fi连接。</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<h2>虚拟输入 Virtual Input</h2>
<hr>
<h2><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/windows-device-portal-virtual-input-page.png" alt="" width="1278" height="420"></h2>
<p>从远程机器发送键盘输入到HoloLens上。</p>
<p>点击Virtual Keyboard下方区域来放松键盘点击数据到HoloLens。在Input text中输入内容，然后点击Send按钮来发送内容到当前应用。</p>
<p>&nbsp;</p>
<h2>设备控制台Rest API's Device Portal REST API's</h2>
<hr>
<h2>&nbsp;</h2>
<p>设备控制台里的所有内容都是基于<a href="https://developer.microsoft.com/zh-cn/windows/holographic/device_portal_api_reference" target="_blank">REST API</a>制作的，你可以利用它们通过编程来自定义访问数据和控制你的设备。</p>
<p>&nbsp;</p>

