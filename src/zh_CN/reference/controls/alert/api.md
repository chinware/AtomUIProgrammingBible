# Alert API 参考

## 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `Type` | 警告提示类型 | `AlertType` | `Success` |
| `Message` | 提示消息内容（也可作为 Content 直接书写） | `string` | `""` |
| `Description` | 辅助描述信息 | `string?` | `null` |
| `IsShowIcon` | 是否显示类型对应的语义图标 | `bool` | `false` |
| `IsClosable` | 是否显示关闭按钮 | `bool` | `false` |
| `CloseIcon` | 自定义关闭按钮图标 | `PathIcon?` | `null`（默认使用 CloseOutlined） |
| `IsMessageMarqueEnabled` | 是否启用消息跑马灯滚动 | `bool` | `false` |
| `ExtraAction` | 自定义操作区域，位于 Alert 右侧 | `Control?` | `null` |

## 事件

| 事件 | 说明 | 参数类型 |
|---|---|---|
| `CloseRequest` | 点击关闭按钮时触发 | `EventHandler` |

## 枚举类型

### AlertType

| 值 | 说明 | 图标 |
|---|---|---|
| `Success` | 成功提示，绿色系 | CheckCircleFilled |
| `Info` | 信息提示，蓝色系 | InfoCircleFilled |
| `Warning` | 警告提示，黄色系 | ExclamationCircleFilled |
| `Error` | 错误提示，红色系 | CloseCircleFilled |

## 伪类（Pseudo Classes）

| 伪类 | 说明 |
|---|---|
| `:has-description` | Description 属性非空时 |
| `:has-extra-action` | ExtraAction 属性非空时 |

## 模板部件（Template Parts）

| 名称 | 类型 | 说明 |
|---|---|---|
| `PART_CloseBtn` | `IconButton` | 关闭按钮 |
