# API 参考

## ProgressBar

`ProgressBar` 继承自 `AbstractLineProgress`，是基础的线性进度条组件。

### 属性

| 属性 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `Value` | `double` | `0` | 当前进度值 |
| `Minimum` | `double` | `0` | 最小值 |
| `Maximum` | `double` | `100` | 最大值 |
| `Status` | `ProgressStatus` | `Normal` | 进度条状态，可选 Normal、Success、Exception、Active |
| `ShowProgressInfo` | `bool` | `true` | 是否显示进度百分比信息 |
| `SizeType` | `SizeType` | `Large` | 尺寸，可选 Large、Middle、Small |
| `Orientation` | `Orientation` | `Horizontal` | 方向，可选 Horizontal、Vertical |
| `PercentPosition` | `PercentPosition` | `PercentPosition { IsInner = false, Alignment = End }` | 百分比文本的显示位置 |
| `StrokeLineCap` | `PenLineCap` | `Round` | 线条端点形状，可选 Round、Square |
| `StrokeBrush` | `IBrush` | - | 进度条描边画笔，支持渐变色 |
| `SuccessThreshold` | `double` | `0` | 成功阈值，超过此值的部分以成功色标识 |
| `SuccessStrokeBrush` | `IBrush` | - | 成功段的描边颜色，默认浅绿色 |
| `IsEnabled` | `bool` | `true` | 是否启用组件 |

### PercentPosition

`PercentPosition` 是一个 record struct，用于控制百分比文本在进度条上的位置。

| 字段 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `IsInner` | `bool` | `false` | 为 `true` 时百分比显示在进度条内部，为 `false` 时显示在外部 |
| `Alignment` | `LinePercentAlignment` | `End` | 对齐方式 |

### LinePercentAlignment

| 值 | 说明 |
|----|------|
| `Start` | 百分比文本位于进度条起始位置 |
| `Center` | 百分比文本位于进度条中间位置 |
| `End` | 百分比文本位于进度条末尾位置 |

---

## CircleProgress

`CircleProgress` 继承自 `AbstractCircleProgress`，以圆环形式展示进度。

### 属性

| 属性 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `Value` | `double` | `0` | 当前进度值 |
| `Minimum` | `double` | `0` | 最小值 |
| `Maximum` | `double` | `100` | 最大值 |
| `Status` | `ProgressStatus` | `Normal` | 进度条状态 |
| `SizeType` | `SizeType` | `Large` | 尺寸 |
| `StrokeLineCap` | `PenLineCap` | `Round` | 线条端点形状 |
| `StrokeBrush` | `IBrush` | - | 描边画笔 |
| `StepCount` | `int` | `0` | 分段数量，大于 0 时启用分段模式 |
| `StepGap` | `double` | `0` | 分段间距 |
| `IndicatorThickness` | `double` | - | 圆环厚度 |
| `SuccessThreshold` | `double` | `0` | 成功阈值 |
| `IsEnabled` | `bool` | `true` | 是否启用组件 |

---

## DashboardProgress

`DashboardProgress` 继承自 `AbstractCircleProgress`，是带缺口的仪表盘样式进度组件。与 `CircleProgress` 无继承关系，二者独立继承自 `AbstractCircleProgress`。

### 属性

除继承 `CircleProgress` 相同的基础属性外，还包含以下特有属性：

| 属性 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `DashboardGapPosition` | `DashboardGapPosition` | `Bottom` | 仪表盘缺口位置，可选 Left、Top、Right、Bottom |
| `GapDegree` | `double` | `75` | 缺口角度大小 |

---

## StepsProgressBar

`StepsProgressBar` 是分段式线性进度条，将进度条分割为若干段展示。

### 属性

| 属性 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `Value` | `double` | `0` | 当前进度值 |
| `Minimum` | `double` | `0` | 最小值 |
| `Maximum` | `double` | `100` | 最大值 |
| `Status` | `ProgressStatus` | `Normal` | 进度条状态 |
| `SizeType` | `SizeType` | `Large` | 尺寸 |
| `Steps` | `int` | `1` | 分段数量 |
| `Orientation` | `Orientation` | `Horizontal` | 方向 |
| `PercentPosition` | `string` | - | 百分比位置，可选 Start、Center、End |
| `StepsStrokeBrush` | `List<IBrush>` | - | 每段的自定义颜色列表 |
| `IsEnabled` | `bool` | `true` | 是否启用组件 |
