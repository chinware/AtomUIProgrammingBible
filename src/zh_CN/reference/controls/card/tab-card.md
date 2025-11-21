# Tab卡片

通过 `CardTabsContent` 子组件创建标签页，可以容纳展示更多内容。

![AtomUI Card组件](./images/tag-card.webp)

```xaml
<StackPanel Orientation="Vertical">
   <atom:Card Header="Card title" HorizontalAlignment="Stretch" SizeType="Large">
       <atom:Card.Extra>
           <atom:HyperLinkButton>More</atom:HyperLinkButton>
       </atom:Card.Extra>
       <atom:CardTabsContent>
           <atom:TabItem Header="Tab1">content1</atom:TabItem>
           <atom:TabItem Header="Tab2">content2</atom:TabItem>
       </atom:CardTabsContent>
   </atom:Card>

   <atom:Card HorizontalAlignment="Stretch">
       <atom:CardTabsContent>
           <atom:CardTabsContent.TabBarExtraContent>
               <atom:HyperLinkButton>More</atom:HyperLinkButton>
           </atom:CardTabsContent.TabBarExtraContent>
           <atom:TabItem Header="article">article content</atom:TabItem>
           <atom:TabItem Header="app">app content</atom:TabItem>
           <atom:TabItem Header="project">project content</atom:TabItem>
       </atom:CardTabsContent>
   </atom:Card>
</StackPanel>
```