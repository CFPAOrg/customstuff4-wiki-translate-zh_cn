#All Items
Some attributes are used by all types of items:

```json
{
	"id" : "myitem",
	"model" : "mymod:myitemmodel",
	"creativeTab" : "tools"
}
```

* __id__: This is the unique id of the item. This is used to reference the item in recipes or in the lang file. This has to be all lowercase and must not contain spaces. It only has to be unique in your mod and only for items. So you can also have a block with the same id. If your mod id is _mymod_ and the item id is _myitem_, you reference the item with _mymod:myitem_.

* __model__: This defines the model file that is being used. In the example above the file is located in _assets/mymod/models/item/myitemmodel.json_. You can also use the model of another mod or minecraft itself. Supports metadata subtypes.

* __creativeTab__: This defines the creative tab that the item appears in. Omit to make it not appear in any tab. Supports metadata subtypes.

#Metadata Subtypes
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

#Simple
Type name: __item:simple__

This item has no special functionality, like sticks or coal. It supports metadata subtypes. There are no additional attributes for this item.

#Axe, Pickaxe, Shovel
Type name: __item:axe__, __item:pickaxe__, __item:shovel__

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