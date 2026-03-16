# Result API 参考

## 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `Status` | 结果状态，控制图标和配色风格 | `ResultStatus` | `Success` |
| `Header` | 标题内容 | `object?` | `null` |
| `HeaderTemplate` | 标题的数据模板 | `IDataTemplate?` | `null` |
| `HeaderFontSize` | 标题字体大小 | `double` | - |
| `SubHeader` | 副标题内容 | `object?` | `null` |
| `SubHeaderTemplate` | 副标题的数据模板 | `IDataTemplate?` | `null` |
| `SubHeaderFontSize` | 副标题字体大小 | `double` | - |
| `Icon` | 自定义图标，覆盖 Status 对应的默认图标 | `PathIcon?` | `null` |
| `Extra` | 额外操作区域，通常放置操作按钮 | `object?` | `null` |
| `ExtraTemplate` | 额外操作区域的数据模板 | `IDataTemplate?` | `null` |

> `Result` 继承自 `ContentControl`，因此其 `Content` 属性可用于放置自定义的详细内容（如错误详情列表等）。

## 枚举类型

### ResultStatus

| 值 | 说明 |
|---|---|
| `Info` | 信息提示，蓝色系图标 |
| `Success` | 成功结果，绿色系图标 |
| `Error` | 错误结果，红色系图标 |
| `Warning` | 警告结果，黄色系图标 |
| `ErrorCode404` | HTTP 404 错误，展示专属插画 |
| `ErrorCode403` | HTTP 403 错误，展示专属插画 |
| `ErrorCode500` | HTTP 500 错误，展示专属插画 |
