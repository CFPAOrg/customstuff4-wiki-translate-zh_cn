## 原版工作台的合成配方

在Minecraft 1.12及以上版本的原版合成中, 我们使用json文件来定义每一个合成配方. 目前禁用了合成配方的删除. 要在合成配方内使用一个带有耐久值的物品, 你可以使用 `customstuff4:damageable_shaped` 和 `customstuff4:damageable_shapeless` 类的合成, [这里](https://github.com/cubex2/customstuff4/tree/master/examplemod/assets/cs4examplemod/recipes)有一个示例.

**注意**: 这仅适用于为原版合成台使用的**合成**配方. 其他任何地方, 包括冶炼配方, 都不要使用这种格式.

# 有序合成

类名: __`shapedRecipe`__

```json
{
  "shape": [
      "SS",
      "D "
    ],
  "items": {
    "S": "minecraft:sword_diamond@all",
    "D": "ore:blockDiamond"
  },
  "damage": {
    "S": 5
  },
  "result": {
    "item": "minecraft:obsidian",
    "amount": 3
  },
  "mirrored": false,
  "remove": false,
  "recipeList": "mymod:myrecipes"
}
```
	
* __shape__: 这是一个由字符串组成的列表. 第一条字符串就相当于合成配方中的第一行, 第二条就是第二行, 以此类推; 字符串中的每个字母都是一个物品. 每个字符串互相之间必须是相同的长度, 并且长度必须在1到3个字母之间, 但相对的, 这个列表中不能有超过3条字符串.

* __items__: 与同级参数 `shape` 一起构成了合成配方的输入. 这会将 `shape` 中使用的字母映射到配方输入中. 如果你希望配方中有空白点, 则不要为该字母定义物品. 你可以使用 `all` 来匹配该物品的所有子类型(metadata). 在这里为物品指定NBT是无效的.
* __damage__: 该参数为每个物品指定是否应该具有耐久值. 默认值为 `0`, 表示物品没有耐久值(满耐久).
* __result__: 用于定义配方的输出, 输出的应该是一个ItemStack(物品)

* __mirrored__: 用于定义配方镜像翻转后是否仍生效. 接受布尔值. 默认值为 `true`.
* __remove__: 如果该参数被设为 `true`, 则会删除与条目相同的合成, 且可以省略 `result` 或 `items` 和 `shape`. 这将删除与输入或结果匹配的所有配方. 默认值为 `false`.
* __recipeList__: 要添加或删除配方的列表.

# 无序合成

类名: __`shapelessRecipe`__

```json
{
  "items": [
    "minecraft:sword_diamond@all",
    "oreclass:stickWood"
  ],
  "damage": [5, 0],
  "result": {
    "item": "minecraft:obsidian",
    "amount": 3
  },
  "remove": false,
  "recipeList": "mymod:myrecipes"
}
```
	
* __items__: 这是配方输入的列表, 并定义了配方所需的物品. 你可以使用 `all` 来匹配该物品的所有子类型(metadata). 在这里为物品指定NBT是无效的.
* __damage__: 该参数为每个物品指定是否应该具有耐久值. 默认值为 `0`, 表示物品没有耐久值(满耐久). 你可以根本不为每个输入项定义此项.
* __result__: 用于定义配方的输出, 输出的应该是一个ItemStack(物品)
* __remove__: 如果该参数被设为 `true`, 则会删除与条目相同的合成, 且可以省略 `result` 或 `items` 和 `shape`. 这将删除与输入或结果匹配的所有配方. 默认值为 `false`.
* __recipeList__: 要添加或删除配方的列表.