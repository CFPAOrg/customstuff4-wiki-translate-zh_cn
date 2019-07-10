# 机械和合成配方
类名: __jei:machineRecipe__, __jei:craftingRecipe__

这两个类为CS4添加了在JEI中对机器和合成配方列表的支持:

```json
{
  "recipeList": "cs4examplemod:machine",
  "gui": "cs4examplemod:machine",
  "tileEntity": "cs4examplemod:machine",
  "bgX": 37,
  "bgY": 16,
  "bgWidth": 126,
  "bgHeight": 54,
  "icon": "cs4examplemod:machine",
  "title": "Machine Recipes",
  "recipeAreaX": 80,
  "recipeAreaY": 35,
  "recipeAreaWidth": 22,
  "recipeAreaHeight": 15,
  "transferButtonX": 119,
  "transferButtonY": 57
}
```

* __recipeList__: 用于展示合成的合成配方列表.

* __gui__: 用于展示机械或合成台GUI的内部资源项.

* __tileEntity__: 用于展示机械或合成台的Tile Entity的内部资源项.

* __bgX__, __bgY__, __bgWidth__, __bgHeight__: 该属性定义了GUI中背景材质的哪一部分显示在JEI GUI中. 该部分应至少包含配方的所有重要的物品或流体槽.

* __icon__: 该属性定义了用于作为图标的物品.

* __title__: 为JEI GUI使用的标题.

* __recipeAreaX__, __recipeAreaY__, __recipeAreaWidth__, __recipeAreaHeight__: 这些配置项定义了在GUI中你可以点击以打开显示配方的JEI GUI的部分的大小尺寸.

* __transferButtonX__, __transferButtonY__: 若转移按钮(译者注: 即JEI中将物品转移到GUI内的按钮)的默认位置不太合适, 请使用这些配置项进行绝对定位.

# 物品描述
Type name: __jei:description__

这会在JEI GUI中创建一个描述页.

```json
{
  "items": ["cs4examplemod:crafter"],
  "desc": ["cs4examplemod.crafter.jei.desc"]
}
```

* __items__: 这是以ItemStack为成员的列表, 定义了要添加描述的物品.

* __desc__: 这是一个描述列表, 内部使用的是本地化名称, 其中每个条目都在一个新行上. 你可以在条目中使用  `\n` 来创建新行.