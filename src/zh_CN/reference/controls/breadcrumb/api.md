# API 参考

## Breadcrumb

`Breadcrumb` 继承自 `ItemsControl`，是面包屑导航的容器控件。

### 属性

| 属性名 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `Separator` | `object?` | `"/"` | 全局分隔符内容。设定后，所有子项的分隔符都将使用该值。支持字符串或控件对象。 |
| `SeparatorTemplate` | `IDataTemplate?` | `null` | 分隔符的数据模板。当 `Separator` 为非控件对象时，可通过此模板自定义分隔符的渲染方式。 |
| `IsMotionEnabled` | `bool` | `true` | 是否启用过渡动画效果。 |

### 事件

| 事件名 | 类型 | 说明 |
|--------|------|------|
| `NavigateRequest` | `EventHandler<BreadcrumbNavigateEventArgs>` | 当用户点击面包屑路径节点时触发。事件参数中包含被点击的 `BreadcrumbItem` 实例，可通过其 `NavigateContext` 属性获取导航上下文数据。 |

## BreadcrumbItem

`BreadcrumbItem` 是面包屑导航中的单个路径节点控件。

### 属性

| 属性名 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `Icon` | `PathIcon?` | `null` | 路径节点的图标，使用 `{atom:IconProvider Kind=...}` 标记扩展设定。 |
| `Separator` | `object?` | `null` | 单项分隔符。设定后仅覆盖当前节点的分隔符，不影响其他节点。 |
| `NavigateContext` | `object?` | `null` | 导航上下文数据。用于在路径节点上携带自定义参数，点击时通过 `NavigateRequest` 事件传递给开发者。 |

## BreadcrumbItemData

`BreadcrumbItemData` 用于在 MVVM 模式下通过 `ItemsSource` 绑定动态生成面包屑导航条。

### 属性

| 属性名 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `Content` | `string` | `""` | 路径节点的显示文本。 |
| `Separator` | `object?` | `null` | 单项分隔符。 |
| `NavigateContext` | `object?` | `null` | 导航上下文数据。 |

## BreadcrumbNavigateEventArgs

导航事件的参数类型。

### 属性

| 属性名 | 类型 | 说明 |
|--------|------|------|
| `BreadcrumbItem` | `BreadcrumbItem` | 被点击的面包屑路径节点实例。可通过该实例访问 `NavigateContext` 等属性。 |
