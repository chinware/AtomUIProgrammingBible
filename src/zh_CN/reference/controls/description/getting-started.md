# Description 快速入门

### 基础配置条件

* Nuget安装Avalonia
* Nuget安装AtomUI

### 基础用法

![AtomUI Description组件](./images/basic.png)

```xaml
<atom:Descriptions Header="User Info">
    <atom:DescriptionItem Label="UserName" Content="Zhou Maomao" />
    <atom:DescriptionItem Label="Telephone" Content="1810000000" />
    <atom:DescriptionItem Label="Live" Content="Hangzhou, Zhejiang" />
    <atom:DescriptionItem Label="Remark" Content="empty" />
    <atom:DescriptionItem Label="Address"
                          Content="No. 18, Wantang Road, Xihu District, Hangzhou, Zhejiang, China" />
</atom:Descriptions>
```

### 边框

![AtomUI Description组件](./images/border.png)

```xaml
<atom:Descriptions IsBordered="True">
    <atom:DescriptionItem Label="Product" Content="Cloud Database" />
    <atom:DescriptionItem Label="Billing Mode" Content="Prepaid" />
    <atom:DescriptionItem Label="Automatic Renewal" Content="YES" />
    <atom:DescriptionItem Label="Order time" Content="2018-04-24 18:00:00" />
    <atom:DescriptionItem Label="Usage Time" Content="2019-04-24 18:00:00" Span="2" />
    <atom:DescriptionItem Label="Status" Content="Running" Span="3" />
    <atom:DescriptionItem Label="Negotiated Amount" Content="$80.00" />
    <atom:DescriptionItem Label="Discount" Content="$20.00" />
    <atom:DescriptionItem Label="Official Receipts" Content="$60.00" />
    <atom:DescriptionItem Label="Config Info">
        <atom:DescriptionItem.Content>
            <StackPanel Orientation="Vertical" Spacing="5">
                <TextBlock>Data disk type: MongoDB</TextBlock>
                <TextBlock>Database version: 3.4</TextBlock>
                <TextBlock>Package: dds.mongo.mid</TextBlock>
                <TextBlock>Storage space: 10 GB</TextBlock>
                <TextBlock>Replication factor: 3</TextBlock>
                <TextBlock>Region: East China 1</TextBlock>
            </StackPanel>
        </atom:DescriptionItem.Content>
    </atom:DescriptionItem>
</atom:Descriptions>
```

### 尺寸大小

![AtomUI Description组件](./images/size.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="30">
    <StackPanel Orientation="Horizontal" Spacing="10">
        <atom:RadioButton Name="DefaultSizeRadioButton" IsChecked="True">Large</atom:RadioButton>
        <atom:RadioButton Name="MiddleSizeRadioButton">Middle</atom:RadioButton>
        <atom:RadioButton Name="SmallSizeRadioButton">Small</atom:RadioButton>
    </StackPanel>
    <atom:Descriptions IsBordered="True" SizeType="{Binding DescriptionsSizeType}"
                       x:DataType="viewModels:DescriptionsViewModel"
                       Header="Custom Size">
        <atom:Descriptions.Extra>
            <atom:Button ButtonType="Primary">Edit</atom:Button>
        </atom:Descriptions.Extra>
        <atom:DescriptionItem Label="Product" Content="Cloud Database" />
        <atom:DescriptionItem Label="Billing Mode" Content="Prepaid" />
        <atom:DescriptionItem Label="Automatic Renewal" Content="YES" />
        <atom:DescriptionItem Label="Order time" Content="2018-04-24 18:00:00" />
        <atom:DescriptionItem Label="Usage Time" Content="2019-04-24 18:00:00" Span="2" />
        <atom:DescriptionItem Label="Status" Content="Running" Span="3" />
        <atom:DescriptionItem Label="Negotiated Amount" Content="$80.00" />
        <atom:DescriptionItem Label="Discount" Content="$20.00" />
        <atom:DescriptionItem Label="Official Receipts" Content="$60.00" />
        <atom:DescriptionItem Label="Config Info">
            <atom:DescriptionItem.Content>
                <StackPanel Orientation="Vertical" Spacing="5">
                    <TextBlock>Data disk type: MongoDB</TextBlock>
                    <TextBlock>Database version: 3.4</TextBlock>
                    <TextBlock>Package: dds.mongo.mid</TextBlock>
                    <TextBlock>Storage space: 10 GB</TextBlock>
                    <TextBlock>Replication factor: 3</TextBlock>
                    <TextBlock>Region: East China 1</TextBlock>
                </StackPanel>
            </atom:DescriptionItem.Content>
        </atom:DescriptionItem>
    </atom:Descriptions>

    <atom:Descriptions Header="Custom Size"
                       SizeType="{Binding DescriptionsSizeType}"
                       x:DataType="viewModels:DescriptionsViewModel">
        <atom:Descriptions.Extra>
            <atom:Button ButtonType="Primary">Edit</atom:Button>
        </atom:Descriptions.Extra>
        <atom:DescriptionItem Label="UserName" Content="Zhou Maomao" />
        <atom:DescriptionItem Label="Telephone" Content="1810000000" />
        <atom:DescriptionItem Label="Live" Content="Hangzhou, Zhejiang" />
        <atom:DescriptionItem Label="Remark" Content="empty" />
        <atom:DescriptionItem Label="Address"
                              Content="No. 18, Wantang Road, Xihu District, Hangzhou, Zhejiang, China" />
    </atom:Descriptions>
</StackPanel>
```

### 响应式

![AtomUI Description组件](./images/responseive.webp)

```xaml
<atom:Descriptions IsBordered="True" SizeType="{Binding DescriptionsSizeType}"
                   x:DataType="viewModels:DescriptionsViewModel"
                   Header="Responsive Descriptions"
                   ColumnInfo="xs: 1, sm: 2, md: 3, lg: 3, xl: 4, xxl: 4">
    <atom:DescriptionItem Label="Product" Content="Cloud Database" />
    <atom:DescriptionItem Label="Billing" Content="Prepaid" />
    <atom:DescriptionItem Label="Time" Content="18:00:00" />
    <atom:DescriptionItem Label="Amount" Content="$80.00" />
    <atom:DescriptionItem Label="Discount" Content="$20.00" Span="xl: 2, xxl: 2" />
    <atom:DescriptionItem Label="Official" Content="$60.00" Span="xl: 2, xxl: 2" />
    <atom:DescriptionItem Label="Config Info" Span="xs: 1, sm: 2, md: 3, lg: 3, xl: 2, xxl: 2">
        <atom:DescriptionItem.Content>
            <StackPanel Orientation="Vertical">
                <TextBlock>Data disk type: MongoDB</TextBlock>
                <TextBlock>Database version: 3.4</TextBlock>
                <TextBlock>Package: dds.mongo.mid</TextBlock>
            </StackPanel>
        </atom:DescriptionItem.Content>
    </atom:DescriptionItem>
    <atom:DescriptionItem Label="Hardware Info" Span="xs: 1, sm: 2, md: 3, lg: 3, xl: 2, xxl: 2">
        <atom:DescriptionItem.Content>
            <StackPanel Orientation="Vertical">
                <TextBlock>CPU: 6 Core 3.5 GHz</TextBlock>
                <TextBlock>Replication factor: 3</TextBlock>
                <TextBlock>Region: East China 1</TextBlock>
            </StackPanel>
        </atom:DescriptionItem.Content>
    </atom:DescriptionItem>
</atom:Descriptions>
```

### 垂直显示

![AtomUI Description组件](./images/vertical.png)

```xaml
<atom:Descriptions Header="User Info" Layout="Vertical">
    <atom:DescriptionItem Label="UserName" Content="Zhou Maomao" />
    <atom:DescriptionItem Label="Telephone" Content="1810000000" />
    <atom:DescriptionItem Label="Live" Content="Hangzhou, Zhejiang" />
    <atom:DescriptionItem Label="Remark" Content="empty" />
    <atom:DescriptionItem Label="Address"
                          Content="No. 18, Wantang Road, Xihu District, Hangzhou, Zhejiang, China" />
</atom:Descriptions>
```

### 垂直显示带边框

![AtomUI Description组件](./images/vertical-border.png)

```xaml
<atom:Descriptions IsBordered="True" Layout="Vertical">
    <atom:DescriptionItem Label="Product" Content="Cloud Database" />
    <atom:DescriptionItem Label="Billing Mode" Content="Prepaid" />
    <atom:DescriptionItem Label="Automatic Renewal" Content="YES" />
    <atom:DescriptionItem Label="Order time" Content="2018-04-24 18:00:00" />
    <atom:DescriptionItem Label="Usage Time" Content="2019-04-24 18:00:00" Span="2" />
    <atom:DescriptionItem Label="Status" Content="Running" Span="3" />
    <atom:DescriptionItem Label="Negotiated Amount" Content="$80.00" />
    <atom:DescriptionItem Label="Discount" Content="$20.00" />
    <atom:DescriptionItem Label="Official Receipts" Content="$60.00" />
    <atom:DescriptionItem Label="Config Info">
        <atom:DescriptionItem.Content>
            <StackPanel Orientation="Vertical" Spacing="5">
                <TextBlock>Data disk type: MongoDB</TextBlock>
                <TextBlock>Database version: 3.4</TextBlock>
                <TextBlock>Package: dds.mongo.mid</TextBlock>
                <TextBlock>Storage space: 10 GB</TextBlock>
                <TextBlock>Replication factor: 3</TextBlock>
                <TextBlock>Region: East China 1</TextBlock>
            </StackPanel>
        </atom:DescriptionItem.Content>
    </atom:DescriptionItem>
</atom:Descriptions>
```

### 垂直显示带边框

![AtomUI Description组件](./images/row.png)

```xaml
<atom:Descriptions Header="User Info" IsBordered="True">
    <atom:DescriptionItem Label="UserName" Content="Zhou Maomao" />
    <atom:DescriptionItem Label="Live" Content="Hangzhou, Zhejiang" IsFilled="True" />
    <atom:DescriptionItem Label="Remark" Content="empty" IsFilled="True" />
    <atom:DescriptionItem Label="Address"
                          Content="No. 18, Wantang Road, Xihu District, Hangzhou, Zhejiang, China" />
</atom:Descriptions>
```