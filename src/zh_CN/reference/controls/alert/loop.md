# Alert 自定义行为

当文案过长时，可以通过 `IsMessageMarqueEnabled` 属性开启滚动效果。

![AtomUI Alert组件滚动效果](./images/loop-banner.webp)

```axaml
<atom:Alert Type="Warning" IsShowIcon="True" IsMessageMarqueEnabled="True">
    I can be a React component, multiple React components, or just some text, Info Description Info Description Info Description Info Description
</atom:Alert>
```