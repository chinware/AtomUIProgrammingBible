# AtomUI Avatar多类型支持

头像组件支持图片、Icon以及字符，其中Icon和字符型可以自定义图标颜色及背景色。

![AtomUI Avatar](./images/type.png)

```axaml
<StackPanel>
    <atom:Avatar Icon="{atom:IconProvider UserOutlined}" />
    <atom:Avatar>U</atom:Avatar>
    <atom:Avatar Size="40">USER</atom:Avatar>
    <atom:Avatar Src="avares://AtomUIGallery/Assets/AvatarShowCase/AntDesign.svg" />
    <atom:Avatar Background="#fde3cf" Foreground="#f56a00">U</atom:Avatar>
    <atom:Avatar Background="#87d068" Icon="{atom:IconProvider UserOutlined}" />
</StackPanel>
```