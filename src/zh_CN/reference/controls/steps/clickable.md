# 垂直步骤条

![AtomUI Steps](./images/clickable.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="20">
    <atom:Steps CurrentStep="0" IsItemClickable="True">
        <atom:StepsItem Header="Step 1" Description="This is a description." />
        <atom:StepsItem Header="Step 2" Description="This is a description." SubHeader="Left 00:00:08"/>
        <atom:StepsItem Header="Step 3" Description="This is a description." />
    </atom:Steps>
    <atom:Separator/>
    <atom:Steps CurrentStep="0" IsItemClickable="True" Orientation="Vertical">
        <atom:StepsItem Header="Step 1" Description="This is a description." />
        <atom:StepsItem Header="Step 2" Description="This is a description." SubHeader="Left 00:00:08"/>
        <atom:StepsItem Header="Step 3" Description="This is a description." />
    </atom:Steps>
    <atom:Separator/>
    <atom:Steps CurrentStep="0" IsItemClickable="True" ItemIndicatorType="Dot">
        <atom:StepsItem Header="Step 1" Description="This is a description." />
        <atom:StepsItem Header="Step 2" Description="This is a description." SubHeader="Left 00:00:08"/>
        <atom:StepsItem Header="Step 3" Description="This is a description." />
        <atom:StepsItem Header="Step 4" Description="This is a description." />
    </atom:Steps>
    <atom:Separator/>
    <atom:Steps CurrentStep="0" IsItemClickable="True" ItemIndicatorType="Dot" Orientation="Vertical">
        <atom:StepsItem Header="Step 1" Description="This is a description." />
        <atom:StepsItem Header="Step 2" Description="This is a description." SubHeader="Left 00:00:08"/>
        <atom:StepsItem Header="Step 3" Description="This is a description." />
        <atom:StepsItem Header="Step 4" Description="This is a description." />
    </atom:Steps>
</StackPanel>
```