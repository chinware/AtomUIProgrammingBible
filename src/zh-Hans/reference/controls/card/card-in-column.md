# 栅格卡片

配合 `Grid` 栅格布局使用，可以达到非常不错的预览墙效果。

![AtomUI Card组件](./images/card-in-column.png)

```xaml
<Border Padding="20"">
    <Grid RowDefinitions="*" ColumnDefinitions="*, *, *" ColumnSpacing="20">
        <atom:Card Header="Card title" StyleVariant="Borderless" Grid.Row="0" Grid.Column="0" HorizontalAlignment="Stretch">
            <StackPanel Orientation="Vertical" Spacing="3">
                <atom:TextBlock>Card content</atom:TextBlock>
                <atom:TextBlock>Card content</atom:TextBlock>
                <atom:TextBlock>Card content</atom:TextBlock>
            </StackPanel>
        </atom:Card>
        <atom:Card Header="Card title" StyleVariant="Borderless" Grid.Row="0" Grid.Column="1" HorizontalAlignment="Stretch">
            <StackPanel Orientation="Vertical" Spacing="3">
                <atom:TextBlock>Card content</atom:TextBlock>
                <atom:TextBlock>Card content</atom:TextBlock>
                <atom:TextBlock>Card content</atom:TextBlock>
            </StackPanel>
        </atom:Card>
        <atom:Card Header="Card title" StyleVariant="Borderless" Grid.Row="0" Grid.Column="2" HorizontalAlignment="Stretch">
            <StackPanel Orientation="Vertical" Spacing="3">
                <atom:TextBlock>Card content</atom:TextBlock>
                <atom:TextBlock>Card content</atom:TextBlock>
                <atom:TextBlock>Card content</atom:TextBlock>
            </StackPanel>
        </atom:Card>
    </Grid>
</Border>
```