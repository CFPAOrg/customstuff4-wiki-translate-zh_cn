# All Tile Entities
Some attributes are used by all types of tile entities:

```json
{
  "id": "mytileentity",
  "modules": [
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

## Crafting
Type name: __crafting__

This module adds crafting functionality to the tile entity. It has the following attributes:

```json
{
	"rows": 2,
	"columns": 3,
	"recipeList": "mymod:myrecipelist"
}
```

* __rows__, __columns__: The number of rows and columns of the crafting area. Both have to be 1, 2 or 3. Default value is 3.
* __recipeList__: This defines what recipes can be used. For vanilla recipes use "minecraft:vanilla". Default value is "minecraft:vanilla".

This module has rows * columns+1 slots: rows * columns for the input area and one for the recipe output. Input slots are numbered from left to right and top to bottom.

## Machine
Type name: __machine__

This module adds machine functionality to the tile entity, for example a furnace. It has the following attributes:

```json
{
  "inputSlots": 2,
  "outputSlots": 2,
  "fuelSlots": 2,
  "cookTime": 150,
  "recipeList": "mymod:machinerecipes",
  "fuelList": "mymod:machinefuel",
  "sidesInput": ["up"],
  "sidesOutput": ["down"],
  "sidesFuel": ["north", "south", "east", "west"],
  "inputTanks": ["input_tank"],
  "outputTanks": ["output_tank"]
}
```

* __inputSlots__: The number of input slots that the machine uses. Default value is 1.
* __outputSlots__: The number of output slots that the machine uses. Default value is 1.
* __fuelSlots__: The number of fuel slots for this machine. Note that two slots mean that the machine burns two items at once. Setting this to 0 means the machine works without fuel. Default value is 1.
* __cookTime__: The number of ticks a recipe takes to finish. If a recipe has its own cook time, the recipes time is used instead. Default value is 200.
* __recipeList__: This defines what recipes can be used. For vanilla furnace recipes use "minecraft:vanilla". Default value is "minecraft:vanilla".
* __fuelList__: This defines what items can be used as fuel. For vanilla furnace fuel use "minecraft:vanilla". Default value is "minecraft:vanilla".
* __sidesInput__, __sidesOutput__, __sidesFuel__: This defines from what sides the different slots can be accessed, for example by the hopper. Default value is as seen above.
* __inputTanks__, __outputTanks__: Defines the tanks that are used for the input and output of a recipe that uses fluids. The tanks have to be modules of the same tile entity. Default value is no tanks at all.

The slots are numbered like this: input then output then fuel.

## Tank
Type name: __tank__

This module adds a fluid tank to the tile entity. It has the following attributes:

```json
{
  "capacity": 10000,
  "canDrain": true,
  "canFill": true,
  "sides": ["north", "south", "east", "west", "up", "down"]
}
```

* __capacity__: The tank's capacity. Default values is 10000.
* __canDrain__: If the tank can be drained. Default value is true.
* __canFill__: If the tank can be filled. Default values is true.
* __sides__: Defines the sides from which the tank can accessed by clicking with a fluid container, pipe, etc. Default value is all sides.

# Simple
Type name: __tileentity:simple__

This tile entity has no special functionality. There are no additional attributes for this tile entity.