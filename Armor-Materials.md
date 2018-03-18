Armor materials are used by armor items to define certain properties for them.

Type name: __armorMaterial__

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

* __id__: This is the unique id of the material. This is the id, you set the material property of armor items to.
* __textureName__: The name of the armor texture. This defines two textures: one for helmet, chest and boots and one for legs. If this is set to `examplemod:myleather`, the paths of the two textures will be `assets/examplemod/textures/armor/myleather_layer_1.png` for helmet, chest and boots and `assets/examplemod/textures/armor/myleather_layer_2.png` for legs.
* __durability__: How many uses the armor. This value is multiplied by another value depending on the type of armor, 13 for boots, 15 for legs, 16 for chest and 11 for helmet. The default value is 5.
* __enchantability__: This defines how enchantable the armor is. Default value is 15.
* __armorHelmet__, __armorChest__, __armorLegs__, __armorBoots__: These define the armor values for the different armor types. Default values are 1 (helmet), 3 (chest), 2 (legs) and 1 (boots).
* __equipSound__: The sound that is played when the armor is being equipped. Default value is `item.armor.equip_leather`.
* __toughness__: Defines the toughness for the armor. Default value is 0.0.
* __repairItem__: This is an ItemStack that defines what can be used to repair the armor. Can be omitted to make the armor unrepairable.