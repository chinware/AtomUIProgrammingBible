# API 参考

### Steps

`Steps` 继承自 `SelectingItemsControl`，是步骤条的容器组件。

#### 属性

| 属性名 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| CurrentStep | `int` | `0` | 当前步骤的索引，从 0 开始 |
| InitialStep | `int` | `-1` | 初始步骤索引，设置后组件首次加载时定位到该步骤 |
| ProgressValue | `double` | `0` | 当前步骤的进度值，范围 0-100 |
| CurrentStepStatus | `StepsItemStatus` | `Process` | 当前步骤的状态 |
| Orientation | `Orientation` | `Horizontal` | 步骤条的方向，支持 `Horizontal`（水平）和 `Vertical`（垂直） |
| LabelPlacement | `Orientation` | `Horizontal` | 标签放置方向，设置为 `Vertical` 时标签显示在指示器下方 |
| SizeType | `SizeType` | - | 步骤条尺寸，设置为 `Small` 可启用迷你模式 |
| ItemIndicatorType | `StepsItemIndicatorType` | `Default` | 步骤指示器类型，`Default` 为数字/图标，`Dot` 为点状 |
| Style | `StepsStyle` | `Default` | 步骤条风格样式 |
| IsMotionEnabled | `bool` | - | 是否启用动画效果 |
| IsItemClickable | `bool` | `false` | 是否允许点击步骤进行切换 |
| IsShowItemProgress | `bool` | `false` | 是否在当前步骤指示器上显示环形进度条 |
| ContentTemplate | `IDataTemplate?` | `null` | 步骤内容的数据模板 |

### 枚举类型

#### StepsItemIndicatorType

步骤指示器的类型。

| 值 | 说明 |
| --- | --- |
| `Default` | 默认指示器，显示数字序号或自定义图标 |
| `Dot` | 点状指示器，以小圆点形式展示 |

#### StepsItemStatus

步骤的状态。

| 值 | 说明 |
| --- | --- |
| `Wait` | 等待状态，表示该步骤尚未开始 |
| `Process` | 进行中状态，表示该步骤正在执行 |
| `Finish` | 完成状态，表示该步骤已完成 |
| `Error` | 错误状态，表示该步骤执行出错 |

#### StepsStyle

步骤条的展示风格。

| 值 | 说明 |
| --- | --- |
| `Default` | 默认风格，标准步骤条样式 |
| `Navigation` | 导航风格，常用于页面顶部导航区域 |
| `Inline` | 内联风格，适合嵌入到列表项等内容中 |
