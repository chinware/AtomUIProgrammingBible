# 内联样式

![AtomUI Steps](./images/inline-steps.png)

```axaml
<ItemsControl>
    <DockPanel LastChildFill="True">
        <atom:Steps CurrentStep="0" DockPanel.Dock="Right" Style="Inline">
            <atom:StepsItem Header="Step 1" Description="This is a description."/>
            <atom:StepsItem Header="Step 2" Description="This is a description."/>
            <atom:StepsItem Header="Step 3" Description="This is a description."/>
        </atom:Steps>
        <StackPanel Orientation="Vertical" Spacing="10">
            <TextBlock FontWeight="Bold">Ant Design Title 1</TextBlock>
            <TextBlock Foreground="{DynamicResource {x:Static atom:SharedTokenKey.ColorTextTertiary}}">
                Ant Design, a design language for background applications, is refined by Ant UED Team
            </TextBlock>
            <atom:Separator/>
        </StackPanel>
    </DockPanel>
    <DockPanel LastChildFill="True">
        <atom:Steps CurrentStep="1" DockPanel.Dock="Right" Style="Inline" CurrentStepStatus="Error">
            <atom:StepsItem Header="Step 1" Description="This is a description."/>
            <atom:StepsItem Header="Step 2" Description="This is a description."/>
            <atom:StepsItem Header="Step 3" Description="This is a description."/>
        </atom:Steps>
        <StackPanel Orientation="Vertical" Spacing="10">
            <TextBlock FontWeight="Bold">Ant Design Title 2</TextBlock>
            <TextBlock Foreground="{DynamicResource {x:Static atom:SharedTokenKey.ColorTextTertiary}}">
                Ant Design, a design language for background applications, is refined by Ant UED Team
            </TextBlock>
            <atom:Separator/>
        </StackPanel>
    </DockPanel>
    <DockPanel LastChildFill="True">
        <atom:Steps CurrentStep="2" DockPanel.Dock="Right" Style="Inline">
            <atom:StepsItem Header="Step 1" Description="This is a description."/>
            <atom:StepsItem Header="Step 2" Description="This is a description."/>
            <atom:StepsItem Header="Step 3" Description="This is a description."/>
        </atom:Steps>
        <StackPanel Orientation="Vertical" Spacing="10">
            <TextBlock FontWeight="Bold">Ant Design Title 3</TextBlock>
            <TextBlock Foreground="{DynamicResource {x:Static atom:SharedTokenKey.ColorTextTertiary}}">
                Ant Design, a design language for background applications, is refined by Ant UED Team
            </TextBlock>
            <atom:Separator/>
        </StackPanel>
    </DockPanel>
    <DockPanel LastChildFill="True">
        <atom:Steps CurrentStep="1" DockPanel.Dock="Right" Style="Inline">
            <atom:StepsItem Header="Step 1" Description="This is a description."/>
            <atom:StepsItem Header="Step 2" Description="This is a description."/>
            <atom:StepsItem Header="Step 3" Description="This is a description."/>
        </atom:Steps>
        <StackPanel Orientation="Vertical" Spacing="10">
            <TextBlock FontWeight="Bold">Ant Design Title 4</TextBlock>
            <TextBlock Foreground="{DynamicResource {x:Static atom:SharedTokenKey.ColorTextTertiary}}">
                Ant Design, a design language for background applications, is refined by Ant UED Team
            </TextBlock>
        </StackPanel>
    </DockPanel>
</ItemsControl>
```