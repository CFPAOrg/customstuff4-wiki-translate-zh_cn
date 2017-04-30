# All Tile Entities
Some attributes are used by all types of tile entities:

```json
{
	"id" : "mytileentity",
	"modules" : [
		{
			"type": "inventory",
			"name": "inv1",
			"size": 27
		}
	]
}
```

* __id__: This is the unique id of the tile entity. This is used to reference the tile entity in blocks. This has to be all lowercase and must not contain spaces. It only has to be unique in your mod.

* __modules__: This is a list of tile entity modules. These modules add functionality to the tile entity.

# Tile Entity Modules
All modules have the following attributes:

```json
{
	"type": "inventory",
	"name": "inv1"
}
```

* __type__: This is the type of the module. Depending on this, more attributes are available.
* __name__: This is the name of the module. It has to be unique in the tile entity only. This is used to reference the module, for example in a gui file.

## Inventory
Type name: __inventory__

This module adds a simple inventory to the tile entity. It has the following attributes:

```json
{
	"size": 27,
	"sides": ["up", "down", "east", "west"]
}
```

* __size__: This defines how many slots the inventory has.
* __sides__: This defines from what sides the inventory can be accessed, for example by the hopper. The default is all sides.

# Simple
Type name: __tileentity:simple__

This tile entity has no special functionality. There are no additional attributes for this tile entity.