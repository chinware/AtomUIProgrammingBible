# Block Node

`ToggleType` 为Radio表示节点切换类型为单选模式，`IsDefaultExpandAll` 为True表示所有节点默认展开，`NodeHoverMode` 为Block设置节点悬停效果为块状高亮，`IsEnabled` 为False表示禁用某个节点。

![AtomUI TreeView组件](./images/block-mode.webp)

```axaml
<atom:TreeView ToggleType="Radio" IsDefaultExpandAll="True" NodeHoverMode="Block">
    <atom:TreeViewItem Header="parent">
        <atom:TreeViewItem Header="child 1" IsEnabled="False" />
        <atom:TreeViewItem Header="child 2" />
    </atom:TreeViewItem>
</atom:TreeView>
```
