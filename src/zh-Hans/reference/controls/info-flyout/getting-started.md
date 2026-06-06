# InfoFlyout 快速入门

### 基础配置条件

* Nuget安装Avalonia
* Nuget安装AtomUI

### 基础用法

`FlyoutHost` 容器作为触发器和飞出层的宿主容器，`Trigger` 属性（值为"Hover"）属性设置为悬停触发包含触发元素和飞出内容两部分。

通过 `FlyoutHost.Flyout` 附加属性定义飞出层内容，使用 `Flyout` 控件包装实际内容，本示例中内容为一个固定尺寸的 `TextBlock`。

![AtomUI InfoFlyout组件](./images/basic.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:FlyoutHost Trigger="Hover">
        <atom:FlyoutHost.Flyout>
            <atom:Flyout>
                <TextBlock Width="200" Height="100" Padding="20">The most basic example.</TextBlock>
            </atom:Flyout>
        </atom:FlyoutHost.Flyout>
        <atom:Button ButtonType="Primary">Hover me</atom:Button>
    </atom:FlyoutHost>
</StackPanel>
```