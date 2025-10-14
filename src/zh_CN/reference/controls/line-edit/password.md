# 密码隐私

密码输入是开发者经常用到的高频率业务场景，为此  `LineEdit` 提供了相关支持。

开发者只需要关注如下属性：
* `RevealPassword` 属性用于控制密码输入框的明文显示，如果为 `True` 时，密码输入框将显示明文，否则将显示密文。
* `PasswordChaar` 属性表示用于替换密码明文的字符。
* `IsEnableRevealButton` 属性用于控制是否启用密码显示/隐藏切换按钮，也就是密码输入框最右侧的那个小眼睛。

![AtomUI LineEdit组件](./images/password.webp)

axaml文件：
```axaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:LineEdit Watermark="input password"
                   Width="400"
                   RevealPassword="False"
                   PasswordChar="•"
                   HorizontalAlignment="Left"
                   IsEnableRevealButton="True" />
    <atom:LineEdit Watermark="input password"
                   Width="400"
                   RevealPassword="False"
                   HorizontalAlignment="Left"
                   PasswordChar="•"
                   IsEnableRevealButton="True"
                   IsEnableClearButton="True" />
</StackPanel>
```