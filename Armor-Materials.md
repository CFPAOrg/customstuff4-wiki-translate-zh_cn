装甲使用装甲材料来定义装甲的某些属性.

类型名称: __armorMaterial__

```json
{
  "id" : "myleather",
  "textureName" : "examplemod:myleather",
  "durability": 5,
  "enchantability": 15,
  "armorHelmet": 1,
  "armorChest": 3,
  "armorLegs": 2,
  "armorBoots": 1,
  "equipSound": "item.armor.equip_leather",
  "toughness": 0.0,
  "repairItem": "minecraft:leather"
}
```

* __id__: 该属性定义该材料的唯一ID. 你可以使用ID设置装甲的材料.
* __textureName__: 该属性定义装甲材质的名称. 其包含了两种材质: 一种用于头盔, 胸甲和靴子, 另外一种用于护膝. 如果该属性被设置为 `examplemod:myleather`, 用于头盔, 胸甲和靴子的材质的路径将为 `assets/examplemod/textures/armor/myleather_layer_1.png`, 用于护膝的材质路径将为 `assets/examplemod/textures/armor/myleather_layer_2.png`.
* __durability__: 该属性定义用于该种装甲的耐久值. 该值将用于游戏计算装甲的实际耐久值, 计算方式如下: 如果一种装甲使用该材料, 那么该套装甲的头盔的最大耐久值为`11 * ${该属性}`, 以此类推, 胸甲为`16 * ${该属性}`, 护膝为`15 * ${该属性}`, 靴子则为`13 * ${该属性}`. 该属性的默认值为`5`.
* __enchantability__: 该属性定义了材料所具有的可附魔性. 该属性的默认值为`15`.
* __armorHelmet__, __armorChest__, __armorLegs__, __armorBoots__: 这些属性定义了不同装甲类型的装甲值. 默认值为 `1`(头盔[Helmet]) , `3`(胸甲[Chest]), `2`(护膝[Legs]), `1`(靴子[Boots]).
* __equipSound__: 该属性定义装备装甲时游戏播放的声音. 默认值为 `item.armor.equip_leather`.
* __toughness__: 该属性定义了装甲的韧性. 默认值为 `0.0`.
* __repairItem__: 该种属性定义了可用于修复使用该装甲材料的装甲的物品. 若省略该属性则会使使用该装甲材料的装甲无法修复.