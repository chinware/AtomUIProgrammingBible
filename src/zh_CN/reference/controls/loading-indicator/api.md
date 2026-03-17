# Spin API 参考

## 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `SizeType` | 指示器尺寸 | `SizeType` | `Middle` |
| `Tip` | 加载提示文案 | `string?` | `null` |
| `IsShowTip` | 是否显示加载提示文案 | `bool` | `false` |
| `CustomIndicator` | 自定义加载指示器内容 | `object?` | `null` |
| `CustomIndicatorTemplate` | 自定义加载指示器的数据模板 | `IDataTemplate?` | `null` |
| `MotionDuration` | 加载动画持续时长 | `TimeSpan` | — |
| `MotionEasingCurve` | 加载动画缓动曲线 | `Easing?` | `null` |
| `IsSpinning` | 是否处于加载中状态 | `bool` | `false` |
| `IsMaskBlurEnabled` | 是否启用遮罩模糊效果 | `bool` | `true` |
| `IsMaskBackgroundEnabled` | 是否启用遮罩背景 | `bool` | `true` |
| `IsMotionEnabled` | 是否启用过渡动画 | `bool` | `true` |

## 继承关系

`Spin` 继承自 `ContentControl`，因此支持 `Content` 属性。将子内容放入 Spin 中，当 `IsSpinning="True"` 时会在内容上方显示加载遮罩。

## 枚举类型

### SizeType

| 值 | 说明 |
|---|---|
| `Small` | 小尺寸，适用于行内或紧凑区域 |
| `Middle` | 中等尺寸（默认） |
| `Large` | 大尺寸，适用于页面级加载 |
