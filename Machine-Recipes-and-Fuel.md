# 机械合成
类名: __machineRecipe__

译者注: 如果你还没有接触过 `Modular Machinery`(模块化机器), 这里建议去阅读该mod的wiki, 其有说明更多关于如何添加机械合成的相关内容. 这里建议将输入物品多 但 与输入物品少的配方 具有部分相同输入内容的 配方的优先级提高, 这将避免更多的奇葩问题.

```json
{
  "input": [{"ore": "ingotGold", "amount": 4}, "minecraft:apple"],
  "output": [
    {
      "items": ["minecraft:gold_ingot", {"item": "minecraft:golden_apple", "chance": 0.25}],
      "fluids": ["water@500", "lava@500"],
      "weight": 1
    },
    {
      "items": ["minecraft:gold_ingot", {"item": "minecraft:golden_apple", "chance": 0.25}],
      "fluids": ["water@1000", "lava@1000"],
      "weight": 2
    }
  ],
  "inputFluid": ["water@500", "lava@500"],
  "outputFluid": ["examplefluid@1000"],
  "cookTime": 400,
  "recipeList": "mymod:machinerecipes"
}
```

* __input__: 用于定义配方输入的物品的列表.
* __output__: 用于定义配方输出物品和流体的列表. 该列表中的每个条目代表配方的一个**可能**结果. 如果配方的输出只是一个简单项, 可以将此属性直接设置为一个物品堆.
  * __items__: 用于定义配方条目结果的物品堆列表. 你可以为该列表中使用附加属性 `chance` , 这将使物品仅在有的时候出现, 设置为 `0.25` 表示将会有 25% 的机会使该物品出现.
  * __fluids__: 用于定义输出的液体, 使用液体堆列表表示.
  * __weight__: 如果配方有多个结果，则此属性用于使某些结果的出现比其他结果更具有可能性. 默认值为 `1`.
* __inputFluid__: 用于定义配方输入的液体.
* __cookTime__: 用于定义完成配方所需要花费的时间. 如果该值被设置为 `0`, 则会使用机器所定义的合成时间(the cookTime of the machine). 默认值为 `0` .
* __recipeList__: 该配方将被添加到的配方列表.

## 输出的更多示例

这只会输出一个金锭, 一直都会如此:
```json
{
  "output": "minecraft:gold_ingot"
}
```

这将输出一个金锭或一个铁锭:
```json
{
  "output": [
    "minecraft:gold_ingot",
    "minecraft:iron_ingot"
  ]
}
```

这将总会输出一个铁锭, 同时有 50% 的可能会额外输出一个金锭:
```json
{
  "output": [
    {
      "items": [
        "minecraft:iron_ingot",
        {"item": "minecraft:gold_ingot", "chance": 0.5}      
      ]
    }
  ]
}
```

这就总会输出一个金锭和一个铁锭:
```json
{
  "output": [
    {
      "items": ["minecraft:gold_ingot", "minecraft:iron_ingot"]
    }
  ]
}
```

输出的可能是一个金锭或一个铁锭，输出铁锭的可能性是输出另一者的两倍：
```json
{
  "output": [
    {
      "items": "minecraft:gold_ingot",
      "weight": 1
    },
    {
      "items": "minecraft:iron_ingot",
      "weight": 2
    }
  ]
}
```

# 机器燃料
类名: __machineFuel__

```json
{
  "items": ["ore:stickWood", "minecraft:coal"],
  "burnTime": 200,
  "fuelList": "mymod:machinefuel"
}
```

* __items__: 用于定义可以一起燃烧作为燃料的物品.(译者注: 因特殊原因, 译者无法考察该翻译是否准确, 本意无法确定是"可以一起燃烧起来(缺一不可)",还是"无论放入哪个都可以燃烧起来(两者皆可)", 故可能具有错误, 还请读者自己试验, 若产生相应结果请告知译者.)
* __burnTime__: 能使机器运转并生产的时间(单位:游戏刻(Tick))
* __fuelList__: 该燃料条目将加入的燃料列表.