类名: __toolTip__

```json
{  
	"item": "minecraft:coal",
	"text" : [ "This is coal.", "It burns" ],
	"clearExisting" : true,
	"mode" : "noshift"
}
```

* __item__: 该属性定义了该条工具提示条目所作用的物品.
* __text__: 这是一个字符串列表, 其中每个字符串都是工具提示中的一行.
* __clearExisting__: 指定是否应清除现有工具提示, 你可以使用该属性来替换现有的工具提示. 这是可选的，默认为 `false`.
* __mode__: 该属性指示工具提示在何时显示. 共有7种模式: 
  * `all`       (任何时候)
  * `ctrl`      (按下Ctrl键的时候)
  * `shift`     (按下Shift键的时候)
  * `alt`       (按下Alt键的时候)
  * `noctrl`    (没有按下Ctrl键的时候) 
  * `noshift`   (没有按下Shift键的时候)
  * `noalt`     (没有按下Alt键的时候).

## 示例

以下两个工具提示使煤可以显示 `Press SHIFT for more text`. 注意, 第一个工具提示的属性 `mode` 被设置为 `noshift` 而不是 `all`. 否则, 按下SHIFT键时仍会显示 `Press SHIFT for more text` .
```json
{  
	"item": "minecraft:coal",
	"text" : [ "Press SHIFT for more text" ],
	"mode" : "noshift"
},
{  
	"item": "minecraft:coal",
	"text" : [ "This is coal.", "It burns." ],
	"mode" : "shift"
}
```
