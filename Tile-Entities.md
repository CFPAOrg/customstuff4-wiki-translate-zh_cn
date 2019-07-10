# 实体标签(Tile Entities)
Tile Entities都具有这些属性:

```json
{
  "id": "mytileentity",
  "modules": [
    {
      "type": "inventory",
      "name": "inv1",
      "size": 27
    }
  ]
}
```

* __id__: Tile Entities的**唯一**ID. 用于给方块实例调用. 必须全部小写, 不得包含空格. ID只需要在你的模组中的命名空间中保持唯一性.

* __modules__: Tile Entities的模块列表. 就是这些模块使Tile Entities具有神奇的特殊用途.

# Tile Entity 模块
所有模块都具有这些属性:

```json
{
	"type": "inventory",
	"name": "inv1"
}
```

* __type__: 模块的类型. 根据模块的类型, TEM(Tile Entity Module)条目可以使用特殊的属性.
* __name__: 模块的名称. 在Tile Entities的命名空间里唯一就行. 这用于引用TEM, 例如在gui中引用该TEM条目.

## 物品槽
类名: __inventory__

该模块将简单的物品槽加入到Tile Entities中. 其具有以下附加参数:

```json
{
	"size": 27,
	"sides": ["up", "down", "east", "west"]
}
```

* __size__: 物品槽槽数的多少
* __sides__: 该属性定义了可以从哪些方位访问物品槽, 例如在方块下方(`bottom`)使用漏斗, 默认可以从任何方向上访问.

## 合成槽
类名: __crafting__

该模块为Tile Entities添加了合成功能. 其具有以下附加参数:

```json
{
	"rows": 2,
	"columns": 3,
	"recipeList": "mymod:myrecipelist"
}
```

* __rows__, __columns__: 合成区域的行数和列数. 可以是 `1` , `2` 或 `3` . 默认值为 `3` .
* __recipeList__: 该属性定义了可以使用的合成配方. 填入 `minecraft:vanilla` 以允许使用原版的所有合成配方. 默认值为 `minecraft:vanilla`.

该模块具有 `rows(行数) * columns(列数) + 1(输出槽)` 个物品槽. 输入槽从左到右, 从上到下进行编号.

## 机械(Machine)
类名: __machine__

该模块将类似机械的功能添加到Tile Entities, 熔炉就应用了这种技术. 其具有以下附加参数:

```json
{
  "inputSlots": 2,
  "outputSlots": 2,
  "fuelSlots": 2,
  "cookTime": 150,
  "recipeList": "mymod:machinerecipes",
  "fuelList": "mymod:machinefuel",
  "sidesInput": ["up"],
  "sidesOutput": ["down"],
  "sidesFuel": ["north", "south", "east", "west"],
  "inputTanks": ["input_tank"],
  "outputTanks": ["output_tank"]
}
```

* __inputSlots__: 该机械使用的输入槽的个数, 默认值为 `1`.
* __outputSlots__: 该机械使用的输出槽的个数, 默认值为 `1`.
* __fuelSlots__: 该机械使用的燃料槽的个数. 请注意, 两个槽意味着机器一次熔炼两个物品. 当该属性值为 `0` 时, 意味着该机器不需要使用燃料. 默认值为 `1`.
* __cookTime__: 完成配方并输出成品所需的游戏刻数. 如果配方有自己的 `cookTime`, 则使用配方所定义的 `cookTime`. 默认值为 `200`.
* __recipeList__: 该属性定义了机械可以使用的合成配方. 如果你想使用原版的熔炼配方, 请填入 `minecraft:vanilla`. 默认值为 `minecraft:vanilla`.
* __fuelList__: 该属性定义了机械可以使用的燃料. 如果你想使用原版的燃料, 请填入 `minecraft:vanilla`. 默认值为 `minecraft:vanilla`.
* __sidesInput__, __sidesOutput__, __sidesFuel__: 该属性定义了可以从哪些方位访问机械, 例如在方块下方(`bottom`)使用漏斗进行成品输出, 在上方(`top`)使用漏斗进行原材料输入, 而侧边(`north`, `south`, `east`, `west`)进行燃料补给. 默认值如上所示.
* __inputTanks__, __outputTanks__: 定义用于输入和输出使用流体的配方的储罐. 要引用的储罐必须是同一Tile Entities的模块. 可省略, 表示不需要.

插槽编号顺序如下：输入 -> 输出 -> 燃料. 总之就是从左到右从上到下.

## 储罐
类名: __tank__

该模块可为Tile Entities提供流体储罐的功能. 其具有以下附加参数:

```json
{
  "capacity": 10000,
  "canDrain": true,
  "canFill": true,
  "sides": ["north", "south", "east", "west", "up", "down"]
}
```

* __capacity__: 储罐的容量, 默认值为 `10000`.
* __canDrain__: 储罐是否可以排出液体, 默认值为 `true`.
* __canFill__: 储罐是否可以输入液体, 默认值为 `true`.
* __sides__: 该属性定义了可以从哪些方位访问储罐, 例如使用管道, 桶等, 默认可以从任何方向上访问.

# Simple
类名: __tileentity:simple__

该种Tile Entity没有任何特殊功能, 也没有任何可添加的附加参数.