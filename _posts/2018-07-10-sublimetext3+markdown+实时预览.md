
Sublime Text3是一款给力的文本编辑器，通过安装插件可以编辑Markdown文本，在编辑Markdown文本的同时可以实时预览编辑效果。

_______________________________________________________________________________

# 安装准备：

* 安装`Package Control`：点击[Package Control][] 安装，安装完重启Sublime Text3。
* 从菜单栏进入插件安装窗口：`Preferences` → `Package Control` → `Package Control:Install Package`。

# 安装过程：

* 安装两款插件：`Markdown Editing` + `MarkdownLivePreview`。
* 在`Package Control:Install Package`中输入两款插件的名字，点击即可自动完成安装，安装完重启SubLime Text3。
* 简单设置：`Preferences` → `Package Settings` → `MarkdownLivePreview` → `Setting`，打开后将左边default的设置代码复制到右边User栏，找到`"markdown_live_preview_on_open": false`,把false改为true,保存。

# 使用方法：

* 使用Sublime新建一个文件，右下角选择编辑方式为“Markdown”，将其保存为.md文件，选择保存位置并单击确定，此时自动弹出Markdown文本编辑框（左）和预览框（右），然后就开始愉快地编辑吧。

# _注意_
* 若保存.md文件时无法保存到当前文件夹，可安装`AdvancedNewFile`插件，方法与前面两款插件相同，并且进行设置，同样将default的设置代码复制到User，找到`"default_root": "project_folder"`,把`project_folder`改为`current`，保存。

[Package Control]: https://packagecontrol.io/ "下载链接"
