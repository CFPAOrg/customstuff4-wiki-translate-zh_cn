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
	* __name__: This is the name of the inventory. For inventories in tile enties, this is the value used for the name attribute of the inventory module.
	* __firstSlot__: This is the index of the first slot from the inventory that is being used. This is usefull if you want one inventory to split into multiple areas. The player inventory, for example, is split into the hotbar and the non-hotbar areas. The default value is 0.
	* __rows__, __columns__: These define in how many rows and columns is separated in. They also define how many slots are added (rows * columns = totalSlots). Default values are 1.
	* __x__, __y__: These define where the top-left slot is positioned in the GUI, relative to the background.
	* __dropOnClose__: This defines whether the items in the slots should be dropped when closing the GUI. Default value is false.
	* __spacingX__, __spacingY__: The defines the spacing between the individual slots. Default value is 18.
* __shiftClickRules__: This a list of rules that define what happens when you shift-click a slot. In the example above, the first slots have indices 0 to 26, the second 27 to 53 and the last 54 to 62.
	* __from__: This defines the index of the first and last slot that the rule applies to.
	* __to__: This defines the index of the first and last slot that a itemstack is transferred to. If the first index is greater than the second index, it'll search in reverse order for a valid slot to put the stack to.
	* __filter__: This is a ItemFilter that defines what items this rule applies to. Default value allows all items.
* __labels__: This is a list of labels that are drawn onto the GUI.
	* __text__: The text that is being drawn.
	* __x__, __y__: The position of the text relative to the background.
	* __color__: This is a Color defining the color of the text. Default value is "404040".
	* __dropShadow__: Whether to draw the drop shadow. Default value is false.
* __progressBars__: This is a list of progress bars that are drawn onto the GUI.
	* __x__, __y__: The position of the bar relative to the background.
	* __texX__, __texY__: These define where in the background texture the progress bar is located.
	* __width__, __height__: The width and height of the bar when completely filled.
	* __direction__: The direction in which the bar fills. One of: up, down, left, right.
	* __source__: This defines where the progress for the bar comes from. For example, machine:burnTime, uses the burnTime from the tile entity module with the name machine.
* __fluidDisplays__: This is a list of fluid displays that are drawn onto the GUI.
	* __x__, __y__: The position of the display relative to the background.
	* __width__, __height__: The size of display.
	* __overlayTexX__, __overlayTexY__: If the tank has a overlay that is drawn onto the fluid, these define where in the background texture that overlay is located. The overlay has the same size as the display itself.
	* __source__: This defines where the data for the display is from. This can, for example, be the id of a tank module.
	





