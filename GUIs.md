# 所有gui都遵循的共有法则
所有类型的GUI都使用这些属性:

```json
{
	"id" : "mygui"
}
```

* __id__: 这是GUI的**唯一**ID. 这用于使方块实例引用GUI. 该属性必须全部小写, 且不得包含空格. 该ID只需要在你的模组中的命名空间中保持唯一性.

# 容器
类名: __gui:container__

GUI可以使用物品槽, 并可以使用以下属性:

```json
{
  "width": 176,
  "height": 166,
  "bg": "mymod:textures/gui/container/mybg.png",
  "bgTexX": 0,
  "bgTexY": 0,
  "slots": [
    {
      "name": "inv1",
      "rows": 3,
      "columns": 9,
      "x": 8,
      "y": 17,
      "dropOnClose": true,
      "spacingX": 18,
      "spacingY": 18
    },
    {
      "name": "player",
      "firstSlot": 9,
      "rows": 3,
      "columns": 9,
      "x": 8,
      "y": 84
    },
    {
      "name": "player",
      "rows": 1,
      "columns": 9,
      "x": 8,
      "y": 142
    }
  ],
  "shiftClickRules": [
    {
      "from": [0, 26],
      "to": [62, 27]
    },
    {
      "from": [27, 62],
      "to": [0, 26],
      "filter": "ore:stickWood"
    }
  ],
  "labels": [
    {
      "text": "container.chest",
      "x": 8,
      "y": 6,
      "color": "red",
      "dropShadow": true
    },
    {
      "text": "container.inventory",
      "x": 8,
      "y": 73
    }
  ],
  "progressBars": [
    {
      "source": "machine:burnTime",
      "x": 56,
      "y": 36,
      "width": 14,
      "height": 13,
      "texX": 176,
      "texY": 0,
      "direction": "up"
    }
  ],
  "fluidDisplays": [
    {
      "source": "tank1",
      "x": 50,
      "y": 60,
      "width": 32,
      "height": 100,
      "overlayTexX": 166,
      "overlayTexY": 0
    }
  ]
}
```

* __width__: 该属性定义了GUI的宽度. 默认值为 `176`.
* __height__: 该属性定义了GUI的高度. 默认值为 `166`.
* __bg__: 该属性定义了一个本地资源导引, 用于GUI的背景纹理.
* __bgTexX__, __bgTexY__: 这些属性定义了背景材质中的实际背景的位置. 原点为背景材质左上方, 从(`bgTexX`, `bgTexY`)开始, 其大小为 `width * height` . 默认值都为 `0`.
* __slots__: 该属性定义了GUI的物品槽列表. 列表的顺序取决于Shift-Click(快速分发)策略.
	* __name__: 物品槽在GUI中的名称. 对于Tile Entities中所具有的物品槽模块, 这是用于填入物品槽模块的属性 `name` 的值以与其进行数据绑定.
	* __firstSlot__: 这是正在使用的物品槽的首槽的索引. 如果您希望将一个物品槽分成多个部分, 这将非常有用. 举个例子吧, 玩家的背包就使用这个特性将36个槽划分为快捷栏和背包两个部分. 默认值为 `0`.
	* __rows__, __columns__: 定义了物品槽的行数和列数. 这将会添加 `rows * columns` 个物品槽到GUI中. 默认值则都为 `1`.
	* __x__, __y__: 定义了物品槽的居于最左上角的槽在GUI中相对于背景的位置.
	* __dropOnClose__: 这定义了当关闭GUI时已在GUI内存放的物品是否会掉落到地面上. 默认值为 `false`.
	* __spacingX__, __spacingY__: 定义各个物品槽之间的间距. 默认值皆为 `18`.
* __shiftClickRules__: 这是一个规则列表, 用于定义当你按住Shift键单击物品槽时触发的事件. 在上面的示例中, 第一个物品槽堆的索引为 `0` 到 `26`, 第二个则为 `27` 到 `53`, 最后一个为 `54` 到 `62` .
	* __from__: 定义了规则适用的第一个和最后一个插槽的索引.
	* __to__: 定义了物品堆可移动到的第一个和最后一个物品槽的索引. 如果第一个索引大于第二个索引, 它将以相反的顺序搜索有效的插槽以将物品放入.
	* __filter__: 这是一个物品过滤器, 用于定义此规则所适用的物品. 默认可以接受任意物品.
* __labels__: 包含了将被绘制到GUI上的所有标签的列表.
	* __text__: 将被渲染的标签的内容
	* __x__, __y__: 标签相对于背景的位置.
	* __color__: 标签文字的颜色. 默认值为 `404040`.
	* __dropShadow__: 是否绘制投影(Drop Shadow). 默认值为 `false`.
* __progressBars__: 包含了绘制到GUI上的所有进度条的列表.
	* __x__, __y__: 进度条相对于背景的位置.
	* __texX__, __texY__: 定义了进度条所在的背景材质中的位置.
	* __width__, __height__: 进度条的宽度和高度(当进度为100%时).
	* __direction__: 从进度条起始位置向满进度进发的方向. 可以是 `up`(向上), `down`(向下), `left`(向左), `right`(向右) 中的任意一个.
	* __source__: 这定义了进度条的进度表示了什么. 举个例子, 像机器所具有的燃料值(`machine:burnTime`), 这将使用机器的Tile Entities中的 `machine` 模块的参数值 `burnTime`
* __fluidDisplays__: 包含了将被绘制到GUI上的所有流体槽的列表.
	* __x__, __y__: 流体槽相对于背景的位置.
	* __width__, __height__: 流体槽的尺寸(宽和高)
	* __overlayTexX__, __overlayTexY__: 如果流体槽具有绘制在流体上的覆盖层, 则这些覆盖层定义了覆盖层所在的背景材质中的位置. 覆加层的大小与流体槽本身的大小相同.
	* __source__: 定义数据源自何处. 举个例子, 你可以填入Tile Entities中的模块 `tank` 的id.
	





