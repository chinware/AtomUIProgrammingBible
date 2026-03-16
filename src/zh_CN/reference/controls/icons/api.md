# Icons API 参考

## IconProvider 标记扩展

`IconProvider` 是一个 XAML 标记扩展，用于在 XAML 中便捷地创建图标实例。

### 用法

```xaml
Icon="{atom:IconProvider Kind=SearchOutlined}"
```

### 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `Kind` | 图标类型，对应 `AntDesignIconKind` 枚举值 | `string` | — |

## AntDesignIconKind 枚举

定义在 `namespace AtomUI.IconPkg.AntDesign` 下，包含所有可用的 AntDesign 图标标识。每个图标根据风格提供最多三个变体：

| 风格后缀 | 说明 |
|---|---|
| `Outlined` | 线框风格，适合大多数场景 |
| `Filled` | 实心填充风格，适合强调状态 |
| `TwoTone` | 双色风格，适合装饰性场景 |

### 常用图标一览

#### 方向类

| Kind 值 | 说明 |
|---|---|
| `UpOutlined` | 向上箭头 |
| `DownOutlined` | 向下箭头 |
| `LeftOutlined` | 向左箭头 |
| `RightOutlined` | 向右箭头 |
| `ArrowUpOutlined` | 上箭头 |
| `ArrowDownOutlined` | 下箭头 |
| `ArrowLeftOutlined` | 左箭头 |
| `ArrowRightOutlined` | 右箭头 |

#### 建议类

| Kind 值 | 说明 |
|---|---|
| `CheckCircleOutlined` | 成功（圆圈勾选） |
| `CloseCircleOutlined` | 错误（圆圈关闭） |
| `InfoCircleOutlined` | 信息提示 |
| `ExclamationCircleOutlined` | 警告 |
| `WarningOutlined` | 警告三角 |
| `QuestionCircleOutlined` | 疑问提示 |

#### 编辑类

| Kind 值 | 说明 |
|---|---|
| `EditOutlined` | 编辑 |
| `DeleteOutlined` | 删除 |
| `CopyOutlined` | 复制 |
| `ScissorOutlined` | 剪切 |
| `SaveOutlined` | 保存 |
| `UndoOutlined` | 撤销 |
| `RedoOutlined` | 重做 |

#### 通用类

| Kind 值 | 说明 |
|---|---|
| `SearchOutlined` | 搜索 |
| `HomeOutlined` | 首页 |
| `SettingOutlined` | 设置 |
| `UserOutlined` | 用户 |
| `PlusOutlined` | 添加 |
| `MinusOutlined` | 减少 |
| `CloseOutlined` | 关闭 |
| `CheckOutlined` | 勾选 |
| `LoadingOutlined` | 加载中 |
| `DownloadOutlined` | 下载 |
| `UploadOutlined` | 上传 |
| `EyeOutlined` | 查看 |
| `EyeInvisibleOutlined` | 隐藏 |
| `LockOutlined` | 锁定 |
| `UnlockOutlined` | 解锁 |

#### 数据类

| Kind 值 | 说明 |
|---|---|
| `FolderOutlined` | 文件夹 |
| `FileOutlined` | 文件 |
| `CloudOutlined` | 云 |
| `DatabaseOutlined` | 数据库 |
| `CalendarOutlined` | 日历 |
| `ClockCircleOutlined` | 时钟 |

## 相关组件

- [Button](../button/overview.md) — 按钮组件，支持通过 `Icon` 属性设置图标
- [Tag](../tag/overview.md) — 标签组件，支持搭配图标使用
- [Alert](../alert/overview.md) — 警告提示组件，支持显示图标
