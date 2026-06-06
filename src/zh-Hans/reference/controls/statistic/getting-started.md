# Statistic 快速入门

### 基础配置条件

* Nuget安装Avalonia
* Nuget安装AtomUI

### 基础用法

![AtomUI Statistic组件](./images/basic.png)

```xaml
<UniformGrid Columns="2" Rows="2">
    <atom:Statistic Header="Active Users" Value="112893" />
    <StackPanel Orientation="Vertical" Spacing="16">
        <atom:Statistic Header="Account Balance (CNY)" Value="112893" Precision="2" />
        <atom:Button ButtonType="Primary">Recharge</atom:Button>
    </StackPanel>
    <atom:Statistic Header="Active Users" Value="112893" IsLoading="True" />
</UniformGrid>
```

### 位置设定

![AtomUI Statistic组件](./images/unit.png)

```xaml
<UniformGrid Columns="2" Rows="1">
    <atom:Statistic Header="Feedback" Value="1128" ValuePrefixAddOn="{antdicons:AntDesignIconProvider LikeOutlined}"/>
    <atom:Statistic Header="Unmerged" Value="93" ValueSuffixAddOn="/ 100"/>
</UniformGrid>
```
