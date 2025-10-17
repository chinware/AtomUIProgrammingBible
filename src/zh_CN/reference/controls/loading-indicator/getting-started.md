# LoadingIndicator 快速入门

### 基础配置条件

* Nuget安装Avalonia
* Nuget安装AtomUI

### 基础用法

![AtomUI LoadingIndicator组件](./images/basic.webp)

axaml文件：
```axaml
<atom:LoadingIndicator />
```

### 大小尺寸

通过 `SizeType` 来设定组件的大小，提供了三种尺寸：`Small`、`Middle`、`Large`。

![AtomUI LoadingIndicator组件](./images/size.webp)

```axaml
<StackPanel Orientation="Horizontal">
    <atom:LoadingIndicator SizeType="Small" VerticalAlignment="Center" />
    <atom:LoadingIndicator SizeType="Middle" VerticalAlignment="Center" />
    <atom:LoadingIndicator SizeType="Large" VerticalAlignment="Center" />
</StackPanel>
```
