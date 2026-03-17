# Icons 快速入门

## 前置条件

- NuGet 安装 `Avalonia`
- NuGet 安装 `AtomUI`

## 基础用法

通过 `IconProvider` 标记扩展设置图标，指定 `Kind` 属性即可使用对应的 AntDesign 图标。

![AtomUI Icons 基础用法](./images/icons.webp)

```xaml
<atom:Button ButtonType="Primary"
             Shape="Circle"
             Icon="{atom:IconProvider Kind=SearchOutlined}" />
```

在支持 `Icon` 属性的组件中，直接使用 `{atom:IconProvider Kind=...}` 即可加载图标。

## 图标风格

AntDesign 图标提供三种风格，通过 `Kind` 属性值的后缀区分：

| 后缀 | 风格 | 示例 |
|---|---|---|
| `Outlined` | 线框风格（默认） | `SearchOutlined`、`HomeOutlined` |
| `Filled` | 实心风格 | `SearchFilled`、`HomeFilled` |
| `TwoTone` | 双色风格 | `SearchTwoTone`、`HomeTwoTone` |

```xaml
<!-- 线框风格 -->
<atom:Button ButtonType="Primary"
             Icon="{atom:IconProvider Kind=HomeOutlined}">
    Outlined
</atom:Button>

<!-- 实心风格 -->
<atom:Button ButtonType="Primary"
             Icon="{atom:IconProvider Kind=HomeFilled}">
    Filled
</atom:Button>

<!-- 双色风格 -->
<atom:Button ButtonType="Primary"
             Icon="{atom:IconProvider Kind=HomeTwoTone}">
    TwoTone
</atom:Button>
```

## 搭配按钮使用

图标最常见的使用场景是与 Button 组件搭配，支持图标 + 文字、纯图标等组合。

```xaml
<!-- 图标 + 文字 -->
<atom:Button ButtonType="Primary"
             Icon="{atom:IconProvider Kind=SearchOutlined}">
    搜索
</atom:Button>

<!-- 纯图标圆形按钮 -->
<atom:Button ButtonType="Primary"
             Shape="Circle"
             Icon="{atom:IconProvider Kind=PlusOutlined}" />

<!-- 纯图标胶囊形按钮 -->
<atom:Button ButtonType="Primary"
             Shape="Round"
             Icon="{atom:IconProvider Kind=DownloadOutlined}" />
```

## 搭配其他组件使用

`IconProvider` 可以用于所有支持 `Icon` 属性的组件：

```xaml
<!-- 在 Tag 组件中使用 -->
<atom:Tag Icon="{atom:IconProvider Kind=CheckCircleOutlined}">
    已完成
</atom:Tag>

<!-- 在 Alert 组件中使用 -->
<atom:Alert Type="Success"
            Message="操作成功"
            ShowIcon="True" />
```

## 查找可用图标

所有可用的 `Kind` 值定义在 `namespace AtomUI.IconPkg.AntDesign` 下的 `AntDesignIconKind` 枚举中。常用图标分类包括：

| 分类 | 示例 |
|---|---|
| 方向类 | `UpOutlined`、`DownOutlined`、`LeftOutlined`、`RightOutlined` |
| 建议类 | `CheckCircleOutlined`、`CloseCircleOutlined`、`InfoCircleOutlined`、`WarningOutlined` |
| 编辑类 | `EditOutlined`、`DeleteOutlined`、`CopyOutlined`、`ScissorOutlined` |
| 数据类 | `FolderOutlined`、`FileOutlined`、`CloudOutlined`、`DatabaseOutlined` |
| 通用类 | `SearchOutlined`、`HomeOutlined`、`SettingOutlined`、`UserOutlined` |
