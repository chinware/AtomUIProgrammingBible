# Statistic API 参考

## Statistic

统计数值组件，继承自 `AbstractStatistic`，用于突出展示某个或某组关键数据指标。

### 属性

| 属性名 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `Value` | `object?` | - | 需要展示的数值内容 |
| `Formatter` | `Func<Statistic, object?, string?>?` | - | 自定义数值格式化函数，接收当前 Statistic 实例和 Value，返回格式化后的字符串 |

## AbstractStatistic（基类属性）

以下属性由基类 `AbstractStatistic` 提供，`Statistic` 同样可以使用。

### 属性

| 属性名 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `Header` | `object?` | - | 统计项的标题 |
| `Precision` | `int?` | - | 数值的小数精度位数 |
| `IsLoading` | `bool` | `false` | 是否处于加载中状态，为 `True` 时显示骨架屏 |
| `ValuePrefixAddOn` | `object?` | - | 数值前缀内容，可设置为图标或文字 |
| `ValueSuffixAddOn` | `object?` | - | 数值后缀内容，可设置为文字单位等 |
