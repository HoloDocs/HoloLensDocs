# App Model 应用程序模型

<p>HoloLens使用<a href="https://dev.windows.com/en-us/getstarted">Universal Windows Platform</a>&nbsp;(UWP)提供的应用模型。UWP应用模型定义了应用如何被安全和完全地安装、更新、版本控制和移除。它管理了应用生命周期 - 应用如何被执行、休眠和中断 - 以及如何保留应用状态。它也覆盖了和操作系统、文件以及其他应用的集成和交互。</p>
<p>&nbsp;</p>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/20160112_055908_HoloLens.jpg" alt="2D apps arranged in holographic shell in a breakfast area" /></p>
<p>&nbsp;</p>
<h2>应用生命周期 App lifecycle</h2>
<hr />
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>全息应用的生命周期涉及到了标准应用的概念，例如放置。启动、中断和移除。</p>
<p>&nbsp;</p>
<h3>放置就是启动 Placement is launch</h3>
<p>&nbsp;</p>
<p>每一个应用都通过放置应用磁贴在HoloLens shell中启动。这些应用磁铁，在放置的时候，就将开始运行应用。这些应用磁贴会持久化的停留在它们被放置的位置，任何时候你都可以从它们返回应用。</p>
<p>&nbsp;</p>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/Slide1.PNG" alt="Placement puts a secondary tile in the world" /></p>
<p>&nbsp;</p>
<p>一旦完成放置（除非放置是由应用间启动唤起的），应用开始启动。HoloLens应用同一时刻可以运行一个应用。一旦你放置和启动了一个应用，任何其他激活的应用都会被挂起，在你放置它的地方，应用磁贴上会留下一个它最后状态的截图。阅读<a href="https://msdn.microsoft.com/en-us/library/windows/apps/mt243287.aspx" target="_blank">标准生命周期</a>的文章来了解更多关于处理恢复和其他生命周期事件的方法。</p>
<p>&nbsp;</p>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/Slide2.PNG" alt="After placing a tile, the app starts running" /></p>
<h3>&nbsp;</h3>
<h3>移除是关闭/终止处理 Remove is close/terminate process</h3>
<p>&nbsp;</p>
<p>当你从世界中移除一个放置好的应用磁贴，这闭合了基础的流程。这对于确保你的应用被终止或者重启一个有问题的应用可能是有用的。</p>
<p>&nbsp;</p>
<h3>应用暂停/终止 App suspension/termination</h3>
<p>&nbsp;</p>
<p>使用HoloLens，用户能够为一个应用创建多个启动入口。它们通过从开始菜单启动你的应用，并将应用磁贴放置在世界中来做到这点。每一个应用磁贴都表现为不同的启动入口，在系统中都具有一个单独的磁贴实例。<a href="https://msdn.microsoft.com/en-us/library/windows/apps/br242208.aspx">SecondaryTile.FindAllAsync()</a>&nbsp;查询的队列将可以列出所有应用的二级磁贴。</p>
<p>当一个UWP应用暂停时，应用当前状态的屏幕截图被获取。</p>
<p>&nbsp;</p>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/Slide9.PNG" alt="Screenshots are shown for suspended apps" /></p>
<p>&nbsp;</p>
<p>与其他Windows 10平台的关键区别是通过CoreApplication.Resuming和CoreApplication.Activated事件，应用如何被通知它的一个实例被激活。</p>
<p>&nbsp;</p>
<table style="height: 231px; width: 719px;" border="1" align="center">
<thead>
<tr align="center" valign="middle">
<td style="text-align: center;" valign="middle">情况 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</td>
<td>恢复</td>
<td>激活</td>
</tr>
</thead>
<tbody>
<tr>
<td>从开始菜单启动一个应用新实例</td>
<td>&nbsp;</td>
<td>使用一个新的TileId激活应用</td>
</tr>
<tr>
<td>从开始菜单启动第二个应用实例</td>
<td>&nbsp;</td>
<td>使用一个新的TileId激活应用</td>
</tr>
<tr>
<td>选中当前未激活的应用实例</td>
<td>&nbsp;</td>
<td>使用实例关联的TileId激活应用</td>
</tr>
<tr>
<td>选中一个不同的应用，然后选中先前激活的实例</td>
<td>恢复被触发</td>
<td>&nbsp;</td>
</tr>
<tr>
<td>选中一个不同的应用，然后选中先前未激活的实例</td>
<td>恢复被触发</td>
<td>然后使用实例关联的TileId激活应用</td>
</tr>
</tbody>
</table>
<p>&nbsp;</p>
<h3>&nbsp;扩展的执行 Extended execution</h3>
<p>&nbsp;</p>
<p>有时你的应用需要继续在后台做一些工作或者播放声音。<a href="https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh977049.aspx">Background tasks</a>&nbsp;在Windows Holographic里是可以使用的，但是有一些<a href="https://developer.microsoft.com/en-us/windows/holographic/current_limitations_for_apps_using_apis_from_the_shell" target="_blank">限制</a>。</p>
<p>&nbsp;</p>
<p>&nbsp;<img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/Slide10.PNG" alt="Apps can run in the background" /></p>
<p>&nbsp;</p>
<h2>应用视图 App views</h2>
<hr />
<h2>&nbsp;</h2>
<p>当你的应用激活时，你可以选择显示哪种类型的视图。对一个应用CoreApplication来说，总存在一个初始的应用视图（<a href="https://msdn.microsoft.com/en-us/library/windows/apps/windows.ui.viewmanagement.applicationview.aspx" target="_blank">app view</a>）和任意数量的其他你想创建的次级视图。对于桌面环境，你可以认为一个应用视图就是一个窗口。我们的全息应用项目模板将会创建一个初始视图是全息视图的Unity项目。你的应用可以使用像Xaml这样的技术来创建额外的2D视图来使用应用内购买之类的shell控件。如果你的应用以通用应用形式启动，那么初始视图会是2D的，但是你可以通过添加一个额外的全息视图来提升在HoloLens的体验。想象一下，我们用XAML构建了一个图片查看器，里面有个视图切换按钮，可以一键切换到全息视图，在全息视图中，来自应用的照片飞到世界和物体表面上。</p>
<p>&nbsp;</p>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/Slide3.PNG" alt="The running app can have a 2D view or a holographic view" /></p>
<p>&nbsp;</p>
<h3>创建一个全息视图 Create a Holographic view</h3>
<p>&nbsp;</p>
<p>全息视图是指那些通过HolographicSpace 类型创建了全息视图的应用。</p>
<p>&nbsp;</p>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/Slide4.PNG" alt="Apps running in holographic view are the only one visible" /></p>
<p>&nbsp;</p>
<h3>混合世界中的2D视图 2D view in the Mixed World</h3>
<p>&nbsp;</p>
<p>任何非全息视图的在你的世界中都会被渲染成2D视图.</p>
<p>&nbsp;</p>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/Slide5.PNG" alt="Apps running in 2D view share the space in the mixed world with other apps" /></p>
<h3>&nbsp;</h3>
<h3>次级视图磁贴的放置 Placement of further App Tiles</h3>
<p>&nbsp;</p>
<p>使用二级磁贴(Secondary Tile) API你可以放置任意数量你想要的2D视图。这些被放置的磁贴将会以闪屏的形式出现，用以来之后启动你的应用。Windows Holographic当前不支持渲染任何2D磁贴作为动态磁贴。在二级磁贴API（S<a href="https://msdn.microsoft.com/en-us/library/windows/apps/xaml/Hh868249(v=win.10)">econdary tile APIs</a>）页面你可以了解到更多信息。</p>
<p>&nbsp;</p>
<p><img src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/Slide6.PNG" alt="Apps can have multiple placements using secondary tiles" /></p>
<p>&nbsp;</p>
<h3>切换视图 Switching views</h3>
<p>&nbsp;</p>
<h4>从2D视图切换到全息视图 Switching from &nbsp;the 2D XAML view to the holographic view</h4>
<p>&nbsp;</p>
<p>如果用户使用了XAML，然后XAML IFrameworkViewSource将会控制应用的首个视图。应用需要在激活CoreWindow之前切换到全息视图，以保证应用直接进入全息体验。</p>
<p>使用<a href="https://msdn.microsoft.com/en-us/library/windows/apps/windows.applicationmodel.core.coreapplication.createnewview.aspx">CoreApplication::CreateNewView</a>&nbsp;和&nbsp;<a href="https://msdn.microsoft.com/en-us/library/windows/apps/windows.ui.viewmanagement.applicationviewswitcher.switchasync.aspx">ApplicationViewSwitcher::SwitchAsync</a>&nbsp;来实现视图的切换。</p>
<p>注意：</p>
<ul>
<li>当从XAML视图切换到全息视图或将被从世界中移除的应用面板时，不要为SwitchAsync方法指定Consolidate标记</li>
<li>SwitchAsync方法应该被你想要切换去的视图关联的Dispatcher所调用</li>
<li>如果你需要启动一个虚拟键盘或想要激活其他应用，你需要使用SwitchAsync方法回到XAML视图</li>
</ul>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/Slide7.PNG" alt="Apps can switch between 2D views and holographic views" /></p>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/Slide8.PNG" alt="When an app goes into a holographic view, the mixed world and other apps disappear" /></p>
<p>&nbsp;</p>
<h4>从全息视图切换回键盘XAML视图&nbsp;Switching from the holographic view back to a keyboard XAML view</h4>
<p>&nbsp;</p>
<p>在视图间反复切换通常是为了在全息应用显示一个键盘。如果你的应用显示了一个2D视图，shell只能够显示系统键盘。如果你的应用需要获取文本输入源，然后他们会写一个带有文本输入框的自定义XAML视图，它能在切换到它后，输入完成后再切换回去。</p>
<p>上述所说情形，可以使用<a href="https://msdn.microsoft.com/en-us/library/windows/apps/windows.ui.viewmanagement.applicationviewswitcher.switchasync.aspx">ApplicationViewSwitcher::SwitchAsync</a>&nbsp;从你的全息视图切换回XAML视图。</p>
<p>&nbsp;</p>
<h2>应用大小 App size</h2>
<hr />
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>2D应用视图总是出现在一个固定的可视面板中。这使得所有2D视图显示同等数量的内容。下面是关于2D应用视图大小的进一步细节：</p>
<ul>
<li>调整大小时，应用的宽高比始终一样</li>
<li>调整大小时，应用的分辨率和拉伸率都不会改变</li>
<li>应用不能查询他们在世界中实际的大小</li>
</ul>
<p>&nbsp;</p>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/12493521_10104043956964683_6118765685995662420_o.jpg" alt="2D apps appear with fixed window sizes" /></p>
<p>&nbsp;</p>
<h2>应用磁贴 App tiles</h2>
<hr />
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>开始菜单使用了标准小号和中号磁贴用于pin视图和所有应用视图。</p>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="https://az835927.vo.msecnd.net/sites/holographic/resources/images/start.png" alt="The start menu for Windows Holographic" /></p>
<p>&nbsp;</p>
<h2>应用间交互 App to app interactions</h2>
<hr />
<p>&nbsp;</p>
<p>当你构建应用时，Windows 10上你可以获得丰富的应用间通信机制。即使HoloLens目前不支持最新的应用协议启动（<a href="https://developer.microsoft.com/en-us/windows/holographic/current_limitations_for_apps_using_apis_from_the_shell">app service protocol launches</a>），但是许多新的协议API和文件注册机制在HoloLens上能够确保应用间启动和通信。</p>
<h3>协议 Protocols</h3>
<p>HoloLens通过<a href="https://msdn.microsoft.com/en-us/library/windows/apps/xaml/windows.system.launcher.aspx">Windows.System.Launcher APIs</a>&nbsp;支持应用间启动。</p>
<p>当启动其他应用时，以下内容要被考虑：</p>
<ul>
<li>当非模态启动时，例如<a href="https://msdn.microsoft.com/en-us/library/windows/apps/xaml/windows.system.launcher.launchuriasync.aspx">LaunchUriAsync</a>，用户在与应用交互前必须放置好它</li>
<li>当模态启动时，例如<a href="https://msdn.microsoft.com/en-us/library/windows/apps/xaml/windows.system.launcher.launchuriforresultsasync.aspx">LaunchUriForResultsAsync</a>，模态应用会被放置在窗口顶部</li>
<li>HoloLens不能在独占视图（这里应该是指全息视图？）顶部覆盖上其他应用。为了显示启动的应用，HoloLens会使用会回到世界中以显示此应用。</li>
</ul>
<p>&nbsp;</p>
<h3>文件选取器 File pickers</h3>
<p>HoloLens支持<a href="https://msdn.microsoft.com/en-us/library/windows/apps/windows.storage.pickers.fileopenpicker.aspx">FileOpenPicker</a>&nbsp;和&nbsp;<a href="https://msdn.microsoft.com/en-us/library/windows/apps/windows.storage.pickers.filesavepicker.aspx">FileSavePicker</a>&nbsp;合约。尽管没有支持文件选取合约的应用被预装，但是你可以从Windows Store下载它们 - 例如OneDrive。</p>
<p>如果你安装了多个文件选取应用，你将不会看到任何有歧义的UI，这些UI通常是用来选取启动哪个应用。取而代之的是，首个安装的文件选取器将会被选中。保存文件时，会自动生成包括时间戳的文件名。用户不能改变文件爱你们。</p>
<p>默认情况下，以下是本地支持的文件拓展格式：</p>
<p>&nbsp;<img style="display: block; margin-left: auto; margin-right: auto;" src="http://images2015.cnblogs.com/blog/599309/201604/599309-20160426124840080-1362682837.png" alt="" /></p>
<p>&nbsp;</p>
<h3>应用合约和Windows Holographic扩展 App contracts and &nbsp;Windows Hologrphic extensions</h3>
<p>应用合约和拓展入口允许你注册你的应用来使用更底层的操作系统特性，例如处理文件拓展或者使用后台任务。下面是Windows Holographic支持的合约和拓展入口列表。这与<a href="https://developer.microsoft.com/en-us/windows/holographic/current_limitations_for_apps_using_apis_from_the_shell" target="_blank">它支持的API集合</a>不同。</p>
<p>&nbsp;</p>
<table style="height: 758px; width: 747px;" border="1">
<thead>
<tr style="background-color: #b0c4de;" align="center" valign="middle"><th>
<p>Contract or Extension</p>
<p>合约或拓展</p>
</th><th>
<p style="text-align: center;">Supported?</p>
<p>是否支持</p>
</th></tr>
</thead>
<tbody>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#account_picture_provider">Account Picture Provider (extension)</a></td>
<td>Unsupported</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#alarm">Alarm</a></td>
<td>Unsupported</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#app_service">App service</a></td>
<td>
<p>Supported but not fully functional in the current version of Windows Holographic</p>
<p>支持，但是当前版本不是所有功能都可用</p>
</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#appointmnets_provider">Appointments provider</a></td>
<td>Unsupported</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#autoplay">AutoPlay (extension)</a></td>
<td>Unsupported</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#background_tasts">Background tasks (extension)</a></td>
<td>
<p>Partially Supported (not all triggers work on Windows Holographic)</p>
<p>部分支持，目前版本不是所有触发器都可用</p>
</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#update_task">Update task (extension)</a></td>
<td>Supported</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#cached_file_updater">Cached file updater contract</a></td>
<td>Supported</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#camera_settings">Camera settings (extension)</a></td>
<td>Unsupported</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#dial_protocol">Dial protocol</a></td>
<td>Unsupported</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#file_activation">File activation (extension)</a></td>
<td>Supported</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#file_open_picker_contract">File Open Picker contract</a></td>
<td>Supported</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#file_save_picker_contract">File Save Picker contract</a></td>
<td>Supported</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#lock_screen_call">Lock screen call</a></td>
<td>Unsupported</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#media_playback">Media playback</a></td>
<td>Unsupported</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#playto_contract">Play To contract</a></td>
<td>Unsupported</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#preinstalled_config_task">Preinstalled config task</a></td>
<td>Unsupported</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#print_3d_workflow">Print 3D Workflow</a></td>
<td>Supported</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#print_task_settings">Print task settings (extension)</a></td>
<td>Unsupported</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#protocol_activation">URI activation (extension)</a></td>
<td>Supported</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#restricted_launch">Restricted launch</a></td>
<td>Unsupported</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#search_contract">Search contract</a></td>
<td>Unsupported</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#settings_contract">Settings contract</a></td>
<td>Unsupported</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#share_contract">Share contract</a></td>
<td>Unsupported</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#ssl_certificates">SSL/certificates (extension)</a></td>
<td>Supported</td>
</tr>
<tr>
<td><a href="https://msdn.microsoft.com/en-us/library/windows/desktop/hh464906.aspx#web_account_provider">Web account provider</a></td>
<td>Supported</td>
</tr>
</tbody>
</table>
<p>&nbsp;</p>
<h2>应用文件存储 App File Storage</h2>
<hr />
<h2>&nbsp;</h2>
<p>所有的存储都是通过Windows.Storage命名空间实现。阅读下面的内容来了解更多细节。HoloLens不支持应用存储同步/漫游。</p>
<ul>
<li>文件、文件夹和库&nbsp;<a href="https://msdn.microsoft.com/en-us/library/windows/apps/mt185399.aspx%7C">Files, folders, and libraries</a></li>
<li>商店和检索设置以及其他应用数据&nbsp;<a href="https://msdn.microsoft.com/en-us/library/windows/apps/mt299098.aspx%7C">Store and retrieve settings and other app data</a></li>
</ul>
<p>&nbsp;</p>
<h3>已知目录 Known folders</h3>
<p>&nbsp;</p>
<p>查看<a href="https://msdn.microsoft.com/en-us/library/windows/apps/windows.storage.knownfolders.aspx">KnownFolders</a>&nbsp;来了解更多UWP应用使用<a href="https://msdn.microsoft.com/en-us/library/windows/apps/windows.storage.knownfolders.aspx">KnownFolders</a>的细节。</p>
<p>&nbsp;</p>
<table style="height: 469px; width: 734px;" border="1">
<thead>
<tr style="background-color: #b0c4de;" align="center" valign="middle"><th>
<p>Property</p>
<p>属性</p>
</th><th>
<p style="text-align: center;">Supported on HoloLens Development Edition</p>
<p>HoloLens开发板是否支持</p>
</th><th>
<p>Description</p>
<p>描述</p>
</th></tr>
</thead>
<tbody>
<tr>
<td><strong><a href="https://msdn.microsoft.com/en-us/library/windows/apps/windows.storage.knownfolders.appcaptures.aspx">AppCaptures</a></strong></td>
<td><strong>Yes</strong></td>
<td>
<p>Gets the App Captures folder.</p>
<p>获取应用捕获文件夹</p>
</td>
</tr>
<tr>
<td><strong><a href="https://msdn.microsoft.com/en-us/library/windows/apps/windows.storage.knownfolders.cameraroll.aspx">CameraRoll</a></strong></td>
<td><strong>Yes</strong></td>
<td>
<p>Gets the Camera Roll folder.</p>
<p>相机文件夹</p>
</td>
</tr>
<tr>
<td><strong><a href="https://msdn.microsoft.com/en-us/library/windows/apps/windows.storage.knownfolders.documentslibrary.aspx">DocumentsLibrary</a></strong></td>
<td><strong>Yes</strong></td>
<td>
<p>Gets the Documents library. The Documents library is not intended for general use.</p>
<p>文档库</p>
</td>
</tr>
<tr>
<td><strong><a href="https://msdn.microsoft.com/en-us/library/windows/apps/windows.storage.knownfolders.musiclibrary.aspx">MusicLibrary</a></strong></td>
<td><strong>Yes</strong></td>
<td>
<p>Gets the Music library.</p>
<p>音乐库</p>
</td>
</tr>
<tr>
<td><strong><a href="https://msdn.microsoft.com/en-us/library/windows/apps/windows.storage.knownfolders.objects3d.aspx">Objects3D</a></strong></td>
<td><strong>Yes</strong></td>
<td>
<p>Gets the Objects 3D folder.</p>
<p>3D对象文件夹</p>
</td>
</tr>
<tr>
<td><strong><a href="https://msdn.microsoft.com/en-us/library/windows/apps/windows.storage.knownfolders.pictureslibrary.aspx">PicturesLibrary</a></strong></td>
<td><strong>Yes</strong></td>
<td>
<p>Gets the Pictures library.</p>
<p>图片库</p>
</td>
</tr>
<tr>
<td><strong><a href="https://msdn.microsoft.com/en-us/library/windows/apps/windows.storage.knownfolders.playlists.aspx">Playlists</a></strong></td>
<td><strong>Yes</strong></td>
<td>
<p>Gets the play lists folder.</p>
<p>播放列表文件夹</p>
</td>
</tr>
<tr>
<td><strong><a href="https://msdn.microsoft.com/en-us/library/windows/apps/windows.storage.knownfolders.savedpictures.aspx">SavedPictures</a></strong></td>
<td><strong>Yes</strong></td>
<td>
<p>Gets the Saved Pictures folder.</p>
<p>保存的图片文件夹</p>
</td>
</tr>
<tr>
<td><strong><a href="https://msdn.microsoft.com/en-us/library/windows/apps/windows.storage.knownfolders.videoslibrary.aspx">VideosLibrary</a></strong></td>
<td><strong>Yes</strong></td>
<td>
<p>Gets the Videos library.</p>
<p>视频库</p>
</td>
</tr>
<tr>
<td><strong><a href="https://msdn.microsoft.com/en-us/library/windows/apps/windows.storage.knownfolders.homegroup.aspx">HomeGroup</a></strong></td>
<td>No</td>
<td>
<p>Gets the HomeGroup folder.</p>
<p>家庭组文件夹</p>
</td>
</tr>
<tr>
<td><strong><a href="https://msdn.microsoft.com/en-us/library/windows/apps/windows.storage.knownfolders.mediaserverdevices.aspx">MediaServerDevices</a></strong></td>
<td>No</td>
<td>
<p>Gets the folder of media server (Digital Living Network Alliance (DLNA)) devices.</p>
<p>媒体设备文件夹</p>
</td>
</tr>
<tr>
<td><strong><a href="https://msdn.microsoft.com/en-us/library/windows/apps/windows.storage.knownfolders.recordedcalls.aspx">RecordedCalls</a></strong></td>
<td>No</td>
<td>
<p>Gets the recorded calls folder.</p>
<p>电话录音文件夹</p>
</td>
</tr>
<tr>
<td><strong><a href="https://msdn.microsoft.com/en-us/library/windows/apps/windows.storage.knownfolders.removabledevices.aspx">RemovableDevices</a></strong></td>
<td>No</td>
<td>
<p>Gets the removable devices folder.</p>
<p>可移动设备文件夹</p>
</td>
</tr>
</tbody>
</table>
<p>&nbsp;</p>
<h2>应用打包 App package</h2>
<hr />
<h2>&nbsp;</h2>
<p>使用Windows10，你不再需要以操作系统为目标但是取而代之的是，你需要以一个或多个设备家族来作为目标（<a href="https://msdn.microsoft.com/en-us/library/windows/apps/dn894631.aspx?f=255&amp;MSPPError=-2147217396#device_families">target your app to one or more device families</a>）。一个设备家族定义了此家族中所有设备都可应用的API、系统字符集和行为集合。它也决定了你的应用从应用商店中能安装到哪系列的设备。</p>
<p>&nbsp;</p>
