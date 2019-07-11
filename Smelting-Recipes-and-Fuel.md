# 熔炼配方
类名: __smeltingRecipe__

```json
{
  "input": "minecraft:stone",
  "result": {
    "item": "minecraft:obsidian",
    "amount": 3
  },
  "xp": 2.7
}
```
	
* __input__: 定义一个物品堆, 用于表示配方的输入. 你可以使用 `all` 来接受该种物品的所有变种. 在此处指定 `nbt` 是没用的.

* __result__: 定义一个物品堆, 用于表示配方完成后所形成的产物.

* __xp__: 当产物被取出时, 给与玩家的经验数量. 该项可选, 默认为 `0`.

# 燃料

类名: __fuel__

```json
{
  "item" : "minecraft:stone",
  "burnTime" : 800
}
```
	
* __item__: 这是一个物品堆, 用于定义作为熔炉燃料的物品. 你可以使用 `all` 来接受该种物品的所有变种. 你可以在此处指定 `nbt` 来匹配具有特定属性的物品.

* __burnTime__: 能为熔炉熔炼物品, 提供燃料值的时间. 单位游戏刻(Tick). 每20游戏刻代表现实中的1秒.