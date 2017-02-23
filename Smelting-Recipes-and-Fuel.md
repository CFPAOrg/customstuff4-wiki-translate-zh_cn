#Smelting Recipes

Type name: __smeltingRecipe__

```json
{
  "input": "minecraft:stone",
  "result": {
    "item": "minecraft:obsidian",
    "amount": 3
  },
  "xp": 2.7
}
```
	
* __input__: This is an ItemStack and defines the input of the recipe. You may use "all" for metadata. Specifying _nbt_ here has no effect.

* __result__: This is an ItemStack and defines the result of the recipe.

* __xp__: This defines the experience gained from this recipe. This is optional and defaults to 0.

#Fuel

Type name: __fuel__

```json
{
  "item" : "minecraft:stone",
  "burnTime" : 800
}
```
	
* __item__: This is an ItemStack and defines the item that is being added as fuel for the furnace. You may use "all" for metadata and specify _nbt_.

* __burnTime__: The time in ticks that the item is burning. A second has 20 ticks.