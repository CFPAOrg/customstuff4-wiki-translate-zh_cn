# 方块条目所具有的所有属性
所有类型的方块都使用这些属性:

```json
{
    "id" : "myblock",
    "material" : "ground",
    "itemModel" : "mymod:myitemmodel",
    "creativeTab" : "redstone",
    "hardness" : 2.5,
    "resistance" : 5.5,
    "soundType" : "metal",
    "maxStack" : 16,
    "opacity" : 128,
    "light" : 7,
    "flammability" : 50,
    "fireSpreadSpeed" : 10,
    "isFireSource" : false,
    "isWood" : false,
    "canSustainLeaves" : false,
    "isBeaconBase" : false,
    "enchantPowerBonus" : 1.5,
    "expDrop" : [0, 1],
    "information" : [ "第一行", "第二行"],
    "tileEntity": "mymod:mytileentity",
    "gui": "mymod:mygui",
    "drop": ["minecraft:dirt", {"item" : "minecraft:stone", "amount": [1,4] } ],
    "isFullCube": false,
    "isOpaqueCube": false,
    "isBurning": false,
    "bounds": { "cube": 0.5, "offset": [0.25, 0.25, 0.25] },
    "slectionBounds": { "cube": 1 },
    "collisionBounds": { "cube": 0.5, "offset": [0.25, 0.25, 0.25] },
    "tint": "foliage",
    "itemTint": "foliageBasic",
    "renderLayer": "solid",
    "canSilkHarvest": false,
    "harvestTool": "axe",
    "harvestLevel": 3,
    "canPlaceOnCeiling": true,
    "canPlaceOnFloor": true,
    "canPlaceOnSides": true,
    "sustainedPlants": "Crop",
    "burnTime": 100,
    "slipperiness": 0.6,
    "pathNodeType": "blocked",
    "isWeb": true
}
```

* __id__: 该属性定义该方块的**唯一**ID. ID用于在配方中引用方块和于lang文件中进行国际化操作. ID必须全部小写, 且不得包含空格. ID只需要在你的模组中的命名空间中保持唯一性. 如果你的ModID是 `mymod` 且该方块的ID是 `myblock`, 你可以使用 `mymod:myblock` 引用该方块, 而*方块状态*文件在路径 `assets/mymod/blockstates/myblock.json` 下. 如果该方块具有很多与其相关联的物品, 则该物品也具有相同的ID.(译者注: 该处作者可能是想表述出 `metadata` 的概念, 如果你想了解更多, 可以去wiki上查找.)

* __material__: 该属性定义该方块的材质. 材料定义了方块的很多属性, 例如其是否是半透明的, 又是否需要相对应的工具才能采掘. 该属性的默认值是 `ground`. 你能在[这里](Block-Materials)找到一个Minecraft原版中已定义的所有可用方块材质的列表.

* __itemModel__: 该属性定义了用于方块物品的模型文件. 在上面的示例中, 该模型文件的位置在 `assets/mymod/models/item/myitemmodel.json` 或 `assets/mymod/blockstates/myitemmodel.json`. 你也可以使用来自另一个模组或Minecraft本身的模型. 支持子类型. 该属性的默认值为 `modid:blockid`. 

* __creativeTab__: 该属性定义了该方块将会被添加到的创造模式标签页. 如果省略填写该属性, 则该方块不会出现在任何创造模式标签页内. 支持子类型. 你能在[这里](Creative-Tabs#vanilla-creative-tabs)找到一个Minecraft原版中已定义的所有可用创造模式标签页的列表.

* __hardness__: 该属性定义了采掘该方块所花费的时间. 支持子类型. 默认值为 `1.0`.

* __resistance__: 该属性定义了该方块的爆炸抗性. 支持子类型. 默认值为 `0.0`.

* __soundType__: 该属性定义了当行走在该方块上时, 打破该方块时和放置该方块时游戏所播放的声音. 支持子类型. 默认值为`stone`. 你能在[这里](Block-Sound-Types)找到一个Minecraft原版中已定义的所有可用创造模式标签页的列表.

* __maxStack__: 该属性定义了该方块的最大堆叠数. 该属性必须是在数字 `1` 和 `64` 之间的数. 支持子类型. 默认值为 `64`.

* __opacity__: 该属性定义了该方块的透明度. 该属性必须是在数字 `0` 和 `255` 之间的数. `0` 表示任何光线都能通过(玻璃般的透明度), `255` 则相反. 支持子类型. 默认值为 `255`(完全不透明).

* __light__: 该属性定义了该方块发光的亮度. 该属性必须是在数字 `0` 和 `15` 之间的数, 其中 `0` 表示不发光, `15` 表示尽可能多地发光. 支持子类型. 默认值为 `0`(不发光).

* __flammability__: 该属性定义了于该方块上火焰蔓延的可能性.  该属性必须是在数字 `0` 和 `100` 之间的数, `0` 表示火焰不可能在该方块上燃烧(0%), 而 `100` 则表示火焰一定会在该方块上蔓延(100%). 支持子类型. 默认值为 `0`(火焰不可能在该方块上燃烧).

* __fireSpreadSpeed__: 该属性定义了于该方块上火焰蔓延的速度. 设置的越高, 火焰蔓延的速度越快. 支持子类型. 默认值为 `0`(火焰在该方块上蔓延的速度为0).

* __isFireSource__: 该属性定义了于该方块上火焰是否会永远地燃烧. 支持子类型. 默认值为`false`(不会在该方块上永远燃烧).

* __isWood__: 该属性定义了方块是否是木头(`Wood`). 支持子类型. 默认值为`false`.

* __canSustainLeaves__: 该属性定义了叶子在该方块附近是否会消失. 支持子类型. 默认值为`false`.

* __isBeaconBase__: 该属性定义了该方块是否能够作为信标的基座材料. 支持子类型. 默认值为`false`.

* __enchantPowerBonus__: 该属性定义了该方块可提升附魔台的附魔等级的多少. 支持子类型. 默认值为`0.0`.

* __expDrop__: 该属性定义了当采掘下该方块时掉落的经验. 可以这样定义: `5` 也可以这样: `[1, 5]`. 当你采掘下第一个方块后,他会掉落5经验,第二个则会在数字 `1` 和 `5` 之间随机抽取出一个值掉落经验. 支持子类型. 默认值为`0`.

* __information__: 该属性定义了该方块在查看其信息时所显示的附加字段. 支持子类型.

* __tileEntity__: 该内部资源项(ResourceLocation)用于定义方块使用的TileEntity的内部资源项. 请配合TileEntityID和modid使用. 支持子类型. 默认没有.

* __gui__: 该内部资源项(ResourceLocation)用于定义当玩家右键方块时呈现的GUI的内部资源项. 请配合`GUI ID`和modid使用. 支持子类型. 默认没有GUI.

* __drop__: 该属性定义了一个或多个的方块掉落物. 要使方块不掉落任何物品, 请填写 `minecraft:air`. 如果省略配置该项, 该方块将只掉落其本身. 支持子类型.

* __isFullCube__: 该属性定义该方块是否为一个完整的块. 如果为`false`, 将呈现相邻方块的连接侧. 支持子类型.

* __isOpaqueCube__: 该属性定义该方块是否不透明. 如果该方块不是完整的方块或具有透明材质, 则应将其设置为false. 支持子类型.

* __isBurning__: 该属性定义实体是否应在与该方块接触时燃烧起来. 请注意, 碰撞箱需要略小于完整立方体才能使其生效. 支持子类型.

* __bounds__: 该属性定义该方块是否会在获得鼠标焦点时显示出选择箱边沿. 如果未指定, 则还需设置选择和碰撞箱. 支持子类型.

* __selectionBounds__: 该属性定义该方块是否会在获得鼠标焦点时突出显示选择箱的线框. 支持子类型.

* __collisionBounds__: 该属性定义该方块的碰撞箱. 支持子类型.

* __tint__: 该属性定义应用于世界中的该方块的色调. 要么是一种颜色, 要么是叶子/草/水中的颜色, 这将根据生物群系对方块进行着色. 支持子类型.

* __itemTint__: 该属性定义与该方块关联的物品的色调. 须填写的是一种颜色. 支持子类型.

* __renderLayer__: 该属性定义了该方块的渲染层, 并且取决于该方块的材质. 如果材质没有透明部分,请使用 `solid` 或省略它, 否则可以使用 `cutout` 或 `mippedCutout` , 后者将使材质变得具有立体感. 如果材质具有半透明部分, 请使用 `translucent` .

* __canSilkHarvest__: 该属性定义了该方块是否能被精准采集附魔完整地采掘. 默认值为`true`. 支持子类型.

* __harvestTool__, __harvestLevel__: 该属性定义了能够有效采掘下该方块的工具和等级. 请注意,如果该方块的材料(`material`)是 `iron` 或 `rock`, 其将始终可以通过镐采掘. 支持子类型.

* __sustainedPlants__: 该属性定义了能种植在该方块上的植物类型. 你可以使用以下的其中一个或多个: `Plains`(草原植被), `Desert`(沙漠植被), `Beach`(需种植在水边), `Cave`(洞穴植被), `Water`(水底植被), `Nether`(地狱植被), `Crop`(农作物). 支持子类型.

* __canPlaceOnFloor__, __canPlaceOnCeiling__, __canPlaceOnSides__: 该属性定义了通过单击另一个方块的顶部, 底部或侧边来判断该方块是否可以放置到世界中的名单

* __burnTime__: 该属性定义了该方块能为熔炉所燃烧的持续时间的长度. 若设置为 `-1`, 且该方块的材料为`wood`(木) ,则会让熔炉系统自动判断该属性值. 支持子类型. 默认值为 `-1` .

* __slipperiness__: 该属性定义了在该方块顶部移动时保持多少速度. 支持子类型. 默认值为 `0.6` .

* __pathNodeType__: 该属性定义了该方块在怪物的寻路AI中所在的地位. 以下是一系列有效值: `blocked`, `open`, `walkable`, `trapdoor`, `fence`, `lava`, `water`, `rail`, `dangerFire`, `damageFire`, `dangerCactus`, `damageCactus`, `dangerOther`, `damageOther`, `doorOpen`, `doorWoodClosed`, `doorIronClosed`. 若省略, 将使用该方块的默认值. 支持子类型.

* __isWeb__: 如果设置该属性为 `true` , 则该方块将使该方块内的实体的移动速度非常慢, 就像一般的蜘蛛网一样. 支持子类型. 默认值为 `false`.

# 子类型(Metadata Subtype)
有些方块类型支持子类型. 这意味着方块可以根据其 `元数据值`(Metadata) 具有不同的模型, 名称或其他内容.  
如果一个方块类型支持子类型, 可以通过为方块条目填写 `_subtypes_` 属性来启用该特性:

```json
{
    "subtypes" : [ 0, 1, 5 ]
}
```
这将使项目具有元数据值分别为 `0` , `1` 和 `5` 的子类型. 你应该保留一个 `0` , 这表示了该方块的父类. 根据方块的类型, 最多可以使用16种子类型( `0` 到 `15` ).

您现在可以为每个支持该特性的属性提供一个HashMap, 使各个子类的属性都不相同, 前提是该属性支持它:

```json
{
    "itemModel" : {
        "0" : "mymod:myitem_0",
        "1" : "mymod:myitem_1",
        "5" : "mymod:myitem_5"
    }
}
```

你仍然可以像这样定义属性:

```json
{
    "itemModel" : "mymod:myitem"
}
```

这将为所有子类型设置**相同**的值.

# 语言文件(Lang File)
语言文件通常位于 `assets/themodid/lang` 路径下.

没有子类型的方块的Lang文件条目如下所示:

```
tile.themodid.theblockid.name=The Localized Name
```

如果方块具有多个子类型:

```
tile.themodid.theblockid.0.name=Subtype 0
tile.themodid.theblockid.1.name=Subtype 1
tile.themodid.theblockid.5.name=Subtype 5
```

# 方块状态(Block States)
方块状态(`Block States`)文件将根据方块的状态定义为其所使用的模型. 例如子类型就是方块状态的一种. 使用子类型的方块的简单的方块状态文件可能如下所示:

```json
{
  "variants": {
    "subtype=subtype0": {"model": "firstpack:sensor_iron"},
    "subtype=subtype1": {"model": "firstpack:sensor_gold"}
  }
}
```

有关方块状态的更多信息, 你可以在[此处](http://minecraft.gamepedia.com/Model#Block_states)查看.

# 简单(Simple)
类名: __`block:simple`__

这个方块没有特殊的功能, 就像 `stone`(石头) 或 `dirt`(泥土). 这种方块类型支持全部的16种子类型. 这个方块没有其他附加的属性了.

其所具有的方块状态(`Block States`): 子类型(`subtype`).

# 可转向(Orientable)
有3种不同的可转向的方块: 垂直转向性(`vertical`), 水平转向性(`horizontal`), 全转向性(`directional`). 它们都有一个附加参数:

```json
{
  "faceBySide" : true
}
```

* __faceBySide__: 该属性定义了方块的面向是否应该由被点击的侧面的方向而不是玩家正在看的位置的方向来确定. 如果该块不能面向被点击侧的方向, 则仍然面向玩家正在看的方向. 支持子类型. 默认值为 `false`.

### 垂直转向性(Vertical)
类名: __`block:orientable:vertical`__

这个方块正面只能朝上或朝下, 它只支持从 `0` 到 `7` 的子类型(共计8个).

其所具有的方块状态(`Block States`): `facing`(朝向的方向) 和 `subtype`(子类型). 前者只能为 `up` 或 `down`.

### 水平转向性(Horizontal)
类名: __`block:orientable:horizontal`__

这个方块正面只能朝向东(`east`), 南(`south`), 西(`west`), 北(`north`) 四个方向, 它只支持从 `0` 到 `3` 的子类型(共计4个).

其所具有的方块状态(`Block States`): `facing`(朝向的方向) 和 `subtype`(子类型). 前者可以是下面几个中的任意一个: `north` , `south` , `east` , `west`.

### 全转向性(Directional)
类名: __`block:orientable:directional`__

这个方块的正面能朝向任何一个方向, 它只支持从 `0` 到 `1` 的子类型(共计2个).

其所具有的方块状态(`Block States`): `facing`(朝向的方向) 和 `subtype`(子类型). 前者可以是下面几个中的任意一个: `up` , `down` , `north` , `south` , `east` , `west`.

# 栅栏(Fence)
类名: __`block:fence`__

该子类定义了一个类似栅栏的方块模型. 其支持全部的16种子类型. 这个方块没有其他附加的属性了.

其所具有的方块状态(`Block States`): `subtype`(子类型).

# Stairs(楼梯)
类名: __`block:stairs`__

该子类定义了一个类似楼梯的方块模型. 它**不支持**子类型, 但它有一个附加属性:

```json
{
  "modelState": {
    "block": "minecraft:log",
    "properties": {
      "variant": "spruce"
    }
  }
}
```

* __modelState__: 这是一个`BlockState`(方块状态)，用于定义此楼梯的原材料方块. 此状态将定义楼梯的某些属性, 例如 `material`(材料).

其所具有的方块状态(`Block States`): `facing`, `half` , `shape`.  
`Facing` : [`north`, `south`, `east` , `west`]  
`Half`   : [`bottom` , `top`]  
`Shape`  : [`straight`, `outer_right`, `outer_left`, `inner_right` , `inner_left`]

# Slab(半砖)
类名: __`block:slab`__

该子类定义了一个类似半砖的方块模型. 它只支持从 `0` 到 `7` 的子类型(共计8个). 它有一个附加属性:

```json
{
  "doubleSlab" : {
      "block": "minecraft:log",
      "properties": "variant=spruce"
  }
}
```

* __doubleSlab__: 这是一个 `BlockState`(方块状态) , 用于定义两个半砖的组合. 支持子类型. 如果省略, 则不能将其组合起来.

其所具有的方块状态(`Block States`): `subtype` , `half`  
`Half` : [`top` , `bottom`]

# Fluid(流体)
类名: __`block:fluid`__

该子类定义了一个类似流体的方块模型. 方块的id也将是流体的id(没有mod前缀), 因此不要使用像 `water` 或 `lava` 那样的**已被占用**的id. 其不支持子类型. 其所具有的附加属性参见下方:

```json
{
  "density": 1000,
  "temperature": 300,
  "viscosity": 1000,
  "flowLength": 8,
  "isGaseous": false,
  "canCreateSource":  false,
  "addUniversalBucket": true,
  "texStill": "cs4examplemod:blocks/fluid_still",
  "texFlowing": "cs4examplemod:blocks/fluid_flow"
}
```

* __density__: 该属性定义该流体的密度. 负密度表示流体比空气轻(会浮起来). 默认值为 `1000`.
* __temperature__: 该属性定义该流体的温度(单位开尔文(K)). 默认值为 `300`.
* __viscosity__: 该属性定义该流体的粘度(厚度). 该属性值越高, 意味着流体流动的越慢, 反之亦然. 默认值为 `1000`.
* __flowLength__: 该属性定义该流体能流动的距离的长短. 该属性必须是在数字 `0` 和 `15` 之间的数. 默认值为 `8`.
* __isGaseous__: 该属性定义该流体是否以气体形式存在于世界上. 默认值为 `false`.
* __canCreateSource__: 该属性定义两个以该流体作为水源的水源方块是否可以创建另一个水源方块, 这种特性类似于水(译者注: 就是无限水.). 默认值为 `false`.
* __addUniversalBucket__: 该属性定义该流体是否可以使用Forge API提供的通用水桶盛装. 默认值为 `true`.
* __texStill__, __texFlowing__: 该属性定义该流体在流动状态和静止状态下所呈现的材质.

该流体的方块状态(`Blockstats`)文件应如下所示(将 `examplefluid` 替换为你所创建的流体的id):

```json
{
    "forge_marker": 1,
    "defaults": {
        "model": "forge:fluid",
        "custom": { "fluid": "examplefluid" }
    },
    "variants": {
        "level": {
            "0": {"model": "forge:fluid"},
            "1": {"model": "forge:fluid"},
            "2": {"model": "forge:fluid"},
            "3": {"model": "forge:fluid"},
            "4": {"model": "forge:fluid"},
            "5": {"model": "forge:fluid"},
            "6": {"model": "forge:fluid"},
            "7": {"model": "forge:fluid"},
            "8": {"model": "forge:fluid"},
            "9": {"model": "forge:fluid"},
            "10": {"model": "forge:fluid"},
            "11": {"model": "forge:fluid"},
            "12": {"model": "forge:fluid"},
            "13": {"model": "forge:fluid"},
            "14": {"model": "forge:fluid"},
            "15": {"model": "forge:fluid"}
        }
    }
}
```

# Carpet(地毯)
类名: __`block:carpet`__

该子类定义了一个类似地毯的方块模型. 其支持全部的16种子类型. 这个方块没有其他附加的属性了.

其所具有的方块状态(`Block States`): subtype.

# Snow(雪和雪块)
类名: __`block:snow`__

该子类定义了一个类似雪的方块模型. 该子类**不支持**子类型. 其具有以下附加属性:

```json
{
  "snowball": "minecraft:snowball",
  "maxLight": 15
}
```

* __snowball__: 若该属性被明确定义为一可用物品ID, 则会在堆叠该方块时剔除相对应数量的该物品.(在现有基础上堆叠一层剔除一个).
* __maxLight__: 如果该方块的亮度高于该属性值, 则会使其消失. 将该属性值设置为 `15` 就不会让其消失. 默认值为 `11` .

其所具有的方块状态(`Block States`): `layers`(层数), 该属性必须是在数字 `0` 和 `8` 之间的数, 也包括 `0` 和 `8`

# Crops
类名: __`block:crops`__

该子类定义了一个类似胡萝卜或者马铃薯这样的作物的方块模型. 该子类不支持子类型. 其具有以下附加属性:

```json
{
  "maxAge": 3,
  "growthFactor": 1.5,
  "heights": [0.1, 0.3, 0.6, 1.0],
  "seeds": "cs4examplemod:seeds",
  "crops": "minecraft:carrot"
}
```

* __maxAge__: 该属性定义了该方块所具有的最多的阶段数量. 将该属性设置为 `0` 就意味着他只有一个阶段. 该属性值的最大值为 `15`. 默认值为 `7`.
* __growthFactor__: 该属性定义了该种作物的生长速度. 将其设置为 `1.0` 则是与常规作物相同的速度一样生长, `2.0` 则会以两倍于常规作物的速度生长, 而 `0.5` 则会以常规作物的生长速度的一半生长. 该属性值应比 `0.0` 更大. 默认值为 `1.0`.
* __heights__: 该属性定义了该种作物每个阶段所达到的高度. 如果省略, 作物的高度将线性递增至 `1.0`, 具体取决于 `maxAge`. 举例说明, 如果 `maxAge` 为 `3`, 则该属性值可以是 `[0.25, 0.5, 0.75, 1.0]`.
* __seeds__: 该属性定义了采掘作为作物的该方块时将掉落的种子. 如果该作物在其最后阶段被收获, 它将像常规作物一样掉落多个种子.
* __crops__: 该属性定义了该作物在其最后阶段被收获时将掉落的作物收成品.

其所具有的方块状态(`Block States`): `age`: 他表示了包括 `0` 和作物最大阶段数(`maxAge`)的作物所处在的阶段.

# Fence Gate(栅栏门)
类名: __`block:fenceGate`__

该子类定义了一个类似栅栏门的方块模型. 该子类**不支持**子类型. 其具有以下附加属性:

```json
{
  "opensWithRedstone": true,
  "openWithHands": true
}
```

* __opensWithRedstone__: 该属性定义了是否可以应用红石信号来打开或关闭栅栏门. 默认值为 `true`.
* __opensWithHands__: 该属性定义了玩家是否可以使用右键单击来打开或关闭栅栏门. 默认值为 `true`.

其所具有的方块状态(`Block States`): `facing`(朝向)(`north`, `south`, `east`, `west`), `in_wall`(true, false), `open`(是否开启)(true, false).

译者注: 在原文中, 该子类所具有的方块状态 `in_wall` 经译者查明, 该方块状态的所具有意义如下:
> 如果为 `true` , 这个栅栏门将被降低了三个像素, 使其更贴合圆石墙和苔石墙的高度.

来处: [URL](https://minecraft-zh.gamepedia.com/%E6%A0%85%E6%A0%8F%E9%97%A8)

# Wall(类圆石墙或苔石墙)
类名: __`block:wall`__

该子类定义了一个类似圆石墙或苔石墙的方块模型. 其支持全部的16种子类型. 其不具有任何附加属性.

其所具有的方块状态(`Block States`): `subtype`(子类型)(`0` 到 `15`), `north`(是否朝北)(`true`, `false`), `south`(是否朝南)(`true`, `false`), `east`(是否朝东)(`true`, `false`), `west`(是否朝西)(`true`, `false`), `up`(是否朝上)(`true`, `false`)

# Trap Door(活板门)
类名: __`block:trapDoor`__

该子类定义了一个类似活板门的方块模型. 该子类**不支持**子类型. 其具有以下附加属性:

```json
{
  "opensWithRedstone": true,
  "openWithHands": true
}
```

* __opensWithRedstone__: 该属性定义了是否可以应用红石信号来打开或关闭栅栏门. 默认值为 `true`.
* __opensWithHands__: 该属性定义了玩家是否可以使用右键单击来打开或关闭栅栏门. 默认值为 `true`.

其所具有的方块状态(`Block States`): `facing`(朝向)(`north`, `south`, `east`, `west`), `half`(活板门是在所依附方块的顶部或底部)(`top`, `bottom`), `open`(是否开启)(true, false).

# Torch(火把)
类名: __`block:torch`__

该子类定义了一个类似火把的方块模型. 该子类**不支持**子类型. 其具有以下附加属性:

```json
{
  "spawnParticles": true
}
```

* __spawnParticles__: 该属性定义了作为火把的该方块是否应该产生火焰和烟雾颗粒. 默认值为 `true`.

其所具有的方块状态(`Block States`): `facing`(朝向)(`north`, `south`, `east`, `west`, `up`)

# Button(按钮)
类名: __`block:button`__

该子类定义了一个类似按钮的方块模型. 该子类**不支持**子类型. 其具有以下附加属性:

```json
{
  "pressedTicks": 20,
  "triggeredByArrows": false
}
```

* __pressedTicks__: 该属性定义了作为按钮的该方块保持按下状态的 游戏刻(`Tick`) 数。 默认值为 `20`.
* __triggeredByArrows__: 该属性定义了作为按钮的该方块是否可以被射出的箭所激活. 默认值为 false.

其所具有的方块状态(`Block States`): `facing`(朝向)(`north`, `south`, `east`, `west`, `up`), `powered`(是否被激活)(`true`, `false`)

# Pane(玻璃板)
类名: __`block:pane`__

该子类定义了一个类似玻璃板或是铁栏杆等的方块模型. 其支持全部的16种子类型. 其不具有任何附加属性.

其所具有的方块状态(`Block States`): `subtype`(子类型)(`0` 到 `15`), `north`(是否朝北)(`true`, `false`), `south`(是否朝南)(`true`, `false`), `east`(是否朝东)(`true`, `false`), `west`(是否朝西)(`true`, `false`)

# Pressure Plate(压力板)
类名: __`block:pressurePlate`__

该子类定义了一个类似压力板的方块模型. 该子类**不支持**子类型. 其具有以下附加属性.

```json
{
  "pressedTicks": 20,
  "selector": "everything",
  "onSound": "block.wood_pressureplate.click_on",
  "offSound": "block.wood_pressureplate.click_off"
}
```

* __pressedTicks__: 该属性定义了作为压力板的该方块保持在受到压力而激活状态的 游戏刻(Tick) 数. 默认值为 `20`.
* __selector__: 该属性定义了哪些实体可以触发压力板. 该属性可以是任意实体的名称(类似`minecraft:sheep`, `minecraft:creeper`), 也可以是这几个中的一个: [`everything`(任何东西), `nothing`(不为任何东西), `livings`(玩家或任意生物), `players`(玩家), `items`(物品)] 所触发. 默认值为 `everything`.
* __onSound__, __offSound__: 该属性定义了当作为压力板的该方块被按下或弹起时游戏所播放的声音的名称. 默认值为 `block.wood_pressureplate.click_on` 和 `block.wood_pressureplate.click_off`

其所具有的方块状态(`Block States`): `powered`(是否被激活)(`true`, `false`)