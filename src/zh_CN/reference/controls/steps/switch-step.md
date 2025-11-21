# 切换流程

![AtomUI Steps](./images/switch-step.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="20">
    <atom:Steps Name="CurrentStepContentSteps" CurrentStep="{Binding CurrentStep}">
        <atom:StepsItem Header="First" Content="First-content" />
        <atom:StepsItem Header="Second" Content="Second-content" />
        <atom:StepsItem Header="Third" Content="Last-content" />
    </atom:Steps>
    <atom:DashedBorder BorderThickness="1"
                       BorderBrush="{DynamicResource {x:Static atom:SharedTokenKey.ColorBorder}}"
                       StrokeDashArray="{Binding #StepsShowCaseName.DashedArray}"
                       CornerRadius="{DynamicResource {x:Static atom:SharedTokenKey.BorderRadiusLG}}"
                       Background="{DynamicResource {x:Static atom:SharedTokenKey.ColorFillAlter}}"
                       TextElement.Foreground="{DynamicResource {x:Static atom:SharedTokenKey.ColorTextTertiary}}"
                       Height="260">
        <ContentPresenter Content="{Binding #CurrentStepContentSteps.CurrentContent}"
                          ContentTemplate="{Binding #CurrentStepContentSteps.CurrentContentTemplate}"
                          HorizontalAlignment="Center"
                          VerticalAlignment="Center" />
    </atom:DashedBorder>
    <StackPanel Orientation="Horizontal" Spacing="10">
        <atom:Button ButtonType="Primary" Content="Next" Name="NextStepButton" />
        <atom:Button ButtonType="Default" Content="Previous" Name="PreviousButton"
                     IsVisible="{Binding PreviousButtonVisible}" />
    </StackPanel>
</StackPanel>
```
