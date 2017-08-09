# All Items
Some attributes are used by all types of items:

```json
{
	"id" : "myitem",
	"model" : "mymod:myitemmodel",
	"creativeTab" : "tools",
	"information" : ["First line", "Second line"],
	"maxDamage": 9,
	"tint": "red"
}
```

* __id__: This is the unique id of the item. This is used to reference the item in recipes or in the lang file. This has to be all lowercase and must not contain spaces. It only has to be unique in your mod. If your mod id is _mymod_ and the item id is _myitem_, you reference the item with _mymod:myitem_.

* __model__: This defines the model file that is being used. In the example above the file can be  located in _assets/mymod/models/item/myitemmodel.json_ or _assets/mymod/blockstates/myitemmodel.json_. You can also use the model of another mod or minecraft itself. Supports metadata subtypes. Default value is "[modid]:[itemid]".

* __creativeTab__: This defines the creative tab that the item appears in. Omit to make it not appear in any tab. Supports metadata subtypes.

* __information__: This defines additional lines of information below the name of the item in the inventory. Supports metadata subtypes.

* __maxDamage__: This defines if the item is damageable and by what amount it can be damaged. If using this, you can't use metadata subtypes for this item.

* __tint__: Adds a tint to the item. This is a color. Supports metadata subtypes.

# Metadata Subtypes
Some item types support metadata subtypes. That means the item can have different models, names or other things depending on their metadata value. For example dye is an example for this: each color is a metadata subtype of the same item.
If an item type supports metadata subtypes, you can enable it by providing the _subtypes_ attribute:

```json
{
	"subtypes" : [ 0, 1, 5 ]
}
```
This will make the item have subtypes for metadata values 0, 1 and 5. You should always have a 0 in their.

You can now define attribute values for each of those metadata values provided that the attribute is supporting it:

```json
{
	"model" : {
		"0" : "mymod:myitem_0",
		"1" : "mymod:myitem_1",
		"5" : "mymod:myitem_5"
	}
}
```

You can still define the attribute like this:

```json
{
	"model" : "mymod:myitem"
}
```

This will set the value for all subtypes.

# Lang File
The lang files are located in _assets/themodid/lang_.

The lang file entry for an item without subtypes looks like this:

```
item.themodid.theitemid.name=The Localized Name
```

And for an item with subtypes:

```
item.themodid.theitemid.0.name=Subtype 0
item.themodid.theitemid.1.name=Subtype 1
item.themodid.theitemid.5.name=Subtype 5
```
# Simple
Type name: __item:simple__

This item has no special functionality, like sticks or coal. It supports metadata subtypes.

```json
{
	"maxStack" : 32
}
```

* __maxStack__: This defines the maximum number of items in one stack. This has to be between 1 and 64. Supports metadata subtypes. The default value is 64.

# Axe, Pickaxe, Shovel, Sword
Type name: __item:axe__, __item:pickaxe__, __item:shovel__, __item:sword__

These items act like their vanilla equivalents. They do not support metadata subtypes. All of them has the same set of attributes.

```json
{
	"material" : "iron",
	"damage" : 3.5,
	"attackSpeed" : 4.7,
	"durability" : 750
}
```

* __material__: This defines the material of the tool, which is responsible for mining speed, durability, damage and attack speed. Minecraft materials are wood, stone, iron, diamond and gold.
* __damage__: This defines the damage against entities. If omitted, the materials damage will be used.
* __attackSpeed__: This defines the attack speed. If omitted, the materials attack speed will be used.
* __durability__: This defines the number of uses before the tool breaks. If omitted, the materials durability will be used.

# Food
Type name: __item:food__

As the name suggests, this item type is for food. It supports metadata subtypes.

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

* __maxStack__: This defines the maximum number of items in one stack. This has to be between 1 and 64. Supports metadata subtypes. The default value is 64.
* __healAmount__: The amount the item heals the player. Supports metadata subtypes. The default value is 2.
* __saturation__: The amount of saturation that this food provides. The default value is 0.6. Supports metadata subtypes.
* __alwaysEdible__: This defines whether the food can be eaten even if the player has a filled food bar. The default value is false. Supports metadata subtypes.
* __potionEffect__: This is a PotionEffect that defines what effect is being added to the player. Omit if no effect should be added. Supports metadata subtypes.
* __potionEffectProbability__: This defines the probability that the potion effect is being added to the player. 0.5 means a 50% chance, 1.0 means it is being added everytime. The default value is 1.0. Supports metadata subtypes.
* __isWolfFood__: This defines whether wolves like this food. The default value is false.
* __result__: This is a ItemStack that, if defined, sets the item that is returned to the inventory when the food has been eaten. Supports metadata subtypes.
* __useAction__: This is either eat or drink and defines whether the player eats or drinks this food. Supports metadata subtypes.

# Fluid Container
Type name: __item:fluidContainer__

This will create a container that can hold any fluid. It does not support metadata subtypes. It has one additional attribute:

```json
{
	"capacity" : 1000
}
```

* __capacity__: The capacity of the container. Default value is 1000.

To correctly use the model that dynamically uses the fluid texture, put the following model file to the blockstates folder:

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

You only need to modify the textures. The model has 3 layers: base, fluid and cover. Base is the background. Fluid is a white-only texture where the white part is replaced with the fluid texture. Cover is rendered on top of the base and fluid.


