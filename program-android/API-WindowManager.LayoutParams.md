# Window LayoutParams Flag 说明
| Flag | Describe |
|:--|:--|
| FLAG_FULLSCREEN | 窗口显示时，隐藏所有的屏幕装饰（例如状态条）。使窗口占用整个显示区域。 |
| FLAG_LAYOUT_NO_LIMITS | 允许窗口扩展到屏幕之外 ,这里指的窗口之外就是 Statusbar(状态栏) 和 NavigationBar（导航栏) |
| FLAG_KEEP_SCREEN_ON | 当此窗口为用户可见时，保持设备常开，并保持亮度不变。|

## 刘海屏相关参数 Android P 版本以上才有
| Flag | Describe |
|:--|:--|
LAYOUT_IN_DISPLAY_CUTOUT_MODE_DEFAULT|只有当DisplayCutout完全包含在系统状态栏中时，才允许窗口延伸到DisplayCutout区域显示。(横屏后，凹槽就到了左边或者右边)|
|LAYOUT_IN_DISPLAY_CUTOUT_MODE_NEVER|该窗口决不允许与DisplayCutout区域重叠。|
|LAYOUT_IN_DISPLAY_CUTOUT_MODE_SHORT_EDGES|该窗口始终允许延伸到屏幕短边上的DisplayCutout区域。|
