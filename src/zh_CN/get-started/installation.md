---
title: 安装 AtomUI
---

> [!NOTE]
> AtomUI OSS 底层是基于 Avalonia 技术打造，同时也是使用 Avalonia 标准方式进行研发，所以开发者如果对 Avalonia 不熟悉，可以去
> Avalonia 官方学习
>
> [Avalonia 快速入门](https://docs.avaloniaui.net/docs/get-started)

## 前置准备

### 开发工具推荐

AtomUI 支持 Visual Studio、Rider 和 Visual Studio Code。但是如果您是进行跨平台软件的研发，推荐使用 Rider 和 Visual Studio
Code

### .NET 版本

AtomUI 目前将最低的版本提升到 .NET 8，目前滚动的版本支持为 .NET 8 和 .NET 9，请确认您机器上的 .NET SDK 版本信息。

您可以用以下命令进行确认

```bash
dotnet --list-sdks

8.0.117 [/usr/lib/dotnet/sdk]
9.0.107 [/usr/lib/dotnet/sdk]
```

### AtomUI 与 Avalonia 版本说明

目前 AtomUI 正在属于快速开发迭代阶段，所以每次小版本发布我们大概率会锚定 Avalonia 已经发布的最新的版本。目前 Avalonia
也没有发布长期支持版，所以这种策略是可以接受的。
> 比如 AtomUI 0.0.6-build.1 就锚定了 Avalonia 11.3.2 版本

> [!IMPORTANT]
> 因为 AtomUI 是基于 Avalonia 的深度定制，所以 AtomUI 跟 Avalonia 版本是一个强绑定，您在开发的时候需要主要，这样强绑定的好处可以用
> Avalonia 的内部接口和类，不足之处就是 AtomUI 无法同时多个版本，会导致使用 AtomUI 做开发的项目也会形成对 Avalonia
> 特定版本的绑定。
>
> 但是这个情况其实影响不大，因为 Avalonia 编成接口还是比较稳定，不同版本间只需要重新编译即可，一般不会涉及接口的调整。

## 安装方式

AtomUI 推荐的以 nuget 包的方式进行安装，我们已经将 AtomUI OSS 相关的包上传到 nuget.org，目前 AtomUI
没有发布长期支持版，所以推荐安装我们发布的最新版本

目前我们已经发布的包如下：

| 包名称                      | 描述                                                    |
|--------------------------|-------------------------------------------------------|
| AtomUI                   | 主库，包含了主题系统和 AtomUI OSS 版本所有的控件                        |
| AtomUI.Controls.DataGrid | 数据表格控件定义，如果不用可以不引入                                    |
| AtomUI.Generator         | 自定义控件需要的一些源码生成器定义，您如果在自定义控件的时候需要接入 AtomUI 主题系统，需要引入此包 |
| AtomUI.IconPkg.Generator | 如果您需要自定义 Icon 包，需要引入此包                                |

### nuget 包安装

```bash
dotnet add package AtomUI --version 0.0.6-build.4
```

