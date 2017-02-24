#All Blocks
Some attributes are used by all types of blocks:

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
	"information" : [ "First line", "Second line"]
}
```

* __id__: This is the unique id of the block. This is used to reference the block in recipes or in the lang file. This has to be all lowercase and must not contain spaces. It only has to be unique in your mod. If your mod id is _mymod_ and the item id is _myblock_, you reference the item with _mymod:block_. The block state files is then located in _assets/mymod/blockstates/myblock.json_. If the block has an item associated with it as most blocks do, that item has the same id.

* __material__: This is the material of the block. The material defines different default properties for the block such as if it is translucent or if it requires a tool to mine. The default value is _ground_.

* __itemModel__: This defines the model file that is being used for the item of the block. In the example above the file is located in _assets/mymod/models/item/myitemmodel.json_. You can also use the model of another mod or minecraft itself. Supports metadata subtypes.

* __creativeTab__: This defines the creative tab that the item of the block appears in. Omit to make it not appear in any tab. Supports metadata subtypes.

* __hardness__: This defines how long it takes to break the block. Supports metadata subtypes. The default value is 1.0. 

* __resistance__: This defines the resistance against explosions. Supports metadata subtypes. The default value is 0.0.

* __soundType__: This defines the sound that is being played when the block is being walked on, breaked or placed. Supports metadata subtypes. The default value is stone.

* __maxStack__: This defines the maximum number of items in one stack. This has to be between 1 and 64. Supports metadata subtypes. The default value is 64.

* __opacity__: This defines the light opacity. This has to between 0 and 255 where 0 means all light goes through the block and 255 means none does. Supports metadata subtypes. The default value is 255.

* __light__: This defines how much light the block is emitting. This has to be between 0 and 15, where 0 means no light and 15 means as much light as possible. Supports metadata subtypes. The default value is 0.

* __flammability__: This defines the chance that fire will spread and consume the block. This has to be between 0 and 100, where 0 is 0% chance and 100 a 100% chance. Supports metadata subtypes. The default value is 0.

* __fireSpreadSpeed__: This defines how fast fire will spread around the block. Higher values mean higher speed. Supports metadata subtypes. The default value is 0.

* __isFireSource__: This defines whether fire indefinitely burns on the block. Supports metadata subtypes. The default value is false.

* __isWood__: This defines whether the block is wood. Supports metadata subtypes. The default value is false.

* __canSustainLeaves__: This defines whether leaves decay near the block. Supports metadata subtypes. The default value is false.

* __isBeaconBase__: This defines whether the block can be used as a base for the beacon. Supports metadata subtypes. The default value is false.

* __enchantPowerBonus__: This defines the amount of enchanting power this block can provide to an enchanting table. Supports metadata subtypes. The default value is 0.0.

* __expDrop__: This defines the amount of exp dropped when breaking the block. You can define it like this: `5` or like this: `[1, 5]`. The first one will always drop 5 exp, the second one drops a random amount between 1 and 5. Supports metadata subtypes. The default value is 0.

* __information__: This defines additional lines of information below the name of the item in the inventory. Supports metadata subtypes.

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

#Lang File
The lang files are located in _assets/themodid/lang_.

The lang file entry for a block without subtypes looks like this:

```
tile.themodid.theblockid.name=The Localized Name
```

And for a block with subtypes:

```
tile.themodid.theblockid.0.name=Subtype 0
tile.themodid.theblockid.1.name=Subtype 1
tile.themodid.theblockid.5.name=Subtype 5
```

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

#Sound Types
The following sound types can be used.

* anvil
* cloth
* glass
* grass
* gravel
* ladder
* metal
* sand
* slime
* snow
* stone
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

This block has no special functionality, like stone or dirt. It supports all 16 metadata subtypes. There are no additional attributes for this block.

Block state properties: subtype.