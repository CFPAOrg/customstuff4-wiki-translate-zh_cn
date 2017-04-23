This is a list of how to specify certain things in json. 

# ResourceLocation
A ResourceLocation is used to define the location of textures, models, or for item or block identifiers. There are two ways to define an ResourceLocation.

Short version:

```json
"minecraft:stone"
	
"minecraft:textures/gui/bars.png"
```
	
Long version:

```json
{
  "domain" : "minecraft",
  "path" : "stone"
}

{
  "domain" : "minecraft",
  "path" : "textures/gui/bars.png"
}
```

# NBTTagCompound
A NBTTagCompound is defined as a string containg the nbt data:

```json
"{display:{Name:\"Some Obsidian\"}}"
```
	
#ItemStack
There a multiple ways of specifying an item stack:

```json
{
  "item" : "minecraft:stone",
  "metadata" : 10,
  "amount" : 42,
  "nbt" : "{display:{Name:\"Some Obsidian\"}}"
}
```
	
Everything but _item_ is optional. _metadata_ defaults to 0, _amount_ to 1.  
For some recipes you may want to allow all metadata variants. This can be done like this:

```json
{
  "item": "minecraft:stone",
  "metadata": "all",
  "amount": 42
}
```
	
There is also a short version of defining an item stack. However that way you can only define the item and metadata:

```json
"minecraft:stone"
	
"minecraft:stone@1"
	
"minecraft:stone@all"
```
	
This will define an stack with an amount of 1. Omitting the metadata part will default in a metadata of 0.

## Examples
The following is a smelting recipe. Both _input_ and _result_ are item stacks:

```json
{
  "input": "minecraft:stone@all",
  "result": {
    "item": "minecraft:obsidian",
    "amount": 3,
    "nbt": "{display:{Name:\"Custom Obsidian\"}}"
  }
}
```
	
# RecipeInput
A recipe input is either an ItemStack or a ore class.
An ore class is defined like this:

```json
"oreclass:stickWood"
```
	
An ItemStack is defined as usual.

## Examples
The following is the input part of a shapeless recipe, _items_ is a list of RecipeInput:

```json
{
  "items": [
    "minecraft:stone@all",
    "oreclass:stickWood",
    {
      "item": "minecraft:obsidian",
      "metadata": 0
    }
  ]
}
```

# PotionEffect
A potion effect defines the effect itself and the duration and amplifier.

```json
{
	"id": "minecraft:hunger",
	"duration": 60,
	"amplifier" : 2,
	"showParticles": false
}
```

* __id__: This is a ResourceLocation defining what effect is being used.
* __duration__: The duration of the effect in ticks. The default value is 60 (3 seconds).
* __amplifier__: An amplifier for the effect. This increases the effect. The default value is 1.
* __showParticles__: Whether to show the effect particles. The default value is true.