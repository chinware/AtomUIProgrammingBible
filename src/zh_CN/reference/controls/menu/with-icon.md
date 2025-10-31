# 图标与子菜单

![AtomUI Menu组件](./images/with-icon.webp)

axaml文件：
```axaml
<atom:Menu>
    <atom:MenuItem Header="_File">
        <atom:MenuItem Header="New Text File" InputGesture="Ctrl+N" />
        <atom:MenuItem Header="New File" InputGesture="Ctrl+Alt+N" />
        <atom:MenuItem Header="New Window" InputGesture="Ctrl+Shift+N" />
        <atom:MenuSeparator />
        <atom:MenuItem Header="Save" InputGesture="Ctrl+S" />
        <atom:MenuItem Header="Save As..." InputGesture="Ctrl+Shift+S" />
        <atom:MenuItem Header="Save All" InputGesture="Ctrl+K" />
        <atom:MenuSeparator />
        <atom:MenuItem Header="Exit" />
    </atom:MenuItem>
    <atom:MenuItem Header="_Edit">
        <atom:MenuItem Header="Undo" InputGesture="Ctrl+Shift+Z" />
        <atom:MenuSeparator />
        <atom:MenuItem Header="Cut" InputGesture="Ctrl+X" Icon="{atom:IconProvider Kind=ScissorOutlined}" />
        <atom:MenuItem Header="Copy" InputGesture="Ctrl+C" Icon="{atom:IconProvider Kind=CopyOutlined}" />
        <atom:MenuItem Header="Delete" InputGesture="Ctrl+D" Icon="{atom:IconProvider Kind=DeleteOutlined}" />
        <atom:MenuItem Header="Paste">
            <atom:MenuItem Header="Paste" InputGesture="Ctrl+P"
                           Icon="{atom:IconProvider Kind=FileDoneOutlined}" />
            <atom:MenuItem Header="Paste from History" InputGesture="Ctrl+Shift+V" />
        </atom:MenuItem>
    </atom:MenuItem>
</atom:Menu>
```
