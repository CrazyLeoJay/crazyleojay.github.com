# Android selector 使用

> Android中的Selector主要是用来改变ListView和Button控件的默认背景。

### 代码结构
> 没有添加任何属性时其内部代码结构
```xml
<?xml version="1.0" encoding="utf-8" ?>
<selector xmlns:android="http://schemas.android.com/apk/res/android">
    …………
</selector>
```

## 子标签 \<item/>

> 每个\<item/> 都表示一种情况

### 属性介绍：

|常用标记| 参数 | 数据类型 | 备注 |
|---|---|---|---|
||drawable | @drawable ||
||state_accelerated | Boolean |  |
||state_active | Boolean ||
||state_activated | Boolean ||
||state_checkable | Boolean ||
||state_checked | Boolean ||
||state_drag_can_accept | Boolean ||
||state_drag_hovered | Boolean ||
| 1 |state_enabled | Boolean | 设置是否响应事件,指所有事件 |
||state_first | Boolean ||
| 1 |state_focused | Boolean | 获得焦点 |
||state_hovered | Boolean ||
||state_last | Boolean ||
||state_middle | Boolean ||
| 1 |state_pressed | Boolean | 被点击时 |
| 1 |state_selected | Boolean | 当当前控件被选中 |
||state_single | Boolean ||
||state_window_focused | Boolean ||


### 示例

```xml
<?xml version="1.0" encoding="utf-8" ?>
    <selector xmlns:android="http://schemas.android.com/apk/res/android">
    <!-- 默认时的背景图片-->
      <item android:drawable="@drawable/pic1" />
    <!-- 没有焦点时的背景图片 -->
      <item android:state_window_focused="false" android:drawable="@drawable/pic1" />
    <!-- 非触摸模式下获得焦点并单击时的背景图片 -->
      <item android:state_focused="true" android:state_pressed="true"   android:drawable= "@drawable/pic2" />
    <!-- 触摸模式下单击时的背景图片-->
    <item android:state_focused="false" android:state_pressed="true"   android:drawable="@drawable/pic3" />
    <!--选中时的图片背景-->
      <item android:state_selected="true"   android:drawable="@drawable/pic4" />
    <!--获得焦点时的图片背景-->
      <item android:state_focused="true"   android:drawable="@drawable/pic5" />
    </selector>
```

