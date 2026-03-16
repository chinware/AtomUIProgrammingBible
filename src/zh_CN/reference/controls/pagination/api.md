# Pagination API 参考

## Pagination

`Pagination` 继承自 `AbstractPagination`，用于创建标准的分页导航组件。

### 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `Total` | 数据总条数 | `int` | `0` |
| `CurrentPage` | 当前页码 | `int` | `1` |
| `PageSize` | 每页条目数 | `int` | `10` |
| `SizeType` | 分页组件的尺寸，可选 `Small`、`Middle`、`Large` | `SizeType` | `Middle` |
| `Align` | 分页组件的对齐方式 | `PaginationAlign` | `Start` |
| `IsShowSizeChanger` | 是否显示每页条目数切换器 | `bool` | `false` |
| `IsShowQuickJumper` | 是否显示快速跳转输入框 | `bool` | `false` |
| `IsShowTotalInfo` | 是否显示数据总数信息 | `bool` | `false` |
| `TotalInfoTemplate` | 总数信息的自定义模板，支持 `${RangeStart}`、`${RangeEnd}`、`${Total}` 占位符 | `string?` | `null` |

## 枚举类型

### PaginationAlign

| 值 | 说明 |
|---|---|
| `Start` | 左对齐（默认） |
| `Center` | 居中对齐 |
| `End` | 右对齐 |
