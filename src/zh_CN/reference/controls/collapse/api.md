# Collapse API 参考

## Collapse

`Collapse` 继承自 `SelectingItemsControl`，用于创建可折叠/展开的面板容器。

### 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `SizeType` | 折叠面板的尺寸，可选 `Small`、`Middle`、`Large` | `SizeType` | `Middle` |
| `IsGhostStyle` | 是否使用幽灵样式（透明无边框背景） | `bool` | `false` |
| `IsBorderless` | 是否使用无边框样式 | `bool` | `false` |
| `IsAccordion` | 是否开启手风琴模式（同时仅展开一个面板） | `bool` | `false` |
| `TriggerType` | 折叠触发区域类型 | `CollapseTriggerType` | `Header` |
| `ExpandIconPosition` | 展开图标的位置 | `CollapseExpandIconPosition` | `Start` |
| `IsMotionEnabled` | 是否启用展开/收起动画 | `bool` | - |
| `ItemHeaderPadding` | 面板项表头区域的内间距 | `Thickness?` | `null` |
| `ItemContentPadding` | 面板项内容区域的内间距 | `Thickness?` | `null` |

## 枚举类型

### CollapseTriggerType

| 值 | 说明 |
|---|---|
| `Header` | 点击表头整行区域触发展开/收起 |
| `Icon` | 仅点击展开图标触发展开/收起 |

### CollapseExpandIconPosition

| 值 | 说明 |
|---|---|
| `Start` | 展开图标位于表头左侧 |
| `End` | 展开图标位于表头右侧 |
