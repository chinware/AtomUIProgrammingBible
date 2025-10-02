# AtomUI Avatar组头像

头像组件支持头像组合展现。

![AtomUI Avatar](./images/group.png)

```axaml
<StackPanel Orientation="Vertical" Spacing="20">
    <atom:AvatarGroup>
        <atom:Avatar Src="avares://AtomUIGallery/Assets/AvatarShowCase/PeopleAvatar1.svg"/>
        <atom:Avatar Background="#f56a00">K</atom:Avatar>
        <atom:Avatar Background="#87d068" Icon="{atom:IconProvider UserOutlined}" />
        <atom:Avatar Icon="{atom:IconProvider AntDesignOutlined}" Background="#1677ff"/>
    </atom:AvatarGroup>
    <atom:Separator/>
    <atom:AvatarGroup MaxDisplayCount="2"
                      FoldInfoAvatarForeground="#f56a00"
                      FoldInfoAvatarBackground="#fde3cf">
        <atom:Avatar Src="avares://AtomUIGallery/Assets/AvatarShowCase/PeopleAvatar2.svg"/>
        <atom:Avatar Background="#f56a00">K</atom:Avatar>
        <atom:Avatar Background="#87d068" Icon="{atom:IconProvider UserOutlined}" />
        <atom:Avatar Icon="{atom:IconProvider AntDesignOutlined}" Background="#1677ff"/>
    </atom:AvatarGroup>
    <atom:Separator/>
    <atom:AvatarGroup MaxDisplayCount="2"
                      FoldInfoAvatarForeground="#f56a00"
                      FoldInfoAvatarBackground="#fde3cf"
                      SizeType="Large">
        <atom:Avatar Src="avares://AtomUIGallery/Assets/AvatarShowCase/PeopleAvatar3.svg"/>
        <atom:Avatar Background="#f56a00">K</atom:Avatar>
        <atom:Avatar Background="#87d068" Icon="{atom:IconProvider UserOutlined}" />
        <atom:Avatar Icon="{atom:IconProvider AntDesignOutlined}" Background="#1677ff"/>
    </atom:AvatarGroup>
    <atom:Separator/>
    <atom:AvatarGroup MaxDisplayCount="2"
                      FoldInfoAvatarForeground="#f56a00"
                      FoldInfoAvatarBackground="#fde3cf"
                      SizeType="Large"
                      FoldAvatarFlyoutTriggerType="Click">
        <atom:Avatar BitmapSrc="/Assets/AvatarShowCase/PeopleAvatar4.png"/>
        <atom:Avatar Background="#f56a00">K</atom:Avatar>
        <atom:Avatar Background="#87d068" Icon="{atom:IconProvider UserOutlined}" />
        <atom:Avatar Icon="{atom:IconProvider AntDesignOutlined}" Background="#1677ff"/>
    </atom:AvatarGroup>
    <atom:Separator/>
    <atom:AvatarGroup Shape="Square">
        <atom:Avatar Background="#fde3cf">A</atom:Avatar>
        <atom:Avatar Background="#f56a00">K</atom:Avatar>
        <atom:Avatar Background="#87d068" Icon="{atom:IconProvider UserOutlined}" />
        <atom:Avatar Icon="{atom:IconProvider AntDesignOutlined}" Background="#1677ff"/>
    </atom:AvatarGroup>
</StackPanel>
```