# Rate API 参考

## Rate

评分组件，继承自 `TemplatedControl`，用于对事物进行快速的评级操作。

### 属性

| 属性名 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `IsAllowClear` | `bool` | `true` | 是否允许再次点击后清除评分 |
| `IsAllowHalf` | `bool` | `false` | 是否允许半星选择 |
| `Character` | `object?` | `StarFilled` | 自定义评分字符，可以是图标、字母或汉字等 |
| `StarColor` | `IBrush?` | - | 自定义星星选中时的颜色 |
| `StarBgColor` | `IBrush?` | - | 自定义星星未选中时的背景颜色 |
| `Count` | `int` | `5` | 星星总数 |
| `Value` | `double` | `NaN` | 当前评分值 |
| `DefaultValue` | `double` | `0` | 默认评分值，组件初始化时使用 |
| `IsKeyboardEnabled` | `bool` | `true` | 是否支持键盘操作（方向键调整评分） |
| `ToolTips` | `IList<string>?` | - | 每颗星对应的提示文字列表 |
| `SizeType` | `SizeType` | - | 组件尺寸大小 |
| `IsMotionEnabled` | `bool` | - | 是否启用动画效果 |

### 事件

| 事件名 | 事件参数类型 | 说明 |
|--------|-------------|------|
| `ValueChanged` | `RateValueChangedEventArgs` | 评分值发生变化时触发 |
| `HoverValueChanged` | `RateValueChangedEventArgs` | 鼠标悬停的评分值发生变化时触发 |

### SizeType 枚举

| 值 | 说明 |
|----|------|
| `Small` | 小尺寸 |
| `Middle` | 中等尺寸（默认） |
| `Large` | 大尺寸 |
