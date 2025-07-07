# AtomUI Theme 系统支持的 Design Token

> [!NOTE]
> 以下内容大部分参考 Ant Design 的定义，少部分 AtomUI 根据 Avalonia 的类型系统进行了调整。
>
> [阅读 Ant Design 原版定义](https://ant.design/docs/react/customize-theme-cn)

## SeedToken

| Token 名称     | 描述                                                                             | 类型           | 	默认值      |
|--------------|--------------------------------------------------------------------------------|--------------|-----------|
| BorderRadius | 基础组件的圆角大小，例如按钮、输入框、卡片等                                                         | CornerRadius | 		6       |
| ColorBgBase  | 用于派生背景色梯度的基础变量，v5 中我们添加了一层背景色的派生算法可以产出梯度明确的背景色的梯度变量。但请不要在代码中直接使用该 Seed Token ！ | Color        | `#fff`    |
| ColorError   | 用于表示操作失败的 Token 序列，如失败按钮、错误状态提示（Result）组件等。	                                   | Color        | `#ff4d4f` |