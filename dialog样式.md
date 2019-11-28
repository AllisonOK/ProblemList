####dialog样式

```
<style name="DialogStyle" parent="Theme.AppCompat.Light.NoActionBar">
        <!--是否半透明-->
        <item name="android:windowIsTranslucent">true</item>
        <!--设置dialog的背景-->
        <item name="android:windowBackground">@color/transparent</item>
        <!--背景是否模糊显示-->
        <item name="android:backgroundDimEnabled">false</item>
        <!--设置窗口内容不覆盖-->
        <item name="android:windowContentOverlay">@null</item>
        <!--点击空白地方关闭-->
        <item name="android:windowCloseOnTouchOutside">false</item>
        <!--是否浮现在activity之上-->
        <item name="android:windowIsFloating">true</item>
        <!--设置动画，在这里使用让它继承系统的Animation.Dialog-->
        <item name="android:windowAnimationStyle">@android:style/Animation.Dialog</item>
    </style>
```
