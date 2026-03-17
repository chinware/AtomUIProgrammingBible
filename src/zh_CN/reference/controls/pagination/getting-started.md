# Pagination 快速入门

### 基础配置条件

* Nuget安装Avalonia
* Nuget安装AtomUI

### 基础用法

最简单的分页用法，通过 `Total` 设置数据总条数，`CurrentPage` 设置当前页码。

![AtomUI Pagination组件](./images/basic.webp)

```xaml
<atom:Pagination Total="50" CurrentPage="1" />
```

### 对齐方式

通过 `Align` 属性可以设置分页组件的对齐方式，支持 `Start`（默认，左对齐）、`Center`（居中对齐）和 `End`（右对齐）三种。

![AtomUI Pagination组件](./images/align.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:Pagination Total="50" CurrentPage="1" Align="Start" />
    <atom:Pagination Total="50" CurrentPage="1" Align="Center" />
    <atom:Pagination Total="50" CurrentPage="1" Align="End" />
</StackPanel>
```

### 页面大小选择器

设置 `IsShowSizeChanger="True"` 可以显示每页条目数的切换器，允许用户动态调整分页大小。

![AtomUI Pagination组件](./images/align.webp)

```xaml
<atom:Pagination Total="500" CurrentPage="6" IsShowSizeChanger="True" />
```

### 快速跳转

设置 `IsShowQuickJumper="True"` 后会在分页组件右侧显示一个输入框，用户可以直接输入页码进行跳转。可与页面大小选择器组合使用。

```xaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:Pagination Total="500" CurrentPage="3" IsShowSizeChanger="True" IsShowQuickJumper="True" />
    <atom:Pagination Total="500" CurrentPage="3" IsShowSizeChanger="True" IsEnabled="False"
                     IsShowQuickJumper="True" />
</StackPanel>
```

### 小尺寸

通过 `SizeType="Small"` 可以使用小尺寸的分页组件，适用于空间有限的场景。

![AtomUI Pagination组件](./images/mini-size.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:Pagination Total="50" CurrentPage="1" SizeType="Small" />
    <atom:Pagination Total="50" CurrentPage="1" SizeType="Small" IsShowSizeChanger="True"
                     IsShowQuickJumper="True" />

    <atom:Pagination Total="50" IsShowTotalInfo="True" CurrentPage="1" SizeType="Small" />
    <atom:Pagination Total="50" IsShowTotalInfo="True" CurrentPage="1" SizeType="Small"
                     IsShowSizeChanger="True" IsShowQuickJumper="True" IsEnabled="False" />
</StackPanel>
```

### 总数信息

设置 `IsShowTotalInfo="True"` 可以在分页组件中展示数据总条数信息。通过 `TotalInfoTemplate` 属性可以自定义总数信息的显示模板，支持 `${RangeStart}`、`${RangeEnd}` 和 `${Total}` 三个占位变量。

![AtomUI Pagination组件](./images/mini-size.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:Pagination Total="85" CurrentPage="1" PageSize="20" IsShowSizeChanger="True" IsShowTotalInfo="True" />
    <atom:Pagination Total="85"
                     CurrentPage="1"
                     PageSize="20"
                     IsShowSizeChanger="True"
                     IsShowTotalInfo="True"
                     TotalInfoTemplate="${RangeStart}-${RangeEnd} of ${Total} items" />
</StackPanel>
```

### 简洁模式

`SimplePagination` 提供简洁版的分页组件，仅显示当前页码和总页数，适用于空间有限或移动端场景。通过 `IsReadOnly` 属性可以控制页码输入框是否可编辑。

![AtomUI Pagination组件](./images/simple-mode.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:SimplePagination Total="50" CurrentPage="1"/>
    <atom:SimplePagination Total="50" CurrentPage="1" IsReadOnly="False"/>
    <atom:SimplePagination Total="50" CurrentPage="1" IsReadOnly="False" IsEnabled="False"/>

    <atom:SimplePagination Total="50" CurrentPage="1" SizeType="Small"/>
    <atom:SimplePagination Total="50" CurrentPage="1" SizeType="Small"/>
    <atom:SimplePagination Total="50" CurrentPage="1" IsReadOnly="False" SizeType="Small"/>
    <atom:SimplePagination Total="50" CurrentPage="1" IsReadOnly="False" IsEnabled="False" SizeType="Small"/>
</StackPanel>
```
