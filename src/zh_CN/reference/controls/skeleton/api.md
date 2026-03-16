# Skeleton API 参考

## Skeleton

`Skeleton` 继承自 `AbstractSkeleton`，用于在数据加载完成前展示占位骨架。

### 属性

| 属性名 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `IsLoading` | `bool` | `false` | 是否显示占位骨架，为 `true` 时展示骨架，为 `false` 时展示实际内容 |
| `IsShowAvatar` | `bool` | `false` | 是否在左侧显示头像占位符 |
| `IsShowParagraph` | `bool` | `true` | 是否显示段落占位符 |
| `IsShowTitle` | `bool` | `true` | 是否显示标题占位符 |
| `IsRound` | `bool` | - | 是否使用圆角样式 |
| `TitleWidth` | `Dimension` | `50%` | 标题占位符的宽度 |
| `ParagraphRows` | `int` | `2`（最小值 1） | 段落占位符的行数 |
| `ParagraphLastLineWidth` | `Dimension` | `61%` | 段落最后一行的宽度 |
| `ParagraphLineWidths` | `List<Dimension>?` | `null` | 自定义每行段落的宽度列表，设置后将覆盖 `ParagraphLastLineWidth` 的效果 |
| `AvatarShape` | `AvatarShape` | `Circle` | 头像占位符的形状 |
| `AvatarSizeType` | `CustomizableSizeType` | `Middle` | 头像占位符的预设尺寸 |
| `AvatarSize` | `double` | `NaN` | 自定义头像占位符尺寸（像素），设置后将覆盖 `AvatarSizeType` 的效果 |
| `Content` | `object?` | `null` | 骨架包裹的实际内容，当 `IsLoading` 为 `false` 时显示 |
| `ContentTemplate` | `IDataTemplate?` | `null` | 实际内容的数据模板 |

### 枚举类型

#### AvatarShape

| 值 | 说明 |
|----|------|
| `Circle` | 圆形 |
| `Square` | 方形 |

#### CustomizableSizeType

| 值 | 说明 |
|----|------|
| `Large` | 大尺寸 |
| `Middle` | 中等尺寸（默认） |
| `Small` | 小尺寸 |
