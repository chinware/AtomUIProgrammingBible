# Empty API 参考

## 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `PresetImage` | 预设空状态图片样式 | `PresetEmptyImage?` | `null` |
| `ImagePath` | 自定义图片资源路径 | `string?` | `null` |
| `ImageSource` | 自定义图片源 | `string?` | `null` |
| `Description` | 描述文本内容 | `string?` | `null` |
| `SizeType` | 组件尺寸 | `SizeType` | `Middle` |
| `IsShowDescription` | 是否显示描述文本 | `bool` | `true` |

## 枚举类型

### PresetEmptyImage

| 值 | 说明 |
|---|---|
| `Simple` | 简洁风格预设图片 |
| `Default` | 默认风格预设图片 |

### SizeType

| 值 | 说明 |
|---|---|
| `Small` | 小尺寸 |
| `Middle` | 中等尺寸（默认） |
| `Large` | 大尺寸 |
