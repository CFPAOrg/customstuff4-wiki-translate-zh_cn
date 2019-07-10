# 物品
所有类型的物品都使用这些属性:

```json
{
  "id" : "myitem",
  "model" : "mymod:myitemmodel",
  "creativeTab" : "tools",
  "information" : ["First line", "Second line"],
  "maxDamage": 9,
  "tint": "red",
  "burnTime": 100
}
```

* __id__: 该属性定义该方块的**唯一**ID. ID用于在配方中引用方块和于lang文件中进行国际化操作. ID必须全部小写, 且不得包含空格. ID只需要在你的模组中的命名空间中保持唯一性. 如果你的ModID是 `mymod` 且该物品的ID是 `myitem`, 你可以使用 `mymod:myitem` 引用该物品.

* __model__: 该属性定义了物品使用的模型文件. 在上面的示例中, 这个文件在路径 `assets/mymod/models/item/myitemmodel.json` 或路径 `assets/mymod/blockstates/myitemmodel.json` 下.你也可以使用来自另一个模组或Minecraft本身的模型. 支持子类型. 默认值为 `<modid>:<itemid>`.

* __creativeTab__: 该属性定义了该物品将会被添加到的创造模式标签页. 如果省略填写该属性, 则该物品不会出现在任何创造模式标签页内. 支持子类型. 你能在[这里](Creative-Tabs#vanilla-creative-tabs)找到一个Minecraft原版中已定义的所有可用创造模式标签页的列表.

* __information__: 该属性定义了在背包中物品名称下方的其他信息行. 支持子类型.

* __maxDamage__: 该属性定义了物品是否可以具有耐久值以及物品的最大耐久值. 如果使用此属性, 则无法为此物品使用子类型.

* __tint__: 该属性将为物品添加色调. 应填入一种颜色. 支持子类型.

* __burnTime__: 该属性定义了物品能让熔炉燃烧的时间长短(单位:Tick). 若将值设为 `-1` , 则会让熔炉系统自己决定. 支持子类型. 默认值为 `-1` .

# 子类型(Metadata Subtype)
有些物品类型支持子类型. 这意味着物品可以根据其 `元数据值`(Metadata) 具有不同的模型, 名称或其他内容. 举个例子, 染色就是一个例子: 每种颜色都是同一物品的子类型.  
如果一个物品类型支持子类型, 可以通过为物品条目填写 `subtypes` 属性来启用该特性:

```json
{
  "subtypes" : [ 0, 1, 5 ]
}
```

这将使物品条目具有元数据值分别为 `0` , `1` 和 `5` 的子类型. 你应该保留一个 `0` , 这表示了该方块的父类. 根据物品的类型, 最多可以使用16种子类型( `0` 到 `15` ).

你现在可以为每个支持该特性的属性提供一个HashMap, 使各个子类的属性都不相同, 前提是该属性支持它:

```json
{
  "model" : {
    "0" : "mymod:myitem_0",
    "1" : "mymod:myitem_1",
    "5" : "mymod:myitem_5"
  }
}
```

你仍然可以像这样定义属性:

```json
{
  "model" : "mymod:myitem"
}
```

这将为所有子类型设置**相同**的值.

# 语言文件(Lang File)
语言文件通常位于 `assets/themodid/lang` 路径下.

没有子类型的方块的Lang文件条目如下所示:

```
tile.themodid.theitemid.name=The Localized Name
```

如果方块具有多个子类型:

```
tile.themodid.theitemid.0.name=Subtype 0
tile.themodid.theitemid.1.name=Subtype 1
tile.themodid.theitemid.5.name=Subtype 5
```

# 简单(Simple)
类名: __item:simple__

这样的物品没有任何特殊的作用, 就像木棍或者煤. 支持子类型.

```json
{
  "maxStack" : 32,
  "gui" : "mymod:mygui",
  "modules": [
    {
      "type": "inventory",
      "name": "inv1",
      "size": 27
    }
  ]
}
```

* __maxStack__: 该属性定义了该物品的最大堆叠数. 该属性必须是在数字 `1` 和 `64` 之间的数. 支持子类型. 默认值为 `64`.
* __gui__: 该内部资源项(ResourceLocation)用于定义当玩家右键使用该物品时呈现的GUI的内部资源项. 请配合 `GUI ID` 和modid使用. 支持子类型. 默认没有GUI(省略).
* __modules__: 这是一个物品模块的列表. 这些模块可以为物品添加特殊的功能.

## 物品模块
所有模块都具有这些属性:

```json
{
  "type": "inventory",
  "name": "inv1"
}
```

* __type__: 模块的类型. 根据模块的类型, 特殊的属性将会被添加到物品上.
* __name__: 模块的名称. 在同一物品的模块列表的命名空间里唯一就行. 这用于外部调用模块, 例如在gui中引用该模块条目.

### 物品槽
类名: __inventory__

该模块将简单的物品槽加入到物品当中. 其具有以下附加参数:

```json
{
  "size": 27
}
```

* __size__: 物品槽槽数的多少

# 斧, 镐, 铲, 剑
类名: __item:axe__, __item:pickaxe__, __item:shovel__, __item:sword__

这些物品就像原版中的四幻神一样. 这些模块不支持子类型. 他们都有这些相同的附加参数.

```json
{
  "material" : "iron",
  "damage" : 3.5,
  "attackSpeed" : 4.7,
  "durability" : 750
}
```

* __material__: 该属性决定了工具的材料, 材料决定了工具的采矿速度, 耐久, 伤害和攻击速度. 原版中可以使用的材料有: `wood`(木), `stone`(石), `iron`(铁), `diamond`(钻石), `gold`(金).
* __damage__: 该属性决定了工具能对实体造成的伤害. 如果省略该属性, 则会使用材料所设定的伤害.
* __attackSpeed__: 该属性决定了工具的攻击速度. 如果省略该属性, 则会使用材料所设定的攻击速度.
* __durability__: 该属性决定了工具的耐久值. 如果省略该属性, 则会使用材料所设定的耐久值.

# 食物
类名: __item:food__

"物"如其名, 此类物品用于填满你的饱食度. It 支持子类型.

```json
{
  "maxStack" : 32,
  "healAmount": 4,
  "saturation" : 1.2,
  "alwaysEdible": true,
  "potionEffect" : {
    "id" : "minecraft:speed",
    "duration" : 120
  },
  "potionEffectProbability" : 0.5,
  "isWolfFood" : false,
  "result": "minecraft:glass_bottle",
  "useAction": "eat"
}
```

* __maxStack__: 该属性定义了该物品的最大堆叠数. 该属性必须是在数字 `1` 和 `64` 之间的数. 支持子类型. 默认值为 `64`.
* __healAmount__: 该属性定义了该物品能够为玩家所提供的饱食度的多少. 支持子类型. 默认值为 `2`.
* __saturation__: 该属性定义了该物品能够为玩家所提供的饱和度的多少. 默认值为 `0.6`. 支持子类型.
* __alwaysEdible__: 该属性定义了当玩家的饱食度饱和时还是否能够以该物品为食物吃下. 默认值为 `false`. 支持子类型.
* __potionEffect__: 该属性定义了当玩家吃下该物品时给与玩家的药水效果. 省略则不会有任何药水效果会被给与玩家. 支持子类型.
* __potionEffectProbability__: 该属性定义了当玩家吃下该物品时给与玩家药水效果的概率. `0.5` 表示50%会给与, `1.0` 则是一定会. 默认值为 `1.0`. 支持子类型.
* __isWolfFood__: 该属性定义了是否能将该物品作为食物饲喂给狼. 默认值为 `false`.
* __result__: 该属性值应是一ItemStack(使用唯一id调用), 如果定义该值, 则会使玩家吃下该食物时返还给玩家该属性值所表示的物品. 支持子类型.
* __useAction__: 该属性值定义了玩家是否使用喝而不是吃的方式食用该物品. 支持子类型.

# 流体容器
类名: __item:fluidContainer__

这将创建一可以容纳所有流体的流体容器物品. 其不支持子类型. 具有一个附加属性:

```json
{
  "capacity" : 1000
}
```

* __capacity__: 所定义流体容器的容量. 默认值为 `1000`.

要让使用动态的流体材质的模型正确显示, 请将以下模型文件内容放入方块模型文件内:

```json
{
  "forge_marker": 1,
  "variants": {
    "inventory": {
      "model": "forge:forgebucket",
      "textures": {
        "base": "cs4examplemod:items/fluid_container_base",
        "fluid": "cs4examplemod:items/fluid_container_fluid",
        "cover": "cs4examplemod:items/fluid_container_cover"
      },
      "transform": "forge:default-item",
      "custom": {
        "fluid": "water",
        "flipGas": true
      }
    }
  }
}
```

你只需要修改材质。 这个模型有3个图层: `base`, `fluid`, `cover`. `base` 是材质的背景. `fluid` 是只由白色构成的材质, 其中白色部分被盛装的流体材质替换. `cover` 是覆盖在 `base` 和 `fluid` 上的材质.

# 剪刀
类名: __item:shears__

该物品类会创建一个像原版剪刀一样的物品. 该物品类不支持子类型. 其具有一个附加参数:

```json
{
  "durability" : 750
}
```

* __durability__: 剪刀的耐久, 默认值为 `238` (即原版剪刀的耐久).

# 种子
类名: __item:seeds__

这将创建一个可以将作物放在土壤上的物品. 该物品类不支持子类型. 其具有一个附加参数:

```json
{
  "plant" : {"block": "cs4examplemod:crops"}
}
```

* __plant__: 这是一个 `BlockStats`(方块状态), 用于指定种子的作物的方块形态.

# 头盔, 胸甲, 护膝, 靴子
类名: __item:helmet__, __item:chest__, __item:legs__, __item:boots__

该物品类允许你创建自定义装甲. 该物品类不支持子类型, 且具有两个附加参数:

```json
{
  "material": "iron",
  "armorTexture": "minecraft:textures/models/armor/gold_layer_1.png"
}
```

* __material__: 该属性定义装甲的材料, 材料定义了材质, 耐久, 减伤系数, 可附魔性, 韧性和装备声音. 该项可以填入 `leather`, `chain`, `iron`, `gold`, `diamond` 或是自定义的装甲材料(see [[Armor Materials]]). 默认值为 `leather`.
* __armorTexture__: 如果指定该属性, 则使用该属性覆盖材料提供的装甲材质.