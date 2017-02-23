#All Blocks
Some attributes are used by all types of blocks:

```json
{
	"id" : "myblock",
	"material" : "ground",
	"itemModel" : "mymod:myitemmodel",
	"creativeTab" : "redstone",
	"hardness" : 2.5
}
```

* __id__: This is the unique id of the block. This is used to reference the block in recipes or in the lang file. This has to be all lowercase and must not contain spaces. It only has to be unique in your mod. If your mod id is _mymod_ and the item id is _myblock_, you reference the item with _mymod:block_. The block state files is then located in _assets/mymod/blockstates/myblock.json_. If the block has an item associated with it as most blocks do, that item has the same id.

* __material__: This is the material of the block. The material defines different default properties for the block such as if it is translucent or if it requires a tool to mine. The default value is _ground_.

* __itemModel__: This defines the model file that is being used for the item of the block. In the example above the file is located in _assets/mymod/models/item/myitemmodel.json_. You can also use the model of another mod or minecraft itself. Supports metadata subtypes.

* __creativeTab__: This defines the creative tab that the item of the block appears in. Omit to make it not appear in any tab. Supports metadata subtypes.

* __hardness__: This defines how long it takes to break the block. The default value is 1.0.

#Metadata Subtypes
Some block types support metadata subtypes. That means the block can have different models, names or other things depending on their metadata value.  
If a block type supports metadata subtypes, you can enable it by providing the _subtypes_ attribute:

```json
{
	"subtypes" : [ 0, 1, 5 ]
}
```
This will make the item have subtypes for metadata values 0, 1 and 5. You should always have a 0 in their. Depending on the type of the block, you can use up to 16 subtypes (0 to 15).

You can now define attribute values for each of those metadata values provided that the attribute is supporting it:

```json
{
	"itemModel" : {
		"0" : "mymod:myitem_0",
		"1" : "mymod:myitem_1",
		"5" : "mymod:myitem_5"
	}
}
```

You can still define the attribute like this:

```json
{
	"itemModel" : "mymod:myitem"
}
```

This will set the value for all subtypes.

#Materials
The following materials can be used:

* air
* cactus
* circuits
* clay
* cloth
* craftedSnow
* fire
* glass
* grass
* ground
* ice
* iron
* lava
* leaves
* plants
* pumpkin
* redstoneLight
* rock
* sand
* snow
* sponge
* tnt
* vine
* water
* wood

#Block States
The blockstate file defines what model the block uses depending on its state. For example the metadata subtype is a state. A simple blockstate file for a block using subtypes might look like this:

```json
{
  "variants": {
	"subtype=subtype0": {"model": "firstpack:sensor_iron"},
	"subtype=subtype1": {"model": "firstpack:sensor_gold"}
  }
}
```

For more information about block states, you might look here: http://minecraft.gamepedia.com/Model#Block_states

#Simple
Type name: __block:simple__

This block has no special functionality, like stone or dirt. It supports metadata subtypes. There are no additional attributes for this block.

Block state properties: subtype.