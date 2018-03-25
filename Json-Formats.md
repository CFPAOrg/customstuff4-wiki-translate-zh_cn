This is a list of how to specify certain things in json. 

# ResourceLocation
A ResourceLocation is used to define the location of textures, models, or for item or block identifiers. There are two ways to define an ResourceLocation.

Short version:

```json
"minecraft:stone"
	
"minecraft:textures/gui/bars.png"
```
	
Long version:

```json
{
  "domain" : "minecraft",
  "path" : "stone"
}

{
  "domain" : "minecraft",
  "path" : "textures/gui/bars.png"
}
```

# NBTTagCompound
A NBTTagCompound is defined as a string containg the nbt data:

```json
"{display:{Name:\"Some Obsidian\"}}"
```
	
# ItemStack
There a multiple ways of specifying an item stack:

```json
{
  "item" : "minecraft:stone",
  "metadata" : 10,
  "amount" : 42,
  "nbt" : "{display:{Name:\"Some Obsidian\"}}"
}
```
	
Everything but _item_ is optional. _metadata_ defaults to 0, _amount_ to 1.  
For some recipes you may want to allow all metadata variants. This can be done like this:

```json
{
  "item": "minecraft:stone",
  "metadata": "all",
  "amount": 42
}
```

Or like this:
```json
{
  "item": "minecraft:stone@all",
  "amount": 42
}
```
	
There is also a short version of defining an item stack. However that way you can only define the item and metadata:

```json
"minecraft:stone"
	
"minecraft:stone@1"
	
"minecraft:stone@all"
```
	
This will define an stack with an amount of 1. Omitting the metadata part will default in a metadata of 0.

## Examples
The following is a smelting recipe. Both _input_ and _result_ are item stacks:

```json
{
  "input": "minecraft:stone@all",
  "result": {
    "item": "minecraft:obsidian",
    "amount": 3,
    "nbt": "{display:{Name:\"Custom Obsidian\"}}"
  }
}
```

# BlockDrop
A BlockDrop is almost identical to an ItemStack. There's two additions:
You can set the amount to a range. In the following example, the actual amount that is dropped will be something between 1 and 3 including both.

```json
{
  "amount" : [1, 3]
}
```

You can also add a `fortuneAmount` property. This amount will be multiplied by the item's fortune level and then added to the regular amount.

```json
{
  "fortuneAmount" : 2
}
```

## Examples

The following will always drop at least 2 dirt. If the item has a fortune level of, for example 2, it will drop an additional 2 or 4 blocks of dirt.
```json
{
  "item": "minecraft:dirt",
  "amount": 2,
  "fortuneAmount": [1, 2]
}
```

Just like an ItemStack, you can define a BlockDrop like this:
```json
"minecraft:stone@1"
```
	
# RecipeInput
A recipe input is either an ItemStack or a ore class.
An ore class is defined like this:

```json
"oreclass:stickWood"
```
	
An ItemStack is defined as usual.

## Examples
The following is the input part of a shapeless recipe, _items_ is a list of RecipeInput:

```json
{
  "items": [
    "minecraft:stone@all",
    "oreclass:stickWood",
    {
      "item": "minecraft:obsidian",
      "metadata": 0
    }
  ]
}
```

# PotionEffect
A potion effect defines the effect itself and the duration and amplifier.

```json
{
	"id": "minecraft:hunger",
	"duration": 60,
	"amplifier" : 2,
	"showParticles": false
}
```

* __id__: This is a ResourceLocation defining what effect is being used.
* __duration__: The duration of the effect in ticks. The default value is 60 (3 seconds).
* __amplifier__: An amplifier for the effect. This increases the effect. The default value is 1.
* __showParticles__: Whether to show the effect particles. The default value is true.

# BlockState
A block state defines a block and its properties.

```json
{
	"block": "minecraft:log",
	"properties": {
		"variant": "spruce",
		"axis": "z"
	}
}
```
```json
{
	"block": "minecraft:log",
	"properties": "variant=spruce,axis=z"
}
```

* __block__: This is a ResourceLocation defining the block.
* __properties__: This defines the properties and is optional.

# Color
There are two ways to define a color: using a hex code and using the name of the color.

```json
"ff0000"

"red"
```

The following color names are available: black, white, red, lime, blue, yellow, aqua, magenta, silver, gray, maroon, olive, green, purple, teal, navy, foliagePine, foliageBirch, foliageBasic

# ItemFilter
An ItemFilter is used to filter item stacks, for example for shift-click rules in container GUIs.

There are multiple ways to specify a filter:

```json
"machineInput:recipe_list"
```
This one accepts all stacks that are a part of the input of a machine recipe from the `recipe_list` list.

```json
"machineFuel:fuel_list"
```
This one accepts all stacks that are a part of the fuel for a machine from the `fuel_list` list.

```json
"ore:stickWood"
```
This one accepts all stacks that are registered for the `stickWood` ore class.

```json
{
	"item": "minecraft:dye",
	"metadata": 5
}

"minecraft:dye@5"
```
Both accept only the dye with metadata 5.

```json
["ore:stickWood", "minecraft:apple"]
```
This one accepts all stacks that are in the `stickWood` ore class or is an apple.

# FluidStack
A FluidStack defines a fluid and an amount of that fluid. If no amount is specified 1000 is used.

```json
"water"
```

```json
"water@500"
```
Uses 500 for the amount.

```json
{
    "fluid": "water@500"
}
```
Uses 500 for the amount.

```json
{
    "fluid": "water",
    "amount": 200
}
```
Uses 200 for the amount.

# BoundingBox
A BoundingBox defines a box shape in 3d space.

```json
{
    "from": [0, 0, 0],
    "to": [1, 1, 1]
}
```
A bounding box for a full cube. The elements in the lists are in the order xyz.

```json
{
    "cube": 1
}
```
Using cube will use `[0, 0, 0]` for the from part and the specified value for all elements of the to part. So this also defines a full cube.

```json
{
    "from": [0, 0, 0],
    "to": [0.8, 0.8, 0.8],
    "offset": [0.1, 0.1, 0.1]
}
```
The values defined in the offset part are being added to both from and to.

```json
{
    "cube": 0.8,
    "offset": [0.1, 0.1, 0.1]
}
```
This defines the same bounding box as before but using cube instead.
…………………………………………………………………………………………………………………………………………………………………………………………………………
在这里你可以查看如何指定json中的具体参数。

资源路径（Resource Location）：用来指定材质，模型，和物品/方块标识符所在的路径。有两种方法可以指定资源路径：
短版：

```json
"minecraft:stone"
	
"minecraft:textures/gui/bars.png"（bar指的是按钮）
```
	
长版:

```json
{
  "domain" : "minecraft",
  "path" : "stone"
}

{
  "domain" : "minecraft",
  "path" : "textures/gui/bars.png"
}
```

NBT Compound是个含有NBT数据的字符串:

```json
"{display:{Name:\"Some Obsidian\"}}"
```

有多种方式指定一个物品堆栈（Item Stack）：

```json
{
  "item" : "minecraft:stone",
  "metadata"（附加值，例如52:10） : 10,
  "amount" : 42（物品堆叠数量）,
  "nbt" : "{display:{Name:\"Some Obsidian\"}}"
}
```

除了“item”选项，其他都是可选的，“metadata”默认是0.“amount”默认是1，对于某些合成你可能需要各种附加值的物品都通用（例如石头与花岗岩，闪长岩），可以这样做：

```json
{
  "item": "minecraft:stone",
  "metadata": "all",
  "amount": 42
}
```
或者像这样：
```json
{
  "item": "minecraft:stone@all",
  "amount": 42
}
```
	
这也有指定物品堆栈的一个简短版本，不过这只能指定物品和附加值：

```json
"minecraft:stone"
	
"minecraft:stone@1"
	
"minecraft:stone@all"
```
	
这会指定一个堆叠数量为1的物品。忽略附加值部分则会默认为0.

下面是一个熔炉合成，“input（输入）”和“result（输出，合成结果）”都是物品堆栈：

```json
{
  "input": "minecraft:stone@all",
  "result": {
    "item": "minecraft:obsidian",（黑曜石）
    "amount（数量）": 3,
    "nbt": "{display:{Name:\"Custom Obsidian\"}}"
  }
}
```

# BlockDrop
方块掉落（BlockDrop）几乎与物品堆栈相同，除了两个附加选项——你可以将掉落数量限定到一个范围内。在示例中，实际掉落数是介于1和3之间，含1和3：

```json
{
  "amount" : [1, 3]（闭区间概念）
}
```
你也可以添加一个“fortuneAmount（时运等级）”参数，掉落数量将会受时运等级加成。

```json
{
  "fortuneAmount" : 2
}
```

这一操作将会掉落至少2块泥土，如果你的工具有时运附魔，例如时运2，它将额外掉落2到4块泥土：
```json
{
  "item": "minecraft:dirt",
  "amount": 2,
  "fortuneAmount": [1, 2]
}
```

你可以像物品堆栈一样定义一个物品掉落：
```json
"minecraft:stone@1"
```
	
一个合成输入（Recipe Input）既是物品堆栈，也是矿物辞典类，矿辞类是这样描述的：

```json
"oreclass:stickWood"
```
	
物品堆栈就像一般那样定义。

下面的操作描述了一个无序合成的输入部分，“items”是合成输入的物品表:

```json
{
  "items": [
    "minecraft:stone@all",
    "oreclass:stickWood（符合木棍的矿辞）",
    {
      "item": "minecraft:obsidian",
      "metadata": 0
    }
  ]
}
```

药水效果（Potion Effect）决定了它自身的效果，持续时间和效力等级。

```json
{
	"id": "minecraft:hunger",（饥饿debuff）
	"duration": 60,（持续时间60tick）
	"amplifier" : 2,（2级药水）
	"showParticles（显示粒子效果）": false
}
```

* “id”: 一个资源路径，决定了使用什么药水效果。
* “duration”: 效果持续时间，默认时间为60tick，即三秒。
* “amplifier”: 药水效力等级，越大药水效果越强。默认值为1.
* “showParticles”：是否显示药水使用之后的效果，默认为true。

方块状态（Block State）定义了一个方块，和它的属性参数。

```json
{
	"block": "minecraft:log",（原木）
	"properties": {
		"variant（材质）": "spruce（云杉木）",
		"axis（坐标轴）": "z"
	}
}
```
```json
{
	"block": "minecraft:log",
	"properties": "variant=spruce,axis=z"
}
```

* “block”: 一个描述了方块的资源路径。
* “properties” ：决定了它的各项属性参数，可选。

有两种方式定义一种颜色：使用十六进制（hex）码定义，或者使用颜色的名字。

```json
"ff0000"

"red"
```

以下的颜色名直接可用: black, white, red, lime, blue, yellow, aqua, magenta, silver, gray, maroon, olive, green, purple, teal, navy, foliagePine, foliageBirch, foliageBasic（就是原版的16种颜色）。

物品过滤器用于过滤物品堆栈，例如在容器的GUI（界面）中shift单击之后的效果。
有多种方式指定一个过滤器：

```json
"machineInput:recipe_list"
```

这个示例接受“recipe_list”表单中，所有属于一个机器的合成输入的物品。
```json
"machineFuel:fuel_list"
```

这个示例接受“fuel_list”表单中，所有是一个机器燃料的物品。
```json
"ore:stickWood"
```
这个示例接受所有注册了“stickWood（木棍）”矿辞的物品。

```json
{
	"item": "minecraft:dye",
	"metadata": 5
}

"minecraft:dye@5"
```

这两个示例都只接受附加值为5的dye（染料）。

```json
["ore:stickWood", "minecraft:apple"]
```

这个示例接受木棍矿辞或者一个苹果。

一个流体堆栈（Fluid Stack）定义了一种流体，和该流体的数量，如果不定义数量，默认使用1000（mb，1000mb即为原版一桶）。
```json
"water"
```

```json
"water@500"
```
一次使用500mb水。

```json
{
    "fluid": "water@500"
}
```
使用500mb水。

```json
{
    "fluid": "water",
    "amount": 200
}
```
使用200mb水。

碰撞箱（Bounding Box）决定了碰撞箱在三维空间中的大小和形状。
```json
{
    "from": [0, 0, 0],
    "to": [1, 1, 1]
}
```
一个完整的正方体碰撞箱（的两个顶点，从起点到终点），[0,0,0]代表着x，y，z坐标都为0.

```json
{
    "cube": 1
}
```
可以直接使用cube（正方体）碰撞箱，“[0, 0, 0]”作为起点，“cube”即为其边长，也可以描述一个完整的立方体。

```json
{
    "from": [0, 0, 0],
    "to": [0.8, 0.8, 0.8],
    "offset": [0.1, 0.1, 0.1]
}
```
决定了碰撞箱的偏移量（offset），偏移量会被加到from和to的坐标上。
```json
{
    "cube": 0.8,
    "offset": [0.1, 0.1, 0.1]
}
```
描述了一个和先前相同的碰撞箱，但是用cube代替了。



