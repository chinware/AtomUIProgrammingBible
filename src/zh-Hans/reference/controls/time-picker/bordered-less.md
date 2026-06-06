# 多样式设定

将 `StyleVariant` 属性设置为 `Outline`、`Filled` 或 `Borderless` 来设定多样式。

![AtomUI TimePicker](./images/variants.png)

```xaml
<StackPanel Orientation="Vertical" Spacing="10">
    <StackPanel Orientation="Horizontal" Spacing="5">
        <atom:TimePicker Watermark="Outline"
                         StyleVariant="Outline" />
        <atom:RangeTimePicker StyleVariant="Outline"
                              Watermark="Outline" />
    </StackPanel>
    <StackPanel Orientation="Horizontal" Spacing="5">
        <atom:TimePicker Watermark="Filled"
                         StyleVariant="Filled" />
        <atom:RangeTimePicker StyleVariant="Filled"
                              Watermark="Filled" />
    </StackPanel>
    <StackPanel Orientation="Horizontal" Spacing="5">
        <atom:TimePicker Watermark="Borderless"
                         StyleVariant="Borderless" />
        <atom:RangeTimePicker StyleVariant="Borderless"
                              Watermark="Borderless" />
    </StackPanel>
</StackPanel>
```