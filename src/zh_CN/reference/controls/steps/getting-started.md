# 快速入门

### 基础配置条件

* Nuget安装Avalonia
* Nuget安装AtomUI

### 基础用法

![AtomUI Steps](./images/basic.png)

```axaml
<atom:Steps CurrentStep="0">
    <atom:StepsItem Header="Finished" Description="This is a description." />
    <atom:StepsItem Header="In Progress" Description="This is a description." SubHeader="Left 00:00:08" />
    <atom:StepsItem Header="Waiting" Description="This is a description." />
</atom:Steps>
```

### Mini尺寸

![AtomUI Steps](./images/mini-size.png)

```axaml
<atom:Steps CurrentStep="0" SizeType="Small">
    <atom:StepsItem Header="Finished" Description="This is a description." />
    <atom:StepsItem Header="In Progress" Description="This is a description." SubHeader="Left 00:00:08" />
    <atom:StepsItem Header="Waiting" Description="This is a description." />
</atom:Steps>
```

### 图标

![AtomUI Steps](./images/with-icon.webp)

```axaml
<atom:Steps CurrentStep="0">
    <atom:StepsItem Header="Login" Status="Finish" Icon="{atom:IconProvider Kind=UserOutlined}" />
    <atom:StepsItem Header="Verification" Status="Finish" Icon="{atom:IconProvider Kind=SolutionOutlined}" />
    <atom:StepsItem Header="Pay" Status="Process"
                    Icon="{atom:IconProvider Kind=LoadingOutlined, Animation=Spin}" />
    <atom:StepsItem Header="Done" Status="Wait" Icon="{atom:IconProvider Kind=SmileOutlined}" />
</atom:Steps>
```