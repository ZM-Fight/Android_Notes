
1. 
  ``` java
  android:layout_width="0dp"
  android:layout_weight="1"
  ```
  android:layout_weight 只在LinearLayout中起作用。

2.
  ImageView的background设置图片背景,src设置显示的图片内容。

  主要是考虑到当src为png等具有透明属性图片的时候,会显示自己设置的背景,而不是系统默认的填充色,有助于美化。
