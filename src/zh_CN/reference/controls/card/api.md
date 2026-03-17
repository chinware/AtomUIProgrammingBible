# Card API

### 类定义

```csharp
public class Card : HeaderedContentControl
```

### 样式变体枚举

```csharp
public enum CardStyleVariant
{
    Outline,
    Borderless
}
```

### 属性

| 属性名 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| BoxShadow | `BoxShadows` | - | 卡片阴影效果 |
| Extra | `object?` | `null` | 卡片右上角额外操作区域内容 |
| ExtraTemplate | `IDataTemplate?` | `null` | Extra 内容的数据模板 |
| StyleVariant | `CardStyleVariant` | `Outline` | 样式变体，`Outline` 为有边框样式，`Borderless` 为无边框样式 |
| SizeType | `SizeType` | - | 卡片尺寸，支持 `Large`、`Middle`、`Small` |
| IsLoading | `bool` | `false` | 是否显示加载状态，为 `true` 时在内容上方显示加载遮罩 |
| IsInnerMode | `bool` | `false` | 是否为内嵌卡片模式，用于在主卡片内部嵌套子卡片 |
| IsHoverable | `bool` | `false` | 是否启用鼠标悬停效果 |
| Cover | `object?` | `null` | 卡片封面内容，通常为图片 |
| CoverTemplate | `IDataTemplate?` | `null` | Cover 内容的数据模板 |
| IsMotionEnabled | `bool` | - | 是否启用动画效果 |

### 集合

| 名称 | 类型 | 说明 |
| --- | --- | --- |
| Actions | `Controls` | 卡片底部操作按钮集合（只读），通过 `Card.Actions` 设置 |

### 继承属性

`Card` 继承自 `HeaderedContentControl`，因此还支持以下常用属性：

| 属性名 | 类型 | 说明 |
| --- | --- | --- |
| Header | `object?` | 卡片标题内容 |
| Content | `object?` | 卡片主体内容 |

### 相关子组件

| 组件 | 说明 |
| --- | --- |
| `CardTabsContent` | Tab 标签页容器，放置于 Card 的 Content 中实现标签页切换 |
| `CardMetaContent` | 元数据内容组件，支持 Header、Content、Avatar 等属性，用于展示结构化信息 |
| `CardGridContent` | 网格布局容器，配合 `CardGridItem` 实现网格卡片 |
| `CardGridItem` | 网格卡片子项，支持 Row、Column 定位及 `IsHoverable` 属性 |
