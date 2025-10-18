# 文字分割符

### 带有样式的文字

通过 `Title` 属性来设定文字，通过 `FontStyle` 来设定文字样式，通过 `TitlePosition` 来指定文字位置。

![AtomUI Separator组件](./images/title-separator.PNG)

```axaml
<StackPanel Orientation="Vertical">
    <atom:TextBlock TextWrapping="Wrap">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed nonne merninisti licere mihi ista probare, quae sunt a te dicta? Refert tamen, quo modo.
    </atom:TextBlock>
    <atom:Separator Title="Text" FontStyle="Italic" />
    <atom:TextBlock TextWrapping="Wrap">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed nonne merninisti licere mihi ista probare, quae sunt a te dicta? Refert tamen, quo modo.
    </atom:TextBlock>
    <atom:Separator Title="Left text" TitlePosition="Left" FontWeight="Bold" />
    <atom:TextBlock TextWrapping="Wrap">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed nonne merninisti licere mihi ista probare, quae sunt a te dicta? Refert tamen, quo modo.
    </atom:TextBlock>
    <atom:Separator Title="Right text" TitlePosition="Right" FontStyle="Oblique" />
    <atom:TextBlock TextWrapping="Wrap">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed nonne merninisti licere mihi ista probare, quae sunt a te dicta? Refert tamen, quo modo.
    </atom:TextBlock>
    <atom:Separator Title="Left Text with 0 orientationMargin" TitlePosition="Left" FontStyle="Oblique"
                    FontWeight="Medium" OrientationMargin="0" />
    <atom:TextBlock TextWrapping="Wrap">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed nonne merninisti licere mihi ista probare, quae sunt a te dicta? Refert tamen, quo modo.
    </atom:TextBlock>

    <atom:Separator Title="Right Text with 50px orientationMargin" TitlePosition="Right" TitleColor="Coral"
                    FontWeight="Medium"
                    OrientationMargin="50" />
    <atom:TextBlock TextWrapping="Wrap">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed nonne merninisti licere mihi ista probare, quae sunt a te dicta? Refert tamen, quo modo.
    </atom:TextBlock>
</StackPanel>
```

### 无样式的文字

通过 `IsPlain` 属性设定文字是否为普通正文样式。

![AtomUI Separator组件](./images/title-separator-without-style.PNG)

```axaml
<StackPanel Orientation="Vertical">
    <atom:TextBlock TextWrapping="Wrap">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed nonne merninisti licere mihi ista probare, quae sunt a te dicta? Refert tamen, quo modo.
    </atom:TextBlock>
    <atom:Separator Title="Text" IsPlain="True"/>
    <atom:TextBlock TextWrapping="Wrap">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed nonne merninisti licere mihi ista probare, quae sunt a te dicta? Refert tamen, quo modo.
    </atom:TextBlock>
    <atom:Separator Title="Left Text" TitlePosition="Left" IsPlain="True"/>
    <atom:TextBlock TextWrapping="Wrap">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed nonne merninisti licere mihi ista probare, quae sunt a te dicta? Refert tamen, quo modo.
    </atom:TextBlock>
    <atom:Separator Title="Right Text" TitlePosition="Right" IsPlain="True"/>
    <atom:TextBlock TextWrapping="Wrap">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed nonne merninisti licere mihi ista probare, quae sunt a te dicta? Refert tamen, quo modo.
    </atom:TextBlock>
</StackPanel>
```