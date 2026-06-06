# 角标

头像组件支持数字角标功能，通常用于消息提示。

![AtomUI Avatar](./images/badge.png)

```xaml
<StackPanel>
    <atom:CountBadge Count="5">
        <atom:Avatar Shape="Square" Icon="{atom:IconProvider UserOutlined}" />
    </atom:CountBadge>
    <atom:DotBadge>
        <atom:Avatar Shape="Square" Icon="{atom:IconProvider UserOutlined}" />
    </atom:DotBadge>
</StackPanel>
```