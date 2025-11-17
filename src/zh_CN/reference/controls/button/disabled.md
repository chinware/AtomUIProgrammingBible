# 禁用

用户对软件的使用方式总是千奇百怪，他们的好奇心也非常旺盛，使用 `IsEnabled` 属性，一键控制奇怪操作带来的奇怪后果。

![AtomUI Button组件](./images/disabled-button.webp)

```axaml
<WrapPanel HorizontalAlignment="Stretch" Orientation="Vertical">
    <StackPanel Orientation="Horizontal">
        <atom:Button ButtonType="Primary">
            Primary
        </atom:Button>
        <atom:Button ButtonType="Primary" IsEnabled="False">
            Primary(disabled)
        </atom:Button>
    </StackPanel>
    <StackPanel Orientation="Horizontal">
        <atom:Button ButtonType="Default">
            Default
        </atom:Button>
        <atom:Button ButtonType="Default" IsEnabled="False">
            Default(disabled)
        </atom:Button>
    </StackPanel>
    <StackPanel Orientation="Horizontal">
        <atom:Button ButtonType="Text">
            Text
        </atom:Button>
        <atom:Button ButtonType="Text" IsEnabled="False">
            Text(disabled)
        </atom:Button>
    </StackPanel>
    <StackPanel Orientation="Horizontal">
        <atom:Button ButtonType="Link">
            Link
        </atom:Button>
        <atom:Button ButtonType="Link" IsEnabled="False">
            Link(disabled)
        </atom:Button>
    </StackPanel>

    <StackPanel Orientation="Horizontal">
        <atom:Button ButtonType="Primary" IsDanger="True">
            Danger Primary
        </atom:Button>
        <atom:Button ButtonType="Primary" IsDanger="True" IsEnabled="False">
            Danger Primary(disabled)
        </atom:Button>
    </StackPanel>
    <StackPanel Orientation="Horizontal">
        <atom:Button ButtonType="Default" IsDanger="True">
            Danger Default
        </atom:Button>
        <atom:Button ButtonType="Default" IsDanger="True" IsEnabled="False">
            Danger Default(disabled)
        </atom:Button>
    </StackPanel>
    <StackPanel Orientation="Horizontal">
        <atom:Button ButtonType="Text" IsDanger="True">
            Danger Text
        </atom:Button>
        <atom:Button ButtonType="Text" IsDanger="True" IsEnabled="False">
            Danger Text(disabled)
        </atom:Button>
    </StackPanel>
    <StackPanel Orientation="Horizontal">
        <atom:Button ButtonType="Link" IsDanger="True">
            Danger Link
        </atom:Button>
        <atom:Button ButtonType="Link" IsDanger="True" IsEnabled="False">
            Danger Link(disabled)
        </atom:Button>
    </StackPanel>
    
    <Border Background="rgb(190, 200, 200)">
        <StackPanel Orientation="Horizontal">
            <atom:Button IsGhost="True">
                Ghost
            </atom:Button>
            <atom:Button IsGhost="True" IsEnabled="False">
                Ghost(disabled)
            </atom:Button>
        </StackPanel>
    </Border>
</WrapPanel>
```