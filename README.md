# KeyCastOW编译



# 下载源码

源项目（英文）下载地址： https://github.com/brookhong/KeyCastOW 

汉化版下载地址： https://github.com/obiscr/KeyCastOW 



# 编译

下载完成之后，用 **Virsual Studio** 打开此项目。

点击 “**工具**” - “**外部工具**” （如果是英文，就是 “**TOOLS**” - “**External Tools**”），点击右上角添加，增加如下配置：

![](https://note.youdao.com/yws/public/resource/fe413d5ad6fc367e137a6cd1f9b13067/xmlnote/WEBRESOURCEea378412333de1837f9f10ca6e0b2cca/4209)



+ 标题：Virsual Studio 2019 Command Prompt（可自定义）

+ 命令：C:\Windows\System32\cmd.exe

+ 参数：/k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Professional\Common7\Tools\VsDevCmd.bat"

  > 参数的这个路径根据自己 Virsual Studio 的安装路径来，不同的版本也有一些细微的差异

+ 初始目录：C:\

配置完成之后，应用即可。



然后打开项目中的 **keycastow.vsxproj** ，全局搜索 `v120` ，根据 **附录（一）**图表中的对应关系，把 `v120` 替换成（一共两处需要替换）与自己VS版本对应的平台工具集的版本，替换完成之后保存。

再次点击工具，会看到 刚才添加的菜单：Virsual Studio 2019 Command Prompt，点击打开，会出现一个cmd窗口，在cmd进入项目的主目录，执行 `msbuild /p:platform=win32 /p:Configuration=Release` ，之后会在Release目录生成 **keycastow.exe**。



# 附录

### 一、 Visual Studio版本与平台工具集版本号的对应关系：

| Virsual Studio 版本 | 平台工具集版本 |
| ------------------- | -------------- |
| Visual Studio 2019  | V142           |
| Visual Studio 2015  | V140           |
| Visual Studio 2013  | V120           |
| Visual Studio 2012  | V110           |
| Visual Studio 2010  | V100           |
| Visual Studio 2008  | V90            |
| Visual Studio 2005  | V80            |
| Visual Studio 2003  | V71            |
| Visual Studio 2002  | V70            |
| Visual Studio 6     | V60            |



### 二、Visual Studio版本与Format Version(解决方案文件版本)的对应关系

| Virsual Studio 版本 | Format Version(解决方案文件版本) |
| ------------------- | -------------------------------- |
| Visual Studio 2015  | Format Version 12.00             |
| Visual Studio 2013  | Format Version 12.00             |
| Visual Studio 2012  | Format Version 12.00             |
| Visual Studio 2010  | Format Version 11.00             |
| Visual Studio 2008  | Format Version 10.00             |
| Visual Studio 2005  | Format Version 9.00              |



### 三、Visual Studio版本与ToolsVersion(.Net Framework版本)的对应关系

| Virsual Studio 版本 | ToolsVersion(.Net Framework版本) |
| ------------------- | -------------------------------- |
| Visual Studio 2015  | ToolsVersion 12.00               |
| Visual Studio 2013  | ToolsVersion 12.00               |
| Visual Studio 2012  | ToolsVersion 4.0                 |
| Visual Studio 2010  | ToolsVersion 4.0                 |
| Visual Studio 2008  | ToolsVersion 3.5                 |