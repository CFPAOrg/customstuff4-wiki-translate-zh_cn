This is a list of how to specify certain things in json. 

# 内部资源项(ResourceLocation)
一个内部资源项将用于调用内部的材质, 模型, 抑或是物品, 方块的唯一标识. 有两种方法可以定义一个内部资源项.

书写较为方便的版本:

```json
"minecraft:stone"
	
"minecraft:textures/gui/bars.png"
```
	
书写完整, 容易阅读的版本:

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

# NBT标签项(NBTTagCompound)
一个NBT标签项就像字符串一样, 用于表示游戏中一些隐藏的数据:

```json
"{display:{Name:\"Some Obsidian\"}}"
```
	
# 物品堆(ItemStack)
可使用多行的方式完整地表示一个物品堆:

```json
{
  "item" : "minecraft:stone",
  "metadata" : 10,
  "amount" : 42,
  "nbt" : "{display:{Name:\"Some Obsidian\"}}"
}
```

除 `item` 外, 其他所有内容都是可选的, `metadata` 默认为 `0` , 而用于表示数量的 `amount` 默认为 `1`.
对于某些配方, 你可能希望可以使用所有的子类型:

```json
{
  "item": "minecraft:stone",
  "metadata": "all",
  "amount": 42
}
```

或者这样做:
```json
{
  "item": "minecraft:stone@all",
  "amount": 42
}
```

还有一个定义物品堆的简短版本, 但是只能定义物品和元数据:

```json
"minecraft:stone"
	
"minecraft:stone@1"
	
"minecraft:stone@all"
```
	
这将定义一个数量为1的物品堆. 当 `metadata` 被省略时, 其值被设置为作为缺省值的 `0` .

## 示例
这是一个无序合成. `input` 和 `result` 都是物品堆:

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

# 方块掉落
BlockDrop几乎与ItemStack相同. 但有两处不同:
你可以将 `amount` 设置为一个区间. 在以下示例中, 物品掉落的实际数量将为 `1个到3个` .

```json
{
  "amount" : [1, 3]
}
```

你也可以添加一个 `fortuneAmount`(时运采掘系数) 属性. 该属性值将在被附有时运附魔的工具采掘时, 掉落 `${fortuneAmount * <时运附魔等级>}` 个物品.

```json
{
  "fortuneAmount" : 2
}
```

## 示例

.这个例子中, 该方块掉落将会掉落至少2个泥土. 如果被附有时运附魔的工具采掘下, 比如说当时运等级为2时, 它将会额外掉落2-4个泥土.
```json
{
  "item": "minecraft:dirt",
  "amount": 2,
  "fortuneAmount": [1, 2]
}
```

跟一个物品堆一样, 你也可以这样定义一个方块掉落:
```json
"minecraft:stone@1"
```
	
# 配方输入
一个配方输入支持使用物品堆和矿典.
一个矿典可以这样声明:

```json
"oreclass:stickWood"
```
	
就像物品堆一样, 和之前一样.

## 示例
下面是一个无序合成配方的配方输入部分, `items` 这个列表就是一个配方输入的列表:

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

# 药水效果
药水效果定义了效果本身以及持续时间和效果的倍率.

```json
{
	"id": "minecraft:hunger",
	"duration": 60,
	"amplifier" : 2,
	"showParticles": false
}
```

* __id__: 这是一个内部资源项, 用于定义正在使用的效果.
* __duration__: 药水效果持续的时间, 默认值为 `60`(3秒).
* __amplifier__: 药水效果的倍率. 使效果变得更加明显. 默认值为 `1`.
* __showParticles__: 是否发出效果粒子. 默认值为 `true`.

# 方块状态
方块状态定义方块及其属性.

下面两种表现方式等效.

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

* __block__: 这是一个内部资源项, 用于定义方块.
* __properties__: 可选, 用于定义属性.

# 颜色
可以用两种方式定义一种颜色: 1.使用16进制码 2.使用颜色名称.

```json
"ff0000"

"red"
```

以下是所有可用的颜色名称: black, white, red, lime, blue, yellow, aqua, magenta, silver, gray, maroon, olive, green, purple, teal, navy, foliagePine, foliageBirch, foliageBasic

# 物品过滤器(ItemFilter)
物品过滤器用于过滤物品堆, 举个例子, GUI的Shift-Click(快速分发)策略就可以使用该技术过滤物品.

构建物品过滤器有两种方法:

```json
"machineInput:recipe_list"
```

这个物品过滤器接受来自 `recipe_list` 这个配方列表的机器配方输入的所有物品堆.

```json
"machineFuel:fuel_list"
```

这个物品过滤器接受来自 `fuel_list` 这个燃料列表所配置的所有燃料.

```json
"ore:stickWood"
```
这个物品过滤器接受来自矿物词典 `stickWood` 的所有已注册的物品.

```json
{
	"item": "minecraft:dye",
	"metadata": 5
}

"minecraft:dye@5"
```

这两者等价, 都接受元数据值为 `5` 的物品 `minecraft:dye`.

```json
["ore:stickWood", "minecraft:apple"]
```

这个物品过滤器不仅接受来自矿物词典 `stickWood` 的所有已注册的物品, 还接受物品 `minecraft:apple`.

# 流体堆
一个流体堆明确了一种流体类型和数量. 数量可以省略, 默认为 `1000` .

```json
"water"
```

```json
"water@500"
```
将数字 `500` 作为该流体堆的数量.

```json
{
    "fluid": "water@500"
}
```
将数字 `500` 作为该流体堆的数量.

```json
{
    "fluid": "water",
    "amount": 200
}
```
将数字 `200` 作为该流体堆的数量.

# 限界框
限界框定义了在三维空间内的一个矩形盒状空间.

```json
{
    "from": [0, 0, 0],
    "to": [1, 1, 1]
}
```
这是一个由完整立方体构成的限界框. 列表中的元素按 `x -> y -> z` 的顺序排列.

```json
{
    "from" : [0, 0, 0],
    "to": [1, 1, 1]
}

{
    "cube": 1
}
```
上面两种书写方式等效, 可选项 `cube` 用 `[0,0,0]` 作为 `from` 部分, 而指定值将作为 `to` 部分的所有元素. 这种方式也定义了一个完整的立方体.

```json
{
    "from": [0.1, 0.2, 0.3],
    "to": [0.9, 1.0, 1.1]
}

{
    "from": [0, 0, 0],
    "to": [0.8, 0.8, 0.8],
    "offset": [0.1, 0.2, 0.3]
}
```

上面两种的表达方式等效.
`offset` 部分中定义的值将被添加到 `from` 和 `to` 所具有相对应的元素中.

```json
{
    "cube": 0.8,
    "offset": [0.1, 0.2, 0.3]
}
```

你也可以把 `cube` 和 `offset` 连用. 这种方式和上面那个也是等效的.