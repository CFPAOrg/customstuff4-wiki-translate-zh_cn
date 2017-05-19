# All GUIs
Some attributes are used by all types of GUIs:

```json
{
	"id" : "mygui"
}
```

* __id__: This is the unique id of the GUI. This is used to reference the GUI in blocks. This has to be all lowercase and must not contain spaces. It only has to be unique in your mod.

# Container
Type name: __gui:container__

This gui can have inventory slots. The following attributes are available:

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
  ]
}
```

* __width__: This defines the width of the GUI. Default value is 176.
* __height__: This defines the width of the GUI. Default value is 166.
* __bg__: This is a ResourceLocation defining the background texture for the gui. 
* __bgTexX__, __bgTexY__: These define where in the background texture the actual background is. The rectangle that is being drawn is at (bgTexX, bgTexY) and its size is (width, height). Default values are 0.
* __slots__: This is a list of inventory slots for the GUI. The order of this list is relevant for the shift-click rules.
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





