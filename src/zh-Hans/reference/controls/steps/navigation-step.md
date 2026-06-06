# 导航步骤

![AtomUI Steps](./images/navigation-step.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="20">
    <atom:Steps CurrentStep="0" Style="Navigation" IsItemClickable="True" SizeType="Small">
        <atom:StepsItem Header="Step 1" Description="This is a description." SubHeader="00:00:05" Status="Finish"/>
        <atom:StepsItem Header="Step 2" Description="This is a description." SubHeader="00:01:02" Status="Process"/>
        <atom:StepsItem Header="Step 3" Description="This is a description." SubHeader="waiting for longlong time" Status="Wait"/>
    </atom:Steps>
    <atom:Separator/>
    <atom:Steps CurrentStep="0" Style="Navigation" IsItemClickable="True">
        <atom:StepsItem Header="Step 1" Status="Finish"/>
        <atom:StepsItem Header="Step 2" Status="Process"/>
        <atom:StepsItem Header="Step 3" Status="Wait"/>
        <atom:StepsItem Header="Step 4" Status="Wait"/>
    </atom:Steps>
    <atom:Separator/>
    <atom:Steps CurrentStep="0" Style="Navigation" IsItemClickable="True" SizeType="Small">
        <atom:StepsItem Header="finish 1" Status="Finish"/>
        <atom:StepsItem Header="finish 2" Status="Finish"/>
        <atom:StepsItem Header="current process" Status="Process"/>
        <atom:StepsItem Header="wait" Status="Wait" IsEnabled="False"/>
    </atom:Steps>
    <atom:Separator/>
    <atom:Steps CurrentStep="0" Style="Navigation" IsItemClickable="True" Orientation="Vertical">
        <atom:StepsItem Header="Step 1" Description="This is a description." SubHeader="00:00:05" Status="Finish"/>
        <atom:StepsItem Header="Step 2" Description="This is a description." SubHeader="10:00:05" Status="Process"/>
        <atom:StepsItem Header="Step 3" Description="This is a description." SubHeader="00:30:05" Status="Wait"/>
        <atom:StepsItem Header="Step 4" SubHeader="waiting for longlong time" Status="Wait"/>
    </atom:Steps>
    <atom:Separator/>
    <atom:Steps CurrentStep="0" Style="Navigation" IsItemClickable="True" Orientation="Vertical" SizeType="Small">
        <atom:StepsItem Header="Step 1" Description="This is a description." SubHeader="00:00:05" Status="Finish"/>
        <atom:StepsItem Header="Step 2" Description="This is a description." SubHeader="10:00:05" Status="Process"/>
        <atom:StepsItem Header="Step 3" Description="This is a description." SubHeader="00:30:05" Status="Wait"/>
        <atom:StepsItem Header="Step 4" SubHeader="waiting for longlong time" Status="Wait"/>
    </atom:Steps>
    <atom:Separator/>
    <atom:Steps CurrentStep="0" Style="Navigation" IsItemClickable="True" ItemIndicatorType="Dot">
        <atom:StepsItem Header="Step 1" Description="This is a description." SubHeader="00:00:05" />
        <atom:StepsItem Header="Step 2" Description="This is a description." SubHeader="00:01:02" />
        <atom:StepsItem Header="Step 3" Description="This is a description." SubHeader="03:01:02"/>
        <atom:StepsItem Header="Step 4" Description="This is a description." SubHeader="10:01:02"/>
    </atom:Steps>
    <atom:Separator/>
    <atom:Steps CurrentStep="0" Style="Navigation" IsItemClickable="True" ItemIndicatorType="Dot" SizeType="Small">
        <atom:StepsItem Header="Step 1" Description="This is a description." SubHeader="00:00:05" />
        <atom:StepsItem Header="Step 2" Description="This is a description." SubHeader="00:01:02" />
        <atom:StepsItem Header="Step 3" Description="This is a description." SubHeader="03:01:02"/>
        <atom:StepsItem Header="Step 4" Description="This is a description." SubHeader="10:01:02"/>
    </atom:Steps>
    <atom:Separator/>
    <atom:Steps CurrentStep="0" Style="Navigation" IsItemClickable="True" ItemIndicatorType="Dot" Orientation="Vertical">
        <atom:StepsItem Header="Step 1" Description="This is a description." SubHeader="00:00:05" />
        <atom:StepsItem Header="Step 2" Description="This is a description." SubHeader="00:01:02" />
        <atom:StepsItem Header="Step 3" Description="This is a description." SubHeader="03:01:02"/>
        <atom:StepsItem Header="Step 4" Description="This is a description." SubHeader="10:01:02"/>
    </atom:Steps>
    <atom:Separator/>
    <atom:Steps CurrentStep="0" Style="Navigation" IsItemClickable="True" ItemIndicatorType="Dot" SizeType="Small" Orientation="Vertical">
        <atom:StepsItem Header="Step 1" Description="This is a description." SubHeader="00:00:05" />
        <atom:StepsItem Header="Step 2" Description="This is a description." SubHeader="00:01:02" />
        <atom:StepsItem Header="Step 3" Description="This is a description." SubHeader="03:01:02"/>
        <atom:StepsItem Header="Step 4" Description="This is a description." SubHeader="10:01:02"/>
    </atom:Steps>
</StackPanel>
```