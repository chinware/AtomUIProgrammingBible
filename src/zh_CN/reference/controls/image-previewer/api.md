# ImagePreviewer API 参考

## ImagePreviewer

`ImagePreviewer` 继承自 `AbstractImagePreviewer`，用于展示和预览图片，支持缩放、旋转、画廊浏览等功能。

### 自有属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `CoverIndicatorContent` | 封面指示器的内容 | `object?` | `null` |
| `CoverIndicatorContentTemplate` | 封面指示器的数据模板 | `IDataTemplate?` | `null` |
| `CoverImageSrc` | 自定义封面图片的路径 | `string?` | `null` |
| `IsShowCoverMask` | 是否显示封面遮罩层 | `bool` | `true` |

### 继承属性（来自 AbstractImagePreviewer）

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `Sources` | 图片源列表 | `IList<string>?` | `null` |
| `FallbackImageSrc` | 加载失败时的兜底图片路径 | `string?` | `null` |
| `IsOpen` | 预览对话框是否处于打开状态 | `bool` | `false` |
| `IsMotionEnabled` | 是否启用动画效果 | `bool` | `false` |
| `CoverWidth` | 封面图片的宽度 | `double` | `NaN` |
| `CoverHeight` | 封面图片的高度 | `double` | `NaN` |
| `CurrentIndex` | 当前预览图片的索引 | `int` | `0` |
| `IsImageMovable` | 预览时图片是否可拖拽移动 | `bool` | `true` |
| `ImageScaleStep` | 图片缩放步长 | `double` | `0.5` |
| `ImageMinScale` | 图片最小缩放比例 | `double` | `1.0` |
| `ImageMaxScale` | 图片最大缩放比例 | `double` | `50.0` |
| `IsDialogModal` | 预览对话框是否为模态 | `bool` | `false` |

### 事件

| 事件 | 说明 | 参数类型 |
|---|---|---|
| `DialogOpened` | 预览对话框打开时触发 | `EventArgs` |
| `DialogClosed` | 预览对话框关闭后触发 | `EventArgs` |
| `DialogClosing` | 预览对话框关闭前触发，可取消关闭操作 | `CancelEventArgs` |
