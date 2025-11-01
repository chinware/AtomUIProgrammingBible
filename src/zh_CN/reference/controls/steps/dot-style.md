# 垂直步骤条

### 基础用法

![AtomUI Steps](./images/dot-style.png)

```axaml
<atom:Steps CurrentStep="1" ItemIndicatorType="Dot">
    <atom:StepsItem Header="Finished" Description="This is a description." />
    <atom:StepsItem Header="In Progress" Description="This is a description." SubHeader="Left 00:00:08" />
    <atom:StepsItem Header="Waiting" Description="This is a description." />
</atom:Steps>
```

### Mini尺寸

![AtomUI Steps](./images/vertical-dot-style.png)

```axaml
<StackPanel Orientation="Vertical" Spacing="20">
    <atom:Steps CurrentStep="1" ItemIndicatorType="Dot" Orientation="Vertical">
        <atom:StepsItem Header="Finished" Description="This is a description." />
        <atom:StepsItem Header="In Progress" Description="This is a description." SubHeader="Left 00:00:08" />
        <atom:StepsItem Header="Waiting" Description="This is a description." />
    </atom:Steps>
    <atom:Separator/>
    <atom:Steps CurrentStep="1" ItemIndicatorType="Dot" Orientation="Vertical" SizeType="Small">
        <atom:StepsItem Header="Finished" Description="This is a description." />
        <atom:StepsItem Header="In Progress" Description="This is a description." SubHeader="Left 00:00:08" />
        <atom:StepsItem Header="Waiting" Description="This is a description." />
    </atom:Steps>
</StackPanel>
```
