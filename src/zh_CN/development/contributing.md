# 开发 AtomUI

如果你有兴趣一同参与 `AtomUI` 的开发与推进，需要在你的设备上搭建一套基础环境，下文将具体说明 `Windows/Linux` 平台上需要的基础配置。

## 前置准备

`AtomUI` 支持 `Visual Studio`、`Rider` 和 `Visual Studio Code`。但是如果您是进行跨平台软件的研发，推荐使用 `Rider` 和 `Visual Studio Code`。

### .NET 版本

AtomUI 目前将最低的版本提升到 `.NET 8`，目前滚动的版本支持为 `.NET 8` 和 `.NET 9`，请确认您机器上的 `.NET SDK` 版本信息。`Windows/Mac/Linux` 均可以通过下面的命令来确认 `.NET` 版本。

```bash
dotnet --version
```

### AtomUI 与 Avalonia 版本说明

目前 `AtomUI` 正在属于快速开发迭代阶段，所以每次小版本发布我们大概率会锚定 `Avalonia` 已经发布的最新的版本。目前 `Avalonia`
也没有发布长期支持版，所以这种策略是可以接受的。
> 比如 AtomUI 0.0.6-build.1 就锚定了 Avalonia 11.3.2 版本

> [!IMPORTANT]
> 因为 `AtomUI` 是基于 `Avalonia` 的深度定制，所以 `AtomUI` 跟 `Avalonia` 版本是一个强绑定，您在开发的时候需要主要，这样强绑定的好处可以用
> `Avalonia` 的内部接口和类，不足之处就是 `AtomUI` 无法同时多个版本，会导致使用 `AtomUI` 做开发的项目也会形成对 `Avalonia`
> 特定版本的绑定。
>
> 但是这个情况其实影响不大，因为 `Avalonia` 编成接口还是比较稳定，不同版本间只需要重新编译即可，一般不会涉及接口的调整。

## Windows系统

优先推荐 `Windows 11`，如果是 `Windows 10` 理论上也没有任何问题。

1、安装最新版 `PowerShell`：打开链接 https://aka.ms/powershell-release?tag=stable ，找到相应的 `msi` 安装包，下载安装即可

2、安装 `MSYS2`：打开链接 https://www.msys2.org/ ，下载安装。小提示：`MSYS2` 安装过程中可能下载基础软件的流程，Installing 读条时间会稍微长一些，请耐心等待即可。
安装完毕后，在 `Windows` 的开始菜单中可以看到很多不同版本的 `MSYS2`，我们只需要留意其中的 `MSYS2 CLANG64` 版本即可

![](./images/msys2-clang64.png)

3、安装 `Clang`：打开链接 https://packages.msys2.org/search ，首先在 Search in 的下拉菜单中选择 `Packages`，其次在搜索框中输入 `Clang`，搜索即可。结果如下图：

![Search clang](./images/search-clang.png)

注意在搜索结果中，一定要选对平台。对于我个人而言，选择图中 `x86_64` 位版本即可，点击进入详情页面，找到下图：

![Clang command](./images/clang-install-command.png)

将 Installation 中的 `pacman` 安装命令复制一下，打开第 3 步中的 `MSYS2 CLANG64` 终端，粘贴进去后回车执行安装即可。

4、安装 `xmake`：首先在 Search in 的下拉菜单中选择 `Base Packages`，其次在搜索框中输入 `xmake`，搜索即可。结果如下图：

![Search xmake](./images/search-xmake.png)

点击进去详情页后，找到 `mingw-w64-clang-x86_64-xmake` 3.0 以及 3.0 以上的版本（即与 `Clang` 对应的版本）后点击进入详情页，和第 3 步一样，将 Installation 中的
`pacman` 安装命令复制到 `MSYS2 CLANG64` 终端后，回车执行安装即可。

5、配置系统环境变量：找到 `Windows` 系统配置环境变量的管理窗口，找到 `Path` 环境变量（至于是用户级 `Path` 还是系统级 `Path`，可自行选择），双击
修改 `Path` 系统变量。在打开的新窗口中找到第2步中 `MSYS2` 的安装目录，再进一步找到 `clang64` 目录，再进一步选择 `bin` 目录，点击确定后添加到 `Path` 环境变量中。

![Path vars](./images/path-var.png)

![Add new var to path](./images/add-new-path.png)

6、fork && clone 项目：打开链接 https://github.com/chinware/AtomUI.ControlGallery ，执行 fork 操作，将 fork 后的项目 clone 到本地；打开链接 https://github.com/chinware/AtomUI ，执行 fork 操作，将 fork 后的项目 clone 到本地。
打开 `AtomUI.ControlGallery` 项目所在的目录，找到 `.gitmodules` 文件并打开，将其中的url后的值修改为 **`AtomUI` 的 fork git 地址** （就是将 `AtomUI` fork 操作后的 git 地址）。

在终端窗口中打开 `AtomUI.ControlGallery` 项目所在的目录，执行下面的命令，将 `AtomUI.ControlGallery` 的子模块 `AtomUI` 从 `github` 上拉到本地。关于 git 的 submodule 知识，自行搜索学习。

```bash
git submodule update --init --recursive
```

7、运行与开发：使用 `Rider` 或 `Visual Studio` 等 `IDE` 打开 `AtomUI.ControlGallery` 项目，可以尝试 Run 运行查看 `AtomUI.ControllGalley` 的最终效果；打开 `packages/AtomUI` 目录，可以对 `AtomUI` 项目源码进行修改，修改后可以再次 Run 运行 `AtomUI.ControlGallery`
项目查看修改。注意运行的项目要选择 `Desktop`，如下图：

![Run desktop project](./images/run-desktop-project.png)

## Linux系统

1、安装最新版 `PowerShell`：打开链接 https://aka.ms/powershell-release?tag=stable ，找到相应的 `Linux` 发行版的安装包即可。一般说来，`Debian` 系的发行版选择 `deb` 后缀；`Redhat` 系选择 `rpm` 后缀即可。除此之外，注意系统是 32 位架构还是 64 位架构。

如果是 deb 包，安装命令如下：

```bash
// sudo 前缀是假设安装需要 sudo 权限 如果不需要 sudo 权限, 直接去掉 sudo 即可
sudo dpkg -i 名字.deb
```

如果是 `rpm` 包，安装命令如下：

```bash
sudo dnf install 名字.rpm
```

2、安装 `xmake`：这里同样需要安装 3.0 以及 3.0 以上版本。无论你的 `Linux` 为哪个发行版，均可以通过如下 `xmake` 官方推荐的方式安装

```bash
curl -fsSL https://xmake.io/shget.text | bash
```

这个命令会将 `xmake` 安装至 `~/.local/bin/xmake` 这个路径中，然后我们通过如下命令将上述路径添加到环境变量中，以便于在命令行中随时使用。

```bash
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

然后可以通过如下命令确认一下是否安装成功以及版本号。

```bash
xmake --version
```

3、安装 `Clang`：在 `Debian` 系发行版中，通过如下命令快速安装

```bash
sudo apt install clang
```

4、安装基础依赖库：在 `Debian` 系发行版中，通过如下命令安装 `libxcb` 与 `xcb-shape` 库

```bash
sudo apt install libxcb1-dev
sudo apt install libxcb-shape0-dev
```

在 `Redhat` 系发行版中，通过如下命令安装

```bash
sudo yum install libxcb-devel xcb-util-devel
```

5、编译依赖库：打开 `AtomUI.ControlGallery` 项目所在目录，切换至 `packages/AtomUI/nativelibs` 目录下，执行下面命令

```bash
xmake config --toolchain=clang
```

以上命令执行后，可能会有一些额外的依赖需要安装，此时输入 y 回车确认即可，如果一切顺利的话，最终如下图

![Xmake config](./images/xmake-config.png)

config 完成后，开始执行编译

```bash
xmake build
```

成功如下图

![Xmake build](./images/xmake-build.png)

6、参考 `Windows` 系统中的第 7 步即可