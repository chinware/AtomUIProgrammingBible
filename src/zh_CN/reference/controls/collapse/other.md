# Collapse 其他用法

### 箭头位置

![AtomUI Collapse组件](./images/expand-icon-position.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="20">
    <atom:Collapse ExpandIconPosition="{Binding CollapseExpandIconPosition}">
        <atom:CollapseItem Header="This is panel header 1"
                           AddOnContent="{antdicons:AntDesignIconProvider Kind=SettingOutlined}">
            <atom:TextBlock TextWrapping="Wrap">
                A dog is a type of domesticated animal. Known for its loyalty and faithfulness, it can be found as a welcome guest in many households across the world.
            </atom:TextBlock>
        </atom:CollapseItem>
        <atom:CollapseItem Header="This is panel header 2"
                           AddOnContent="{antdicons:AntDesignIconProvider Kind=SettingOutlined}">
            <atom:TextBlock TextWrapping="Wrap">
                A dog is a type of domesticated animal. Known for its loyalty and faithfulness, it can be found as a welcome guest in many households across the world.
            </atom:TextBlock>
        </atom:CollapseItem>
        <atom:CollapseItem Header="This is panel header 3"
                           AddOnContent="{antdicons:AntDesignIconProvider Kind=SettingOutlined}">
            <atom:TextBlock TextWrapping="Wrap">
                A dog is a type of domesticated animal. Known for its loyalty and faithfulness, it can be found as a welcome guest in many households across the world.
            </atom:TextBlock>
        </atom:CollapseItem>
    </atom:Collapse>

    <StackPanel Orientation="Horizontal" Spacing="5">
        <atom:TextBlock VerticalAlignment="Center">Expand Icon Position:</atom:TextBlock>
        <atom:OptionButtonGroup ButtonStyle="Outline" Name="ExpandButtonPosGroup">
            <atom:OptionButton IsChecked="True">Start</atom:OptionButton>
            <atom:OptionButton>End</atom:OptionButton>
        </atom:OptionButtonGroup>
    </StackPanel>
</StackPanel>
```

### 幽灵面板

![AtomUI Collapse组件](./images/ghost-collapse.png)

```xaml
<atom:Collapse IsGhostStyle="True">
    <atom:CollapseItem Header="This is panel header 1">
        <atom:TextBlock TextWrapping="Wrap">
            A dog is a type of domesticated animal. Known for its loyalty and faithfulness, it can be found as a welcome guest in many households across the world.
        </atom:TextBlock>
    </atom:CollapseItem>
    <atom:CollapseItem Header="This is panel header 2">
        <atom:TextBlock TextWrapping="Wrap">
            A dog is a type of domesticated animal. Known for its loyalty and faithfulness, it can be found as a welcome guest in many households across the world.
        </atom:TextBlock>
    </atom:CollapseItem>
    <atom:CollapseItem Header="This is panel header 3">
        <atom:TextBlock TextWrapping="Wrap">
            A dog is a type of domesticated animal. Known for its loyalty and faithfulness, it can be found as a welcome guest in many households across the world.
        </atom:TextBlock>
    </atom:CollapseItem>
</atom:Collapse>
```

### 相应区域

![AtomUI Collapse组件](./images/click-area.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:Collapse>
        <atom:CollapseItem Header="This panel can only be collapsed by clicking text">
            <atom:TextBlock TextWrapping="Wrap">
                A dog is a type of domesticated animal. Known for its loyalty and faithfulness, it can be found as a welcome guest in many households across the world.
            </atom:TextBlock>
        </atom:CollapseItem>
    </atom:Collapse>
    <atom:Collapse TriggerType="Icon">
        <atom:CollapseItem Header="This panel can only be collapsed by clicking icon">
            <atom:TextBlock TextWrapping="Wrap">
                A dog is a type of domesticated animal. Known for its loyalty and faithfulness, it can be found as a welcome guest in many households across the world.
            </atom:TextBlock>
        </atom:CollapseItem>
    </atom:Collapse>

    <atom:Collapse IsEnabled="False">
        <atom:CollapseItem Header="This panel can't be collapsed">
            <atom:TextBlock TextWrapping="Wrap">
                A dog is a type of domesticated animal. Known for its loyalty and faithfulness, it can be found as a welcome guest in many households across the world.
            </atom:TextBlock>
        </atom:CollapseItem>
    </atom:Collapse>

    <atom:Collapse IsEnabled="False">
        <atom:CollapseItem Header="This panel can't be collapsed" IsSelected="True">
            <atom:TextBlock TextWrapping="Wrap">
                A dog is a type of domesticated animal. Known for its loyalty and faithfulness, it can be found as a welcome guest in many households across the world.
            </atom:TextBlock>
        </atom:CollapseItem>
    </atom:Collapse>
</StackPanel>
```
